# 🤖 Proposta de Automação de Testes — Landing Page Institucional

**Projeto:** QA Landing Page Institucional  
**Versão:** 1.0.0  
**Data:** Março/2026  

---

## 1. Introdução

Este documento apresenta uma proposta técnica para automatizar os testes manuais executados na landing page, reduzindo o tempo de regressão, aumentando a cobertura e garantindo consistência na validação a cada nova versão do sistema.

A automação **não substitui os testes exploratórios manuais**, mas elimina o trabalho repetitivo de verificar funcionalidades estáveis a cada ciclo, liberando o QA para focar em cenários mais complexos e na experiência do usuário.

---

## 2. Por que Automatizar?

| Situação Atual (Manual) | Com Automação |
|---|---|
| 20 casos executados em ~4 horas | 20 casos executados em ~8 minutos |
| Suscetível a erro humano por repetição | Execução determinística e consistente |
| Impossível executar a cada commit | Pipeline CI/CD executa testes automaticamente |
| Custo crescente por ciclo de regressão | Custo fixo após implementação |
| Dificuldade em testar múltiplos browsers | Multi-browser em paralelo com Selenium Grid |

---

## 3. Casos Prioritários para Automação

Com base nos testes manuais executados, os seguintes casos têm **alto valor de automação** por serem críticos, repetitivos e objetivamente verificáveis:

| ID | Caso de Teste | Justificativa para Automação |
|---|---|---|
| TC-001 | Botão WhatsApp no Header | CTA crítico — verificar URL e parâmetros |
| TC-002 | Botão WhatsApp no Hero | Principal CTA de conversão |
| TC-003 | Botão WhatsApp Fibra 400MB | Mensagem personalizada verificável |
| TC-004 | Botão WhatsApp Fibra 500MB | Mensagem personalizada verificável |
| TC-005 | Botão WhatsApp Fibra 700MB | Mensagem personalizada verificável |
| TC-009 | Preços dos planos | Dados críticos de negócio |
| TC-010 | Nome correto da consultora | Dado de identidade repetidamente alterado |
| TC-011 | Data automática no header | Lógica JS testável |
| TC-012 | Contatos no rodapé | Dados de contato críticos |
| TC-016 | Scroll suave via links | Navegação verificável |
| TC-017 | Header fixo no scroll | Comportamento CSS verificável |

---

## 4. Stack de Automação Recomendada

### 4.1 Opção Principal — Playwright (Recomendada)

```
Linguagem:  JavaScript / TypeScript
Framework:  Playwright (Microsoft)
Runner:     Playwright Test
Relatórios: HTML Reports nativos + Allure Report
CI/CD:      GitHub Actions
```

**Por que Playwright?**
- Suporte nativo a **Chromium, Firefox e WebKit** (Safari) em paralelo
- API moderna com async/await
- Captura automática de screenshots e vídeos em falhas
- Emulação de dispositivos móveis integrada (sem BrowserStack pago)
- Sem necessidade de drivers externos (diferente do Selenium)
- Excelente para projetos iniciantes de automação de portfólio

---

### 4.2 Opção Alternativa — Selenium WebDriver

```
Linguagem:  Java ou Python
Framework:  Selenium WebDriver 4.x
Gerenciador: Maven (Java) ou pip (Python)
Test Runner: TestNG (Java) ou pytest (Python)
Relatórios: ExtentReports (Java) ou Allure (Python)
```

**Quando usar Selenium:**
- Empresas com stack Java consolidado
- Projetos que já utilizam a ferramenta
- Maior oferta de vagas no mercado que exigem conhecimento em Selenium

---

### 4.3 Opção Para Iniciantes — Cypress

```
Linguagem:  JavaScript
Framework:  Cypress
Relatórios: Cypress Dashboard ou Mochawesome
```

**Quando usar Cypress:**
- Equipes focadas exclusivamente em front-end
- Curva de aprendizado mais suave
- Excelente DX (experiência do desenvolvedor) com interface visual

---

## 5. Estrutura do Projeto de Automação (Playwright)

```
qa-automation/
│
├── playwright.config.ts          → Configuração global (browsers, timeouts, base URL)
├── package.json
│
├── tests/
│   ├── contato/
│   │   ├── whatsapp-header.spec.ts
│   │   ├── whatsapp-hero.spec.ts
│   │   └── email-rodape.spec.ts
│   ├── planos/
│   │   ├── planos-fibra.spec.ts
│   │   └── planos-moveis.spec.ts
│   ├── conteudo/
│   │   ├── textos.spec.ts
│   │   └── precos.spec.ts
│   ├── responsividade/
│   │   ├── mobile-375.spec.ts
│   │   ├── tablet-768.spec.ts
│   │   └── desktop-1920.spec.ts
│   └── navegacao/
│       └── scroll-navegacao.spec.ts
│
├── pages/                        → Page Object Model
│   ├── LandingPage.ts
│   ├── PlansSection.ts
│   └── Footer.ts
│
├── fixtures/
│   └── test-data.ts              → Dados reutilizáveis (número WA, e-mail, preços)
│
└── reports/
    └── html/                     → Relatórios gerados automaticamente
```

---

## 6. Exemplos de Código

### 6.1 Teste de URL do WhatsApp por plano (Playwright + TypeScript)

```typescript
// tests/planos/planos-fibra.spec.ts

import { test, expect } from '@playwright/test';

const WHATSAPP_NUMBER = '5516997668997';
const BASE_URL = 'http://localhost:3000'; // ou URL de produção

const planos = [
  {
    nome: 'Internet Fibra 400MB',
    mensagem: 'Olá Bhianca Paulucci, tenho interesse no plano Internet Fibra 400MB.',
    preco: 'R$ 79,99'
  },
  {
    nome: 'Internet Fibra 500MB',
    mensagem: 'Olá Bhianca Paulucci, tenho interesse no plano Internet Fibra 500MB.',
    preco: 'R$ 89,99'
  },
  {
    nome: 'Internet Fibra 700MB',
    mensagem: 'Olá Bhianca Paulucci, tenho interesse no plano Internet Fibra 700MB.',
    preco: 'R$ 99,99'
  }
];

test.describe('Planos de Fibra — Botões WhatsApp', () => {

  test.beforeEach(async ({ page }) => {
    await page.goto(BASE_URL);
  });

  for (const plano of planos) {
    test(`[TC-00x] Botão WhatsApp do plano "${plano.nome}" gera URL correta`, async ({ page }) => {
      // Localiza o card pelo nome do plano
      const card = page.locator('.plan-card').filter({ hasText: plano.nome });

      // Verifica o preço exibido no card
      await expect(card.locator('.plan-price-value')).toContainText(plano.preco);

      // Captura o href do botão sem clicar (evita abrir o WhatsApp de fato)
      const botao = card.locator('.btn-plan');
      const href = await botao.getAttribute('href');

      // Valida o número
      expect(href).toContain(`wa.me/${WHATSAPP_NUMBER}`);

      // Valida a mensagem codificada
      const mensagemCodificada = encodeURIComponent(plano.mensagem);
      expect(href).toContain(mensagemCodificada);
    });
  }
});
```

---

### 6.2 Teste de responsividade mobile (Playwright)

```typescript
// tests/responsividade/mobile-375.spec.ts

import { test, expect, devices } from '@playwright/test';

test.describe('Responsividade — iPhone SE (375px)', () => {

  test.use({ ...devices['iPhone SE'] });

  test('[TC-013] Cards de planos não causam scroll horizontal em 375px', async ({ page }) => {
    await page.goto('/');

    // Aguarda os cards de planos renderizarem
    await page.waitForSelector('.plans-grid');

    // Verifica a largura total da página
    const bodyWidth = await page.evaluate(() => document.body.scrollWidth);
    const viewportWidth = page.viewportSize()?.width ?? 375;

    // Nenhum elemento deve causar overflow horizontal
    expect(bodyWidth).toBeLessThanOrEqual(viewportWidth + 1); // +1 para tolerância de sub-pixel
  });

  test('[TC-013] Card Fibra 500MB não ultrapassa os limites da viewport', async ({ page }) => {
    await page.goto('/');

    const card = page.locator('.plan-card.featured');
    const boundingBox = await card.boundingBox();
    const viewportWidth = page.viewportSize()?.width ?? 375;

    expect(boundingBox?.x).toBeGreaterThanOrEqual(0);
    expect((boundingBox?.x ?? 0) + (boundingBox?.width ?? 0)).toBeLessThanOrEqual(viewportWidth);
  });
});
```

---

### 6.3 Verificação de conteúdo textual crítico

```typescript
// tests/conteudo/textos.spec.ts

import { test, expect } from '@playwright/test';

test.describe('Conteúdo — Verificação de Textos Críticos', () => {

  test.beforeEach(async ({ page }) => {
    await page.goto('/');
  });

  test('[TC-010] Nome "Bhianca Paulucci" aparece consistente em toda a página', async ({ page }) => {
    const textoCompleto = await page.evaluate(() => document.body.innerText);

    // Verifica que o nome correto está presente
    expect(textoCompleto).toContain('Bhianca Paulucci');

    // Verifica que o nome errado NÃO está presente
    expect(textoCompleto).not.toMatch(/\bBianca\b(?!\s*Paulucci)/); // "Bianca" sem "Paulucci"
  });

  test('[TC-012] E-mail no rodapé está correto', async ({ page }) => {
    const emailLink = page.locator('#footerEmail');

    await expect(emailLink).toHaveAttribute('href', 'mailto:bhianca.paulucci@prodataempresas.com.br');
    await expect(emailLink).toContainText('bhianca.paulucci@prodataempresas.com.br');
  });

  test('[TC-012] Número do WhatsApp no rodapé está correto', async ({ page }) => {
    const waText = page.locator('#footerWaText');
    await expect(waText).toContainText('5516997668997');
  });
});
```

---

## 7. Integração com CI/CD (GitHub Actions)

```yaml
# .github/workflows/qa-tests.yml

name: QA — Testes Automatizados

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    timeout-minutes: 30

    steps:
      - name: Checkout do repositório
        uses: actions/checkout@v4

      - name: Configurar Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Instalar dependências
        run: npm ci

      - name: Instalar browsers do Playwright
        run: npx playwright install --with-deps

      - name: Executar testes
        run: npx playwright test --reporter=html

      - name: Publicar relatório de testes
        uses: actions/upload-artifact@v4
        if: always()
        with:
          name: playwright-report
          path: playwright-report/
          retention-days: 30
```

---

## 8. Roadmap de Implementação

| Fase | Ação | Esforço estimado |
|---|---|---|
| **Fase 1** | Setup do ambiente (Playwright + TypeScript + GitHub Actions) | 4h |
| **Fase 2** | Automatizar testes de botões WhatsApp (TC-001 a TC-008) | 6h |
| **Fase 3** | Automatizar testes de conteúdo (TC-009 a TC-012) | 4h |
| **Fase 4** | Automatizar testes de responsividade (TC-013 a TC-015) | 6h |
| **Fase 5** | Automatizar testes de navegação (TC-016 a TC-018) | 3h |
| **Fase 6** | Configurar pipeline CI/CD e relatórios Allure | 4h |
| **Total estimado** | | **~27 horas** |

---

## 9. Métricas Esperadas Após Automação

| Métrica | Atual (Manual) | Estimado (Automatizado) |
|---|---|---|
| Tempo de execução do ciclo completo | ~4 horas | ~8 minutos |
| Frequência de execução | Por demanda | A cada commit/PR |
| Cobertura de browsers | 2 (manual) | 3 simultâneos |
| Confiabilidade do resultado | Variável (humano) | Alta (determinístico) |
| Custo por ciclo de regressão | Alto | Próximo de zero |

---

## 10. Ferramentas de Apoio

| Ferramenta | Finalidade | Gratuito? |
|---|---|---|
| **Playwright** | Automação de testes E2E | ✅ Sim |
| **GitHub Actions** | CI/CD para execução automática | ✅ Sim (plano free) |
| **Allure Report** | Relatórios visuais detalhados | ✅ Sim |
| **axe-playwright** | Testes de acessibilidade automatizados | ✅ Sim |
| **Percy (BrowserStack)** | Testes de regressão visual | ⚡ Freemium |
| **Lighthouse CI** | Auditoria de performance automatizada | ✅ Sim |

---

*Documento gerado em: 24/03/2026*  
*Este roadmap pode ser adaptado conforme a disponibilidade de tempo e prioridades do projeto.*
