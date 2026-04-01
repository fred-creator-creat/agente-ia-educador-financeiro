# 🛡️ Memorial de Desenvolvimento: Projeto VIGI (Vigilante Financeiro)

Este documento registra as etapas de planejamento, implementação e validação do **VIGI**, um Agente Financeiro Inteligente proativo desenvolvido para segurança patrimonial e consultoria de gastos.

---

## 📋 1. Documentação do Agente
O foco do VIGI é a **Segurança Financeira Proativa**. Diferente de chatbots reativos, o VIGI analisa o comportamento de gastos para identificar riscos e sugerir otimizações de reserva de emergência.

* **Caso de Uso:** Consultoria e proteção financeira baseada em dados reais.
* **Persona:** Especialista em segurança, direto, educativo e preventivo.
* **Arquitetura:** * Entrada do Usuário via Interface Python (ipywidgets).
    * Contextualização via Base de Dados (CSV/JSON).
    * Processamento por LLM (Gemini 1.5 Flash).
    * Saída formatada com estratégias anti-alucinação.

## 🗂️ 2. Base de Conhecimento
O agente utiliza quatro fontes de dados estruturadas para fundamentar suas respostas:
* `transacoes.csv`: Histórico de fluxo de caixa.
* `perfil_investidor.json`: Metas e tolerância a risco.
* `produtos_financeiros.json`: Catálogo de ativos disponíveis.
* `historico_atendimento.csv`: Contexto de interações prévias.

## 🧠 3. Engenharia de Prompts
A lógica do VIGI é regida por um **System Prompt** rigoroso:
* **Estratégia:** *Few-Shot Prompting* para garantir respostas precisas.
* **Segurança:** Bloqueio de recomendações fora da base de dados e negação de alucinações sobre taxas de juros não listadas.

## 💻 4. Implementação Técnica (Aplicação Funcional)
Devido a instabilidades de servidores externos, a aplicação foi migrada para uma solução **Nativa do Google Colab**:
* **Interface:** `ipywidgets` para garantir estabilidade e renderização imediata.
* **Modelo:** Integração via Google Generative AI (Gemini API).
* **Ambiente:** Desenvolvimento em nuvem focado em portabilidade.

## 📊 5. Avaliação e Métricas
O VIGI foi testado sob três pilares:
1.  **Assertividade:** Precisão no cálculo de gastos por categoria.
2.  **Segurança:** Recusa de perguntas fora do escopo financeiro.
3.  **Coerência:** Recomendações alinhadas ao perfil de investidor do usuário.

## 🎤 6. Pitch e Demonstração
A solução final inclui uma demonstração em vídeo (Pitch) de até 3 minutos, cobrindo o problema, a solução técnica, a demo funcional e o diferencial de segurança do VIGI.

---
*Este projeto foi desenvolvido como parte do desafio técnico para o setor financeiro, aplicando conceitos de IA Generativa e Análise de Dados.*
