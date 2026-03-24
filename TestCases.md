# 📝 Casos de Teste — Landing Page Institucional

**Projeto:** QA Landing Page Institucional  
**Versão do sistema:** v1.0.0  
**Responsável:** QA Analyst  
**Data de criação:** Março/2026  
**Total de casos:** 20  

---

## Legenda de Status

| Ícone | Status |
|---|---|
| ✅ | Aprovado |
| ❌ | Reprovado |
| ⏳ | Não executado |
| ⚠️ | Bloqueado |

---

## 🔘 Módulo 1 — Botões e Links de Contato

---

### TC-001 — Botão WhatsApp no Header

| Campo | Detalhes |
|---|---|
| **ID** | TC-001 |
| **Módulo** | Header / Contato |
| **Descrição** | Verificar se o botão "Falar no WhatsApp" do header redireciona corretamente para o WhatsApp com o número configurado |
| **Pré-condição** | Página carregada com sucesso em navegador desktop; WhatsApp Web disponível |
| **Prioridade** | Alta |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Acessar a landing page
2. Localizar o botão "Falar no WhatsApp" no canto superior direito do header
3. Clicar no botão
4. Observar o redirecionamento

**Resultado Esperado:**  
O navegador deve abrir `https://wa.me/5516997668997` com a mensagem pré-preenchida: *"Olá Bhianca Paulucci, gostaria de saber mais sobre os planos Vivo Empresas."*

---

### TC-002 — Botão WhatsApp na seção Hero

| Campo | Detalhes |
|---|---|
| **ID** | TC-002 |
| **Módulo** | Hero / CTA Principal |
| **Descrição** | Verificar se o botão principal de CTA da seção Hero abre o WhatsApp corretamente |
| **Pré-condição** | Página carregada; seção Hero visível na tela |
| **Prioridade** | Alta |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Acessar a landing page
2. Na seção Hero (primeira seção visível), localizar o botão "Falar com consultora no WhatsApp"
3. Clicar no botão
4. Verificar a URL e mensagem no WhatsApp

**Resultado Esperado:**  
WhatsApp deve abrir com o número `5516997668997` e mensagem padrão pré-preenchida corretamente.

---

### TC-003 — Botão WhatsApp do plano "Internet Fibra 400MB"

| Campo | Detalhes |
|---|---|
| **ID** | TC-003 |
| **Módulo** | Planos / Cards |
| **Descrição** | Verificar se o botão "Quero este plano" do card Fibra 400MB gera mensagem personalizada correta |
| **Pré-condição** | Página carregada; seção de planos visível |
| **Prioridade** | Alta |
| **Status** | ❌ Reprovado |

**Passo a Passo:**
1. Rolar a página até a seção "Planos Empresariais"
2. Localizar o card "Internet Fibra 400MB"
3. Clicar no botão "Quero este plano"
4. Verificar a mensagem aberta no WhatsApp

**Resultado Esperado:**  
WhatsApp deve abrir com a mensagem: *"Olá Bhianca Paulucci, tenho interesse no plano Internet Fibra 400MB."*

**Resultado Obtido:**  
> ⚠️ Ver Bug #BUG-001

---

### TC-004 — Botão WhatsApp do plano "Internet Fibra 500MB"

| Campo | Detalhes |
|---|---|
| **ID** | TC-004 |
| **Módulo** | Planos / Cards |
| **Descrição** | Verificar se o botão "Quero este plano" do card Fibra 500MB (plano destaque) gera mensagem correta |
| **Pré-condição** | Página carregada; seção de planos visível |
| **Prioridade** | Alta |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Rolar a página até a seção "Planos Empresariais"
2. Localizar o card "Internet Fibra 500MB" (marcado como "Mais Recomendado")
3. Clicar no botão "Quero este plano"
4. Verificar a mensagem aberta no WhatsApp

**Resultado Esperado:**  
WhatsApp deve abrir com a mensagem: *"Olá Bhianca Paulucci, tenho interesse no plano Internet Fibra 500MB."*

---

### TC-005 — Botão WhatsApp do plano "Internet Fibra 700MB"

| Campo | Detalhes |
|---|---|
| **ID** | TC-005 |
| **Módulo** | Planos / Cards |
| **Descrição** | Verificar se o botão "Quero este plano" do card Fibra 700MB gera mensagem personalizada correta |
| **Pré-condição** | Página carregada; seção de planos visível |
| **Prioridade** | Alta |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Rolar a página até a seção "Planos Empresariais"
2. Localizar o card "Internet Fibra 700MB"
3. Clicar no botão "Quero este plano"
4. Verificar a mensagem aberta no WhatsApp

**Resultado Esperado:**  
WhatsApp deve abrir com a mensagem: *"Olá Bhianca Paulucci, tenho interesse no plano Internet Fibra 700MB."*

---

### TC-006 — Botão WhatsApp da seção Planos Móveis

| Campo | Detalhes |
|---|---|
| **ID** | TC-006 |
| **Módulo** | Planos Móveis / Banner |
| **Descrição** | Verificar se o botão "Quero saber mais" da seção de planos móveis abre WhatsApp com mensagem correta |
| **Pré-condição** | Página carregada; seção de planos móveis visível |
| **Prioridade** | Média |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Rolar a página até a seção "Planos Móveis para a sua equipe"
2. Localizar o botão "Quero saber mais"
3. Clicar no botão
4. Verificar a URL e mensagem no WhatsApp

**Resultado Esperado:**  
WhatsApp deve abrir com a mensagem: *"Olá Bhianca Paulucci, quero saber mais sobre os planos móveis da Vivo Empresas."*

---

### TC-007 — Link de e-mail no rodapé

| Campo | Detalhes |
|---|---|
| **ID** | TC-007 |
| **Módulo** | Rodapé / Contato |
| **Descrição** | Verificar se o link de e-mail no rodapé abre o cliente de e-mail padrão com o endereço correto |
| **Pré-condição** | Página carregada; cliente de e-mail configurado no sistema |
| **Prioridade** | Média |
| **Status** | ❌ Reprovado |

**Passo a Passo:**
1. Rolar a página até o rodapé
2. Localizar o link de e-mail na coluna "Consultora"
3. Clicar no link
4. Verificar se o cliente de e-mail abre com o endereço `bhianca.paulucci@prodataempresas.com.br`

**Resultado Esperado:**  
Cliente de e-mail padrão deve abrir com o campo "Para:" preenchido com `bhianca.paulucci@prodataempresas.com.br`

**Resultado Obtido:**  
> ⚠️ Ver Bug #BUG-002

---

### TC-008 — Botão WhatsApp flutuante

| Campo | Detalhes |
|---|---|
| **ID** | TC-008 |
| **Módulo** | Global / Botão Flutuante |
| **Descrição** | Verificar se o botão flutuante verde de WhatsApp (canto inferior direito) está visível e funcional em toda a página |
| **Pré-condição** | Página carregada em qualquer ponto do scroll |
| **Prioridade** | Alta |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Acessar a landing page
2. Verificar se o botão flutuante do WhatsApp está visível no canto inferior direito
3. Rolar a página até o final
4. Verificar se o botão permanece visível
5. Clicar no botão
6. Verificar o redirecionamento

**Resultado Esperado:**  
Botão deve estar fixo e visível em qualquer posição do scroll. Ao clicar, deve abrir o WhatsApp com o número correto.

---

## 🗂️ Módulo 2 — Conteúdo e Informações

---

### TC-009 — Exibição correta dos preços dos planos

| Campo | Detalhes |
|---|---|
| **ID** | TC-009 |
| **Módulo** | Planos / Conteúdo |
| **Descrição** | Verificar se os preços exibidos nos cards dos planos correspondem aos valores definidos |
| **Pré-condição** | Página carregada; seção de planos visível |
| **Prioridade** | Alta |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Rolar a página até a seção "Planos Empresariais"
2. Verificar o preço exibido no card "Internet Fibra 400MB"
3. Verificar o preço exibido no card "Internet Fibra 500MB"
4. Verificar o preço exibido no card "Internet Fibra 700MB"

**Resultado Esperado:**
- Fibra 400MB: **R$ 79,99/mês**
- Fibra 500MB: **R$ 89,99/mês**
- Fibra 700MB: **R$ 99,99/mês**

---

### TC-010 — Nome correto da consultora em toda a página

| Campo | Detalhes |
|---|---|
| **ID** | TC-010 |
| **Módulo** | Global / Conteúdo |
| **Descrição** | Verificar se o nome "Bhianca Paulucci" (com H) está correto em todos os pontos onde aparece na página |
| **Pré-condição** | Página carregada completamente |
| **Prioridade** | Alta |
| **Status** | ❌ Reprovado |

**Passo a Passo:**
1. Acessar a landing page
2. Verificar o nome no subtítulo do logo no header
3. Verificar o nome na seção Hero
4. Verificar o nome na seção "Sobre a Consultora"
5. Verificar o nome nos botões de CTA
6. Verificar o nome no rodapé

**Resultado Esperado:**  
O nome **"Bhianca Paulucci"** deve aparecer de forma idêntica e consistente em todos os pontos.

**Resultado Obtido:**  
> ⚠️ Ver Bug #BUG-003

---

### TC-011 — Data automática no header

| Campo | Detalhes |
|---|---|
| **ID** | TC-011 |
| **Módulo** | Header / Conteúdo |
| **Descrição** | Verificar se a data exibida no header corresponde à data atual do sistema |
| **Pré-condição** | Página carregada; JavaScript habilitado no navegador |
| **Prioridade** | Baixa |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Verificar a data atual no sistema operacional
2. Acessar a landing page
3. Localizar a data exibida no header (canto superior direito)
4. Comparar com a data do sistema

**Resultado Esperado:**  
A data exibida deve corresponder à data atual no formato: *"24 de março de 2026"*

---

### TC-012 — Informações de contato no rodapé

| Campo | Detalhes |
|---|---|
| **ID** | TC-012 |
| **Módulo** | Rodapé / Conteúdo |
| **Descrição** | Verificar se o número de WhatsApp, telefone e e-mail exibidos no rodapé estão corretos |
| **Pré-condição** | Página carregada; seção do rodapé visível |
| **Prioridade** | Alta |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Rolar a página até o rodapé
2. Localizar a coluna "Consultora"
3. Verificar o número de WhatsApp exibido
4. Verificar o telefone exibido
5. Verificar o e-mail exibido

**Resultado Esperado:**
- WhatsApp: `+5516997668997`
- Telefone: `(16) 99766-8997`
- E-mail: `bhianca.paulucci@prodataempresas.com.br`

---

## 📱 Módulo 3 — Responsividade

---

### TC-013 — Layout em smartphone (375px — iPhone SE)

| Campo | Detalhes |
|---|---|
| **ID** | TC-013 |
| **Módulo** | Responsividade / Mobile |
| **Descrição** | Verificar se o layout da página se adapta corretamente em telas de 375px de largura |
| **Pré-condição** | Chrome DevTools aberto; emulação de dispositivo móvel ativada (375x667) |
| **Prioridade** | Alta |
| **Status** | ❌ Reprovado |

**Passo a Passo:**
1. Abrir a landing page no Chrome
2. Abrir o Chrome DevTools (F12)
3. Ativar o modo de emulação de dispositivo
4. Selecionar o perfil "iPhone SE" (375x667)
5. Verificar o header: logo, nome da consultora e botão CTA
6. Verificar a seção Hero: título, subtítulo e botões
7. Verificar os cards de planos
8. Verificar o rodapé

**Resultado Esperado:**  
Todos os elementos devem se reorganizar em coluna única sem sobreposição, corte de texto ou elementos fora da área visível.

**Resultado Obtido:**  
> ⚠️ Ver Bug #BUG-004

---

### TC-014 — Layout em tablet (768px — iPad)

| Campo | Detalhes |
|---|---|
| **ID** | TC-014 |
| **Módulo** | Responsividade / Tablet |
| **Descrição** | Verificar se o layout da página se adapta corretamente em telas de 768px de largura |
| **Pré-condição** | Chrome DevTools aberto; emulação ativada com resolução 768x1024 |
| **Prioridade** | Média |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Abrir a landing page no Chrome
2. Abrir o Chrome DevTools
3. Selecionar resolução 768x1024
4. Verificar a grade dos cards de planos
5. Verificar o layout da seção "Sobre a Consultora"
6. Verificar o rodapé

**Resultado Esperado:**  
Cards de planos devem exibir no máximo 2 colunas; seção "Sobre" em coluna única; rodapé com 2 colunas.

---

### TC-015 — Layout em desktop fullHD (1920px)

| Campo | Detalhes |
|---|---|
| **ID** | TC-015 |
| **Módulo** | Responsividade / Desktop |
| **Descrição** | Verificar se o conteúdo se mantém centralizado e legível em telas widescreen |
| **Pré-condição** | Navegador em resolução 1920x1080 |
| **Prioridade** | Média |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Redimensionar o navegador para 1920x1080
2. Verificar se o conteúdo respeita a largura máxima (max-width: 1200px)
3. Verificar se há espaços laterais adequados
4. Verificar a legibilidade dos textos
5. Verificar se nenhum elemento fica excessivamente espaçado

**Resultado Esperado:**  
Conteúdo centralizado com max-width de 1200px, margens laterais simétricas e layout equilibrado.

---

## 🧭 Módulo 4 — Navegação

---

### TC-016 — Scroll suave via menu de navegação do rodapé

| Campo | Detalhes |
|---|---|
| **ID** | TC-016 |
| **Módulo** | Navegação / Scroll |
| **Descrição** | Verificar se os links de navegação do rodapé levam o usuário até a seção correta com animação de scroll suave |
| **Pré-condição** | Página carregada; JavaScript habilitado |
| **Prioridade** | Média |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Rolar a página até o rodapé
2. Clicar no link "Planos Fibra"
3. Verificar se a página rola até a seção correta
4. Retornar ao rodapé e clicar em "Benefícios"
5. Verificar o scroll

**Resultado Esperado:**  
A página deve rolar suavemente (smooth scroll) até a seção correspondente ao link clicado.

---

### TC-017 — Header fixo durante o scroll

| Campo | Detalhes |
|---|---|
| **ID** | TC-017 |
| **Módulo** | Navegação / Header |
| **Descrição** | Verificar se o header permanece fixo no topo durante toda a rolagem da página |
| **Pré-condição** | Página carregada |
| **Prioridade** | Média |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Acessar a landing page
2. Rolar lentamente a página para baixo
3. Verificar se o header acompanha o scroll
4. Rolar até o rodapé e verificar se o header ainda está visível
5. Verificar se o efeito de sombra é aplicado após o scroll

**Resultado Esperado:**  
Header deve permanecer fixo no topo com `position: fixed`. Após scroll, deve exibir sombra sutil (glassmorphism).

---

### TC-018 — Botão "Ver planos" da seção Hero

| Campo | Detalhes |
|---|---|
| **ID** | TC-018 |
| **Módulo** | Navegação / Hero |
| **Descrição** | Verificar se o botão "Ver planos" da seção Hero leva corretamente até a seção de planos |
| **Pré-condição** | Página carregada; seção Hero visível |
| **Prioridade** | Média |
| **Status** | ✅ Aprovado |

**Passo a Passo:**
1. Na seção Hero, localizar o botão secundário "Ver planos"
2. Clicar no botão
3. Verificar se a página rola até a seção "Planos Empresariais"
4. Verificar se o scroll é suave

**Resultado Esperado:**  
A página deve rolar suavemente até a seção `#planos`, exibindo os três cards de planos de fibra.

---

## ⚡ Módulo 5 — Performance e Comportamento

---

### TC-019 — Carregamento das animações ao rolar a página

| Campo | Detalhes |
|---|---|
| **ID** | TC-019 |
| **Módulo** | Animações / UX |
| **Descrição** | Verificar se os elementos animados (cards, seções) surgem corretamente conforme o usuário rola a página |
| **Pré-condição** | Página recém-carregada; JavaScript habilitado |
| **Prioridade** | Baixa |
| **Status** | ❌ Reprovado |

**Passo a Passo:**
1. Acessar a landing page (sem scroll prévio)
2. Rolar lentamente a página para baixo
3. Observar se os cards de planos surgem com animação de entrada (fadeIn + translateY)
4. Observar se os cards de benefícios surgem com delays escalonados
5. Verificar se os elementos já visíveis no carregamento inicial estão corretos

**Resultado Esperado:**  
Cada seção deve surgir com a animação `.reveal` quando entrar na viewport. Elementos inicialmente visíveis devem já estar com opacidade 1.

**Resultado Obtido:**  
> ⚠️ Ver Bug #BUG-007

---

### TC-020 — Bloqueio de atalhos do DevTools

| Campo | Detalhes |
|---|---|
| **ID** | TC-020 |
| **Módulo** | Segurança / Proteção |
| **Descrição** | Verificar se os atalhos de teclado para abertura das ferramentas de desenvolvedor estão bloqueados |
| **Pré-condição** | Página carregada; JavaScript habilitado |
| **Prioridade** | Baixa |
| **Status** | ❌ Reprovado |

**Passo a Passo:**
1. Acessar a landing page
2. Pressionar a tecla **F12**
3. Verificar se o DevTools é bloqueado
4. Tentar o atalho **Ctrl + Shift + I**
5. Tentar o atalho **Ctrl + U** (ver código-fonte)
6. Tentar clicar com o botão direito do mouse

**Resultado Esperado:**  
F12, Ctrl+Shift+I, Ctrl+U e o menu de contexto (botão direito) devem ser bloqueados pela página.

**Resultado Obtido:**  
> ⚠️ Ver Bug #BUG-008

---

*Documento gerado em: 24/03/2026*  
*Próxima revisão: Após correção dos bugs reportados*
