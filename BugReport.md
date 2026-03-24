# 🐛 Relatório de Bugs — Landing Page Institucional

**Projeto:** QA Landing Page Institucional  
**Versão do sistema:** v1.0.0  
**Responsável pelo reporte:** QA Analyst  
**Data:** Março/2026  
**Total de bugs:** 8  

---

## Legenda

| Campo | Opções |
|---|---|
| **Severidade** | 🔴 Alta — 🟡 Média — 🟢 Baixa |
| **Prioridade** | ⬆️ Urgente — ➡️ Normal — ⬇️ Baixa |
| **Status** | 🔴 Aberto — 🟡 Em análise — 🟢 Corrigido — ⚪ Fechado |

---

## BUG-001 — Mensagem do WhatsApp com nome truncado no plano 400MB

| Campo | Detalhes |
|---|---|
| **ID** | BUG-001 |
| **Relacionado ao teste** | TC-003 |
| **Módulo** | Planos / WhatsApp |
| **Severidade** | 🔴 Alta |
| **Prioridade** | ⬆️ Urgente |
| **Status** | 🔴 Aberto |
| **Ambiente** | Chrome 124 / Desktop / Windows 11 |
| **Data de descoberta** | 24/03/2026 |

**Título:** Mensagem automática do WhatsApp exibe nome incompleto ao clicar no plano Fibra 400MB

**Descrição:**  
Ao clicar no botão "Quero este plano" do card "Internet Fibra 400MB", a mensagem pré-preenchida no WhatsApp exibe o nome da consultora de forma incorreta, faltando o sobrenome "Paulucci".

**Passos para Reproduzir:**
1. Acessar a landing page
2. Rolar até a seção "Planos Empresariais"
3. Clicar no botão "Quero este plano" do card "Internet Fibra 400MB"
4. Observar a mensagem pré-preenchida no WhatsApp

**Resultado Esperado:**  
`Olá Bhianca Paulucci, tenho interesse no plano Internet Fibra 400MB.`

**Resultado Atual:**  
`Olá Bhianca, tenho interesse no plano Internet Fibra 400MB.`

**Evidência:**  
> Screenshot: `evidencias/bug-001-whatsapp-400mb.png` *(a ser anexado)*

**Impacto:**  
Alto — o botão de plano é um ponto crítico de conversão. Mensagem incorreta pode gerar confusão e reduzir a credibilidade do contato.

---

## BUG-002 — Link de e-mail no rodapé abre com endereço desatualizado

| Campo | Detalhes |
|---|---|
| **ID** | BUG-002 |
| **Relacionado ao teste** | TC-007 |
| **Módulo** | Rodapé / Contato |
| **Severidade** | 🔴 Alta |
| **Prioridade** | ⬆️ Urgente |
| **Status** | 🔴 Aberto |
| **Ambiente** | Firefox 125 / Desktop / Windows 11 |
| **Data de descoberta** | 24/03/2026 |

**Título:** Clique no e-mail do rodapé abre cliente de e-mail com endereço `@vivo.com.br` ao invés de `@prodataempresas.com.br`

**Descrição:**  
O link `mailto:` no rodapé da página está apontando para o endereço de e-mail antigo (`bhianca.paulucci@vivo.com.br`) em vez do endereço atualizado (`bhianca.paulucci@prodataempresas.com.br`). O texto exibido está correto, mas o atributo `href` permanece desatualizado.

**Passos para Reproduzir:**
1. Acessar a landing page
2. Rolar até o rodapé
3. Inspecionar o link de e-mail (hover para ver URL na barra de status)
4. Clicar no link e verificar o endereço no campo "Para:" do cliente de e-mail

**Resultado Esperado:**  
`mailto:bhianca.paulucci@prodataempresas.com.br`

**Resultado Atual:**  
`mailto:bhianca.paulucci@vivo.com.br`

**Impacto:**  
Crítico — e-mails enviados pelo usuário não chegarão à consultora, resultando em perda direta de leads.

---

## BUG-003 — Nome "Bianca" (sem H) aparece em 2 pontos da página

| Campo | Detalhes |
|---|---|
| **ID** | BUG-003 |
| **Relacionado ao teste** | TC-010 |
| **Módulo** | Global / Conteúdo |
| **Severidade** | 🟡 Média |
| **Prioridade** | ➡️ Normal |
| **Status** | 🔴 Aberto |
| **Ambiente** | Chrome 124 / Desktop e Mobile |
| **Data de descoberta** | 24/03/2026 |

**Título:** Nome da consultora grafado incorretamente como "Bianca" (sem H) no título da seção Hero e no botão CTA da seção "Sobre"

**Descrição:**  
O nome oficial da consultora é "Bhianca Paulucci" (com H após o B). Em dois pontos específicos da página, o nome aparece grafado incorretamente como "Bianca", sem a letra H: no subtítulo da seção Hero e no texto do botão da seção "Sobre a Consultora".

**Passos para Reproduzir:**
1. Acessar a landing page
2. Na seção Hero, ler o subtítulo abaixo do título principal
3. Rolar até a seção "Sobre a Consultora"
4. Observar o texto do botão de contato

**Resultado Esperado:**  
Todas as ocorrências devem exibir: **"Bhianca Paulucci"**

**Resultado Atual:**  
Exibe: "Bianca Paulucci" (faltando o H)

**Impacto:**  
Médio — inconsistência de identidade que pode causar desconfiança ou confusão no visitante.

---

## BUG-004 — Card de plano "Fibra 500MB" ultrapassa a largura da tela em iPhone SE (375px)

| Campo | Detalhes |
|---|---|
| **ID** | BUG-004 |
| **Relacionado ao teste** | TC-013 |
| **Módulo** | Responsividade / Mobile |
| **Severidade** | 🟡 Média |
| **Prioridade** | ➡️ Normal |
| **Status** | 🔴 Aberto |
| **Ambiente** | Chrome DevTools — Emulação iPhone SE (375x667) |
| **Data de descoberta** | 24/03/2026 |

**Título:** Card "Internet Fibra 500MB" (destaque) gera scroll horizontal em viewport de 375px

**Descrição:**  
Em dispositivos com tela de 375px de largura, o card do plano "Mais Recomendado" (Internet Fibra 500MB) mantém um `transform: scale(1.03)` que o faz ultrapassar os limites laterais da viewport, causando um scroll horizontal indesejado e quebrando o layout mobile.

**Passos para Reproduzir:**
1. Abrir o Chrome e acessar a landing page
2. Abrir DevTools → Toggle Device Toolbar
3. Selecionar "iPhone SE" (375x667)
4. Rolar até a seção de planos
5. Observar o card "Internet Fibra 500MB"

**Resultado Esperado:**  
Todos os cards devem se ajustar dentro da largura de 375px sem overflow.

**Resultado Atual:**  
Card com `transform: scale(1.03)` ultrapassa a borda direita da tela em ~8px, ativando scroll horizontal.

**Sugestão de Correção:**  
Remover ou reduzir o scale em breakpoints abaixo de 600px via media query:  
```css
@media (max-width: 600px) {
  .plan-card.featured { transform: none; }
}
```

**Impacto:**  
Médio — experiência degradada no dispositivo mais comum de acesso (smartphones compactos).

---

## BUG-005 — Seção de Planos Móveis não aparece no menu de navegação do header

| Campo | Detalhes |
|---|---|
| **ID** | BUG-005 |
| **Módulo** | Navegação / Header |
| **Severidade** | 🟢 Baixa |
| **Prioridade** | ⬇️ Baixa |
| **Status** | 🔴 Aberto |
| **Ambiente** | Chrome 124 / Desktop |
| **Data de descoberta** | 24/03/2026 |

**Título:** Ausência de link para a seção "Planos Móveis" na navegação principal do header

**Descrição:**  
A página conta com uma seção dedicada a "Planos Móveis" (`#planos-moveis`), porém o header não possui link de navegação direta para essa seção. O rodapé possui o link, mas o header — que é o ponto de navegação mais acessível — não referencia esse conteúdo.

**Passos para Reproduzir:**
1. Acessar a landing page no desktop
2. Verificar os links de navegação disponíveis no header
3. Confirmar a ausência do link "Planos Móveis"

**Resultado Esperado:**  
O header deve conter um link de navegação para a seção "Planos Móveis".

**Resultado Atual:**  
O header contém apenas o botão CTA de WhatsApp, sem links de seção.

**Impacto:**  
Baixo — a seção ainda é acessível via scroll e rodapé.

---

## BUG-006 — Texto de "preço por mês" cortado em telas de 320px (Galaxy Fold)

| Campo | Detalhes |
|---|---|
| **ID** | BUG-006 |
| **Módulo** | Responsividade / Ultra-compacto |
| **Severidade** | 🟢 Baixa |
| **Prioridade** | ⬇️ Baixa |
| **Status** | 🔴 Aberto |
| **Ambiente** | Chrome DevTools — Emulação Galaxy Fold dobrado (280px) |
| **Data de descoberta** | 24/03/2026 |

**Título:** Preço dos planos exibido com quebra de linha inesperada em telas de 280–320px

**Descrição:**  
Em telas extremamente compactas (280px–320px), como o Galaxy Fold em modo dobrado, o bloco de preço dos cards (`.plan-price-box`) quebra de linha de forma não prevista, separando o valor principal ("R$ 79,99") do texto "/mês" em linhas diferentes, prejudicando a leitura.

**Passos para Reproduzir:**
1. Abrir a landing page no Chrome
2. Abrir DevTools → Toggle Device Toolbar → Inserir largura 280px
3. Rolar até os cards de planos
4. Observar a exibição do preço

**Resultado Esperado:**  
`A partir de R$ 79,99 /mês` — tudo na mesma linha ou quebra harmoniosa.

**Resultado Atual:**  
"R$ 79,99" em uma linha e "/mês" isolado na linha seguinte.

**Impacto:**  
Baixo — afeta apenas dispositivos com telas abaixo de 320px, mercado muito reduzido.

---

## BUG-007 — Elementos com classe `.reveal` não animam em navegadores com `prefers-reduced-motion`

| Campo | Detalhes |
|---|---|
| **ID** | BUG-007 |
| **Relacionado ao teste** | TC-019 |
| **Módulo** | Animações / Acessibilidade |
| **Severidade** | 🟡 Média |
| **Prioridade** | ➡️ Normal |
| **Status** | 🔴 Aberto |
| **Ambiente** | Chrome 124 — Configuração do sistema: reduzir movimento ativado |
| **Data de descoberta** | 24/03/2026 |

**Título:** Elementos com animação `.reveal` ficam invisíveis (opacity: 0) quando o sistema possui `prefers-reduced-motion: reduce` ativado

**Descrição:**  
A classe `.reveal` inicia os elementos com `opacity: 0` e `transform: translateY(32px)`, aguardando a classe `.visible` ser adicionada via JavaScript para exibi-los. Quando o usuário possui a opção de sistema "Reduzir movimento" ativada, a transição CSS pode não ocorrer conforme esperado, deixando os elementos permanentemente invisíveis em alguns navegadores.

**Passos para Reproduzir:**
1. No Windows: Configurações → Acessibilidade → Efeitos Visuais → Desativar animações
2. Acessar a landing page
3. Rolar pela página e observar as seções

**Resultado Esperado:**  
Todos os elementos devem ser exibidos normalmente, com ou sem animação, independente da configuração de acessibilidade.

**Resultado Atual:**  
Elementos permanecem com `opacity: 0` — conteúdo invisível.

**Sugestão de Correção:**  
Adicionar media query de acessibilidade no CSS:  
```css
@media (prefers-reduced-motion: reduce) {
  .reveal { opacity: 1; transform: none; transition: none; }
}
```

**Impacto:**  
Médio — afeta usuários com necessidades de acessibilidade, potencialmente violando diretrizes WCAG 2.1.

---

## BUG-008 — Bloqueio de F12 não funciona no Firefox

| Campo | Detalhes |
|---|---|
| **ID** | BUG-008 |
| **Relacionado ao teste** | TC-020 |
| **Módulo** | Segurança / Proteção |
| **Severidade** | 🟢 Baixa |
| **Prioridade** | ⬇️ Baixa |
| **Status** | 🔴 Aberto |
| **Ambiente** | Firefox 125 / Desktop / Windows 11 |
| **Data de descoberta** | 24/03/2026 |

**Título:** Tecla F12 abre o DevTools do Firefox normalmente, ignorando o bloqueio implementado

**Descrição:**  
O script de proteção implementado na página bloqueia corretamente o F12 no Chrome via `preventDefault()` no evento `keydown`. No Firefox, no entanto, a abertura do DevTools via F12 ocorre antes que o evento JavaScript seja capturado, contornando o bloqueio.

**Passos para Reproduzir:**
1. Abrir a landing page no Firefox
2. Pressionar a tecla **F12**
3. Observar se o DevTools abre

**Resultado Esperado:**  
A tecla F12 deve ser bloqueada e o DevTools não deve abrir.

**Resultado Atual:**  
O DevTools do Firefox abre normalmente, ignorando o evento JavaScript.

**Nota técnica:**  
Este comportamento é intencional do Firefox por razões de segurança do próprio navegador — ele processa atalhos nativos antes de delegar ao JavaScript. Este bug é de difícil correção sem soluções nativas do navegador.

**Impacto:**  
Baixo — como documentado, proteções via JavaScript são camadas de dificultação, não de bloqueio total.

---

## 📊 Resumo dos Bugs

| ID | Título (resumido) | Severidade | Status |
|---|---|---|---|
| BUG-001 | Mensagem WhatsApp com nome incompleto (400MB) | 🔴 Alta | 🔴 Aberto |
| BUG-002 | Link de e-mail com endereço desatualizado | 🔴 Alta | 🔴 Aberto |
| BUG-003 | Nome "Bianca" sem H em 2 pontos da página | 🟡 Média | 🔴 Aberto |
| BUG-004 | Card 500MB ultrapassa viewport em 375px | 🟡 Média | 🔴 Aberto |
| BUG-005 | Planos Móveis sem link no header | 🟢 Baixa | 🔴 Aberto |
| BUG-006 | Preço com quebra em telas de 280px | 🟢 Baixa | 🔴 Aberto |
| BUG-007 | `.reveal` invisível com prefers-reduced-motion | 🟡 Média | 🔴 Aberto |
| BUG-008 | F12 não bloqueado no Firefox | 🟢 Baixa | 🔴 Aberto |

---

*Documento gerado em: 24/03/2026*  
*Todos os bugs devem ser revisados antes do próximo ciclo de testes*
