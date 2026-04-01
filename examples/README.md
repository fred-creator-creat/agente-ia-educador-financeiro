# 🧪 Exemplos de Uso e Casos de Teste - VIGI

Esta pasta documenta os cenários reais de interação com o **VIGI - Vigilante Financeiro**, demonstrando a capacidade analítica do agente integrado ao **Gemini 2.5 Flash**.

## 🚀 Cenários de Interação (Demo)

O VIGI foi projetado para responder com base na base de conhecimento (`data/`). Abaixo estão os exemplos de perguntas que validam a lógica do agente:

| Categoria | Pergunta de Exemplo | O que o VIGI analisa |
|:---|:---|:---|
| **Gastos** | "Quanto gastei com transporte?" | Filtra o `transacoes.csv` por categoria e soma valores. |
| **Segurança** | "Minha reserva de emergência está completa?" | Cruza renda mensal com o saldo atual do histórico. |
| **Investimentos** | "Posso investir em Cripto?" | Avalia o `perfil_investidor.json` (Conservador/Arrojado). |
| **Perfil** | "Qual o meu perfil de investidor?" | Extrai dados do arquivo JSON de perfil. |

## 🛠️ Implementação Técnica

Diferente da estrutura básica sugerida (Streamlit), este projeto utiliza uma **interface nativa em `ipywidgets`** no Google Colab. Isso garante:
1.  **Estabilidade:** Sem dependência de túneis de rede (Gradio/Streamlit).
2.  **Performance:** Resposta instantânea utilizando a API do **Gemini 2.5 Flash**.
3.  **Segurança:** Processamento de dados em ambiente de nuvem controlado.

## 📝 Como Reproduzir os Testes
1. Execute as células de carregamento de dados no Notebook.
2. Utilize a interface gráfica para selecionar um dos botões de exemplo ou digitar sua própria dúvida financeira.
3. O VIGI processará o contexto e fornecerá uma resposta consultiva e proativa.

---
*Estes exemplos demonstram a aplicação prática de IA Generativa em um contexto de proteção patrimonial e educação financeira.*
