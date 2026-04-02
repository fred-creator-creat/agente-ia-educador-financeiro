# 🛡️ VIGI - Vigilante Financeiro Inteligente (GenAI)

> **Projeto Final desenvolvido para o Bootcamp Bradesco - GenAI & Dados em parceria com a [DIO](https://www.dio.me/).**

O **VIGI** é um agente de inteligência artificial proativo, focado em proteção patrimonial e consultoria financeira personalizada. Diferente de chatbots reativos, o VIGI analisa dados históricos para antecipar necessidades e garantir a segurança financeira do usuário.

---

## 👨‍💻 Desenvolvedor e Contexto Técnico

**Fred Cavalheiro**
* 🔄 **Em transição de carreira:** De Vigilante para a área de Tecnologia.
* 🎓 **Técnico em Desenvolvimento de Sistemas** (Senac).
* 📚 **Foco Atual:** Machine Learning, IA Generativa e Análise de Dados.
* 🔗 **[Conecte-se comigo no LinkedIn](https://www.linkedin.com/in/fred-cavalheiro/)**

### 💻 Notas de Hardware e Adaptação (Resiliência Técnica)
Este projeto foi desenvolvido sob condições rigorosas de hardware. Utilizando um **notebook emprestado** com limitações de processamento e RAM, adotei uma estratégia **Cloud-Native**:
- **Ambiente:** Todo o desenvolvimento e execução ocorrem no [Google Colab](https://colab.research.google.com/), eliminando a dependência de hardware local.
- **Interface:** Substituí ferramentas pesadas (como Streamlit/Gradio) pelo [ipywidgets](https://ipywidgets.readthedocs.io/), garantindo uma interface estável, leve e funcional diretamente no navegador.

---

## 🚀 O Projeto VIGI

### 1. Caso de Uso
O VIGI resolve o problema da fragmentação de dados financeiros, oferecendo:
- **Análise de Gastos:** Identificação automática de categorias (Ex: transporte, lazer).
- **Reserva de Emergência:** Cálculo em tempo real da saúde financeira.
- **Perfil de Investidor:** Sugestões baseadas no perfil de risco do usuário (`JSON`).

### 2. Arquitetura e Tecnologias
O fluxo de dados foi desenhado para ser anti-alucinação, utilizando **RAG (Retrieval-Augmented Generation)** simplificado:

| Categoria | Ferramenta Utilizada |
| :--- | :--- |
| **LLM** | [Google Gemini 2.5 Flash](https://ai.google.dev/models/gemini) |
| **Linguagem** | [Python 3.x](https://docs.python.org/3/) |
| **Manipulação de Dados** | [Pandas](https://pandas.pydata.org/) |
| **Interface de Usuário** | [ipywidgets](https://ipywidgets.readthedocs.io/) |
| **Diagramação** | [Mermaid.js](https://mermaid.js.org/) |

---

## 📁 Estrutura do Repositório

* 📂 [**`data/`**](./data): Base de conhecimento com arquivos `CSV` (Transações) e `JSON` (Perfil e Produtos).
* 📂 [**`docs/`**](./docs): Documentação completa, incluindo Engenharia de Prompts e Métricas.
* 📂 [**`src/`**](./src): Código-fonte da aplicação otimizado para Google Colab.
* 📂 [**`examples/`**](./examples): Exemplos de perguntas e respostas do agente.

---

## 🛠️ Como Executar

1.  Acesse o projeto via **Google Colab**.
2.  Configure sua `GOOGLE_API_KEY` nos Secrets do ambiente.
3.  Execute as células em ordem para carregar a base de dados em `data/` e inicializar a interface [**`ipywidgets`**](https://ipywidgets.readthedocs.io/).

---

## 📊 Avaliação e Segurança
O VIGI utiliza **System Prompts** rigorosos para garantir que as respostas sejam baseadas apenas nos dados fornecidos, evitando alucinações sobre saldo ou produtos não disponíveis no catálogo do cliente.

---
> "Transformando limitações técnicas em soluções de engenharia eficientes."
