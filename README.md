# desafio-dio-app-financas

#PRD Refinado no Gemini 
# 🟢 Finances Will

> **Gestão financeira pessoal descomplicada por meio de conversas com Inteligência Artificial.**

O **Finances Will** é um aplicativo de finanças pessoais focado em iniciantes que elimina a burocracia do preenchimento manual de planilhas. Através de uma interface conversacional e recomendações educativas personalizadas, o usuário registra gastos em linguagem natural e recebe orientações práticas para poupar e investir.

Você pode testar o app em: https://conversa-financeira-em-dia.lovable.app
## 📌 Sumário

* [Sobre o Projeto](#-sobre-o-projeto)

* [Público-Alvo](#-público-alvo)

* [Funcionalidades Principais](#-funcionalidades-principais)

* [Arquitetura de Telas](#-arquitetura-de-telas)

* [Tech Stack](#-tech-stack--integrações)

* [Plano de Validação do MVP](#-plano-de-validação-do-mvp)

* [Prompt para Geração no Lovable](#-prompt-mestre-para-lovable)

*[Interação com Lovable](#-Interação-com-Lovable)

* [Conclusão]

## 📌 Sobre o Projeto

### O Problema

Muitas pessoas desistem de controlar suas finanças nos primeiros dias porque os aplicativos tradicionais exigem formulários extensos, cadastros manuais repetitivos e entregam pouca personalização ou auxílio prático.

### A Solução

O FinVibe AI permite registrar transações via chat simples em texto livre (ex: *"Gastei R\$ 45 no almoço"*), classifica os gastos de forma autônoma com Inteligência Artificial e oferece um assistente financeiro educativo para orientar aportes em **Tesouro Direto, Ações, FIIs e Criptomoedas**.

## 🎯 Público-Alvo

* **Iniciantes na Gestão Financeira:** Pessoas que querem organizar receitas e despesas sem complicação.

* **Novos Investidores:** Pessoas buscando entender os primeiros passos em Renda Fixa (Tesouro Direto) e Renda Variável (Ações/Cripto) de forma segura.

## ✨ Funcionalidades Principais

O aplicativo é dividido em **3 Abas Principais**:

### 💬 1. Controle Financeiro Básico

* **Registros em Linguagem Natural:** Chat interativo que interpreta e extrai dados de texto livre.

* **Categorização Automática:** Atribuição de tags (Alimentação, Transporte, Moradia, Lazer).

* **Agente Financeiro Educativo:** Dicas e alertas automáticos com base nos gastos do mês.

* **Painel de Balanço e Metas:** Visão gráfica de entradas, saídas e progresso da Reserva de Emergência.

### 📈 2. Investimentos (Renda Fixa, Tesouro Direto, Ações & FIIs)

* **Módulo Tesouro Direto:** Acompanhamento de títulos públicos (Tesouro Selic, IPCA+, Pré-fixado) com taxas e indexadores atualizados.

* **Módulo Ações & FIIs:** Carteira de renda variável com preço médio, cotação atual e Dividend Yield.

* **Simulador Comparativo:** Projeção visual comparando rendimentos da Poupança vs. Tesouro Selic vs. Benchmark em prazos configuráveis.

### ₿ 3. Criptomoedas

* **Monitor de Criptoativos:** Cotações e variação em tempo real (BTC, ETH, SOL).

* **Gestão de Risco:** Avisos e conceitos educativos sobre volatilidade e diversificação patrimonial.

## 📱 Arquitetura de Telas

A interface utiliza navegação mobile-first com barra inferior (*Bottom Navigation Bar*):

```
+-----------------------------------------------------------+
|                        HEADER APP                         |
+-----------------------------------------------------------+
|                                                           |
|                       CONTEÚDO DA                         |
|                      ABA ATIVA                            |
|                                                           |
+-----------------------------------------------------------+
|  [ 💬 Finanças ]   |   [ 📈 Investimentos ]  |  [ ₿ Cripto ] |
+-----------------------------------------------------------+

```

## 🛠️ Tech Stack & Integrações

* **Frontend:** React, Tailwind CSS, Lucide Icons, Recharts (Gráficos), Shadcn UI.

* **Backend / Database:** Supabase (PostgreSQL, Row Level Security, Auth).

* **Inteligência Artificial:** OpenAI GPT-4o-mini / Claude 3.5 Haiku via Supabase Edge Functions (saída estruturada em JSON).

* **APIs de Cotação:**

  * **Ações e FIIs:** [Brapi API](https://brapi.dev/)

  * **Tesouro Direto:** [BrasilAPI](https://brasilapi.com.br/)

  * **Criptomoedas:** [CoinGecko API](https://www.coingecko.com/en/api)

## 🚀 Plano de Validação do MVP

```
[ Fase 1: Protótipo ] ----> [ Fase 2: Teste Fechado ] ----> [ Fase 3: Ajustes & Retenção ]
  (Construção no Lovable)      (10-20 usuários reais)         (Taxa de acerto do Chat)

```

1. **Fase 1 - Acurácia da IA (Semana 1):** Validar se o agente interpreta com >90% de precisão as frases informadas no chat em português.

2. **Fase 2 - Teste de Uso Diário (Semanas 2 e 3):** Avaliar a retenção de 15 a 20 usuários iniciantes sem hábito prévio de uso de planilhas.

3. **Fase 3 - Validação Educativa:** Coletar feedbacks sobre o impacto das sugestões do Agente na economia pessoal do usuário.

## 🤖 Prompt Mestre para Lovable

Para gerar o protótipo funcional no **Lovable**, copie e cole o código abaixo na caixa de criação da plataforma:

```
Create a responsive, modern personal finance web app in Portuguese (Brazil) named "FinVibe AI" designed for financial beginners. Use Tailwind CSS, Lucide Icons, Shadcn UI components, and Recharts for charts.

### App Layout & Structure:
Implement a fixed bottom navigation bar (or sidebar on desktop) with 3 main tabs:
1. "Controle Financeiro" (Main Dashboard & Conversational Chat)
2. "Investimentos" (Tesouro Direto, Renda Fixa, Stocks & FIIs)
3. "Criptomoedas" (Crypto Assets Tracker)

---

### Tab 1: Controle Financeiro (Main Tab)
- **Top Header**: Show User Avatar, Monthly Net Balance card (Entradas, Saídas, Saldo Atual) using clean UI cards.
- **AI Agent Tip Widget**: A highlighted banner displaying educational saving advice (e.g., "Dica do Agente: Você gastou 15% a menos com delivery esta semana! Que tal guardar esse valor?").
- **Conversational Chat Interface**:
  - Input bar with placeholder: "Ex: Gastei 35 reais no almoço hoje..."
  - Interactive chat feed showing user messages and simulated AI parsing results (e.g., "Transação registrada: Almoço | R$ 35,00 | Categoria: Alimentação").
- **Recent Transactions Feed**: Interactive list of transactions with category badge, date, amount, and delete/edit buttons.
- **Goals Tracker**: Progress bar cards for user goals (e.g., "Reserva de Emergência", "Viagem no Fim de Ano").

---

### Tab 2: Investimentos (Renda Fixa, Tesouro Direto & Ações)
- **Portfolio Summary Card**: Total invested BRL across Fixed Income and Variable Income, total yield %, and monthly returns.
- **Sub-segment Switcher / Toggle**: Filter view between "Renda Fixa & Tesouro" and "Ações & FIIs".
- **Tesouro Direto & Renda Fixa Section**:
  - Cards for held bonds: Tesouro Selic 2029, Tesouro IPCA+ 2035, CDB 100% CDI.
  - Show Rate/Indexer (e.g., "Selic + 0.05%", "IPCA + 6.2%"), Invested Amount, and Current Gross/Net Balance.
  - Tag badge indicating liquidity type (e.g., "Liquidez Diária", "Resgate no Vencimento").
- **Ações e FIIs Section**:
  - Asset table with tickers (PETR4, VALE3, HGLG11), purchase price, current price, quantity, and dividend yield.
- **Educational AI Insights**: Cards explaining concepts like "Por que usar o Tesouro Selic para Reserva de Emergência?", "Marcação a Mercado", and "Dividend Yield".
- **Interactive Investment Simulator**: Sliders for Initial Value, Monthly Contribution, and Horizon (Years). Display interactive multi-line chart comparing Tesouro Selic, Poupança, and Benchmark Growth using Recharts.

---

### Tab 3: Criptomoedas
- **Crypto Portfolio Overview**: Total balance in BRL and 24h market variation badge.
- **Crypto List**: Display main coins (BTC, ETH, SOL) with sparkline/mini-charts, quantity owned, and value in BRL.
- **Risk Assessment Banner**: Educational warning card explaining crypto volatility and risk management for beginners.

---

### Design & Theme Guidelines:
- Color Palette: Emerald green primary accents (#10B981) for positive finances, dark slate text, subtle light gray background (#F8FAFC) for clean contrast.
- Friendly, accessible, and clean typography.
- Use mock state data using React `useState` so the user can interactively toggle sub-tabs, simulate investments, and type transactions in the chat input.

```



##Interação com Lovable
 > Foi colado o prompt gerado pelo Gemini acima.
 > Pedi para que acionasse um Banco de dados local para que as informaçõess do usuário ficassem salvas  ao acessar no seu navegador local.

##💬 Conclusão
  As ferramentas como Lovable aceleram muito a criação de uma aplicação. 
  Ferras mentas como Copalot, Chatgpt e Gemini podem agilizar um brainstorm ou  PRD por exemplo. 
  As ferramenta podem se auto completar pedindo pra criar prompts otimizados uma para outra e tornando o processo mais simples. A criação de apps com vibe code pode ser algo poderoso combinando hard skills com prompts certos é possível criar um infinidade de aplicações  de forma rápida e  eficiente. 
