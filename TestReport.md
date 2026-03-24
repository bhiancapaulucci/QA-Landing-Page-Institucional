# 📊 Relatório Final de Testes — Landing Page Institucional

**Projeto:** QA Landing Page Institucional  
**Versão testada:** v1.0.0  
**Responsável:** QA Analyst  
**Período de execução:** 24/03/2026  
**Data do relatório:** 24/03/2026  

---

## 1. Visão Geral

Este relatório consolida os resultados do ciclo completo de testes manuais executados na landing page institucional de consultoria comercial da Vivo Empresas. O objetivo foi validar a funcionalidade, usabilidade, responsividade e integridade de conteúdo da página antes da entrega ao cliente.

---

## 2. Escopo dos Testes

| Módulo | Casos de Teste | Executados |
|---|---|---|
| Botões e Links de Contato | 8 | 8 |
| Conteúdo e Informações | 4 | 4 |
| Responsividade | 3 | 3 |
| Navegação | 3 | 3 |
| Performance e Comportamento | 2 | 2 |
| **Total** | **20** | **20** |

---

## 3. Resultado dos Testes

### 3.1 Consolidado Geral

```
Total de casos de teste:   20
✅ Aprovados:              13  (65%)
❌ Reprovados:              7  (35%)
⏳ Não executados:          0  ( 0%)
⚠️ Bloqueados:              0  ( 0%)
```

### 3.2 Gráfico de Resultado (ASCII)

```
Aprovados   ████████████████████████████████░░░░░░░░░░░░░░░  65%
Reprovados  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░████████████████  35%
```

### 3.3 Resultado por Módulo

| Módulo | Aprovados | Reprovados | Taxa |
|---|---|---|---|
| Botões e Links de Contato | 5 | 3 | 62,5% |
| Conteúdo e Informações | 3 | 1 | 75% |
| Responsividade | 2 | 1 | 66,7% |
| Navegação | 3 | 0 | 100% |
| Performance e Comportamento | 0 | 2 | 0% |

---

## 4. Casos de Teste Aprovados

| ID | Descrição |
|---|---|
| TC-002 | Botão WhatsApp da seção Hero funciona corretamente |
| TC-004 | Botão do plano Fibra 500MB com mensagem personalizada correta |
| TC-005 | Botão do plano Fibra 700MB com mensagem personalizada correta |
| TC-006 | Botão "Quero saber mais" da seção Planos Móveis funcional |
| TC-008 | Botão flutuante do WhatsApp visível e funcional em toda a página |
| TC-009 | Preços dos planos exibidos corretamente (R$ 79,99 / R$ 89,99 / R$ 99,99) |
| TC-011 | Data automática no header exibe a data atual corretamente |
| TC-012 | Informações de contato no rodapé (número, telefone, e-mail) corretas |
| TC-014 | Layout tablet (768px) responsivo e sem quebras |
| TC-015 | Layout desktop fullHD (1920px) centralizado e bem proporcionado |
| TC-016 | Scroll suave via links do rodapé funciona corretamente |
| TC-017 | Header fixo com efeito glassmorphism durante o scroll |
| TC-018 | Botão "Ver planos" do Hero leva corretamente à seção de planos |

---

## 5. Casos de Teste Reprovados

| ID | Descrição | Bug Relacionado | Severidade |
|---|---|---|---|
| TC-003 | Mensagem do WhatsApp com nome incompleto no plano 400MB | BUG-001 | 🔴 Alta |
| TC-007 | Link de e-mail no rodapé abre endereço desatualizado | BUG-002 | 🔴 Alta |
| TC-010 | Nome "Bianca" (sem H) em 2 pontos da página | BUG-003 | 🟡 Média |
| TC-013 | Card 500MB ultrapassa a tela em smartphones de 375px | BUG-004 | 🟡 Média |
| TC-019 | Animações `.reveal` invisíveis com `prefers-reduced-motion` | BUG-007 | 🟡 Média |
| TC-020 | Bloqueio de F12 não funciona no Firefox | BUG-008 | 🟢 Baixa |
| — | Ausência de link "Planos Móveis" no header | BUG-005 | 🟢 Baixa |

---

## 6. Distribuição de Bugs por Severidade

| Severidade | Quantidade | % do Total |
|---|---|---|
| 🔴 Alta | 2 | 25% |
| 🟡 Média | 3 | 37,5% |
| 🟢 Baixa | 3 | 37,5% |
| **Total** | **8** | **100%** |

---

## 7. Principais Problemas Encontrados

### 🔴 Crítico — Requer correção imediata

**BUG-001 — Mensagem WhatsApp com nome incompleto**  
O botão do plano Fibra 400MB envia a mensagem com o nome "Bhianca" sem o sobrenome "Paulucci", comprometendo a identidade da consultora no primeiro contato com o cliente. Como o WhatsApp é o principal canal de conversão desta landing page, qualquer falha nesse fluxo representa risco direto de perda de negócio.

**BUG-002 — Link de e-mail desatualizado no rodapé**  
O atributo `href` do link de e-mail no rodapé permanece apontando para o endereço antigo (`@vivo.com.br`). Usuários que optarem pelo contato via e-mail não terão retorno da consultora, resultando em leads perdidos silenciosamente.

---

### 🟡 Importante — Requer correção no próximo ciclo

**BUG-003 — Inconsistência ortográfica no nome da consultora**  
O nome "Bhianca" (com H) aparece grafado como "Bianca" (sem H) em ao menos dois pontos da página. Essa inconsistência prejudica a credibilidade da página e a identidade da profissional.

**BUG-004 — Overflow horizontal em smartphones de 375px**  
O card do plano em destaque (Fibra 500MB) mantém uma escala `1.03` que não é removida em breakpoints mobile, causando scroll horizontal indesejado — um dos erros mais visíveis e frustrantes em experiências mobile.

**BUG-007 — Invisibilidade de conteúdo em usuários com redução de movimento**  
Elementos com a classe `.reveal` iniciam com `opacity: 0` sem fallback para a configuração de sistema `prefers-reduced-motion`. Isso torna o conteúdo invisível para usuários com necessidades de acessibilidade, potencialmente violando as diretrizes WCAG 2.1 AA.

---

### 🟢 Melhorias — Podem ser tratadas em sprints futuras

**BUG-005 — Planos Móveis sem acesso direto no header**  
A nova seção de Planos Móveis não possui link no menu principal do header, exigindo scroll ou uso do rodapé para acesso.

**BUG-006 — Quebra de layout em telas menores que 320px**  
Dispositivos muito compactos (ex: Galaxy Fold dobrado) exibem o preço dos planos com quebra de linha prejudicial à leitura.

**BUG-008 — Limitação técnica do bloqueio de F12 no Firefox**  
Por arquitetura do Firefox, atalhos nativos são processados antes do JavaScript da página, impossibilitando o bloqueio do F12 via `preventDefault()`. Comportamento esperado da plataforma.

---

## 8. Métricas de Qualidade

| Indicador | Valor | Referência |
|---|---|---|
| Taxa de aprovação nos testes | 65% | Meta: ≥ 80% |
| Bugs críticos (Alta severidade) | 2 | Meta: 0 |
| Bugs totais reportados | 8 | — |
| Cobertura de testes | 100% das funcionalidades mapeadas | — |
| Testes de acessibilidade contemplados | 1 (TC-019) | — |
| Testes cross-browser executados | 2 (Chrome + Firefox) | — |

---

## 9. Conclusão

A landing page apresenta **funcionamento adequado nas suas funcionalidades principais**, como os botões de WhatsApp dos planos de destaque (500MB e 700MB), a navegação interna, o header fixo e a exibição correta dos preços. A estrutura geral da página está bem construída e demonstra consistência no design.

Entretanto, **a taxa de aprovação de 65% está abaixo da meta de qualidade de 80%**, indicando que o sistema ainda não está pronto para um ambiente de produção de alta visibilidade. Os dois bugs de severidade Alta — a mensagem truncada no WhatsApp e o link de e-mail desatualizado — representam riscos diretos à conversão de clientes e devem ser priorizados antes do lançamento.

### Recomendação

> ⚠️ **Não recomendado para produção** na versão atual.

Antes do lançamento, recomenda-se:
1. Corrigir os bugs de severidade **Alta** (BUG-001 e BUG-002)
2. Corrigir os bugs de severidade **Média** (BUG-003, BUG-004, BUG-007)
3. Executar um novo ciclo de regressão cobrindo todos os casos reprovados
4. Atingir taxa de aprovação ≥ 85% antes da publicação definitiva

---

## 10. Próximos Passos

| Ação | Responsável | Prazo sugerido |
|---|---|---|
| Correção dos bugs Alta e Média | Desenvolvedor | 2 dias úteis |
| Re-teste dos casos reprovados | QA Analyst | 1 dia útil |
| Teste de regressão completo | QA Analyst | 1 dia útil |
| Aprovação para produção | Tech Lead / PO | Após regressão |

---

*Relatório gerado em: 24/03/2026*  
*QA Analyst — Projeto Landing Page Institucional v1.0.0*
