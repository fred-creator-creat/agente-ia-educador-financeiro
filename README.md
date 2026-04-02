# 🤖 VIGI - Vigilante Financeiro Inteligente (GenAI)

## 📌 Contexto e Propósito
O **VIGI** é um agente financeiro proativo desenvolvido para transformar a gestão de patrimônio. Enquanto assistentes comuns apenas respondem dúvidas, o VIGI utiliza IA Generativa para:

- **Antecipar riscos** financeiros analisando padrões de gastos.
- **Personalizar** estratégias de investimento baseadas no perfil real do cliente.
- **Cocriar** planos de reserva de emergência de forma consultiva.
- **Garantir segurança** total através de prompts anti-alucinação.

> [!IMPORTANT]
> **Nota de Resiliência Técnica:** Este projeto foi desenvolvido em um **notebook emprestado** com limitações de hardware (RAM/Processamento). Para superar esse desafio, adotei uma arquitetura **Cloud-Native** via [Google Colab](https://colab.research.google.com/), garantindo performance máxima sem depender de recursos locais.

---

## 👨‍💻 Desenvolvedor e Contexto Técnico

**Fred Cavalheiro**
* 🔄 **Em transição de carreira:** De Vigilante Profissional para a área de Tecnologia.
* 🎓 **Técnico em Desenvolvimento de Sistemas** (Formado pelo Senac).
* 📚 **Bolsista:** Bootcamp [Bradesco](https://www.bradesco.com.br/) - GenAI & Dados em parceria com a [DIO](https://www.dio.me/).
* 🎯 **Foco Atual:** Machine Learning, IA Generativa (LLMs) e Análise de Dados (Python, Neo4j, Power BI e Execel).
* 🔗 **[Conecte-se comigo no LinkedIn](https://www.linkedin.com/in/fred-cavalheiro/)**

---

## 🏗️ O Que Foi Entregue

### 1. Documentação e Estratégia
O VIGI atua como um consultor de proteção patrimonial. O fluxo de dados garante que a IA não "invente" saldos, baseando-se estritamente na base de conhecimento.

| Documento | Descrição |
|-----------|-----------|
| 📄 [**Documentação do Agente**](./docs/01-documentacao-agente.md) | Caso de uso, Persona e Arquitetura do VIGI. |
| 📄 [**Prompts do Agente**](./docs/03-prompts.md) | Engenharia de Prompts e tratamento de Edge Cases. |
| 📄 [**Avaliação e Métricas**](./docs/04-metricas.md) | Testes de assertividade e taxa de alucinação zero. |

### 2. Base de Conhecimento (RAG)
Utilizamos dados estruturados para alimentar a inteligência do agente:

| Arquivo | Formato | Função no VIGI |
|---------|---------|----------------|
| `transacoes.csv` | [CSV](data/transacoes.csv) | Histórico de movimentações para análise de padrões de gastos. |
| `perfil_investidor.json` | [JSON](data/perfil_investidor.json) | Define o apetite a risco, metas e tolerância do usuário. |
| `produtos_financeiros.json` | [JSON](data/produtos_financeiros.json) | Catálogo oficial de soluções e investimentos disponíveis. |
| `historico_atendimento.csv` | [CSV](data/historico_atendimento.csv) | Contexto de interações passadas para um atendimento contínuo. |

---

## 🛠️ Ferramentas e Decisões de Engenharia

| Categoria | Ferramenta | Justificativa Técnica |
|-----------|------------|-----------------------|
| **LLM** | [Gemini 2.5 Flash](https://ai.google.dev/models/gemini) | Escolhido pela alta velocidade e janela de contexto eficiente. |
| **Desenvolvimento** | [Google Colab](https://colab.research.google.com/) | Viabilizou o projeto em hardware limitado via nuvem. |
| **Interface** | [ipywidgets](https://ipywidgets.readthedocs.io/) | Substituiu o Streamlit para garantir estabilidade e UX no navegador. |
| **Orquestração** | **Integração Direta** | Optamos por não usar LangChain para economizar memória RAM local. |
| **Diagramas** | [Mermaid.js](https://mermaid.js.org/) | Fluxogramas dinâmicos renderizados diretamente no GitHub. |

---

## 🚀 Como Executar o Protótipo

1.  **Acesse o código:** Navegue até a pasta [`src/`](./src/) e abra o notebook no Google Colab.
2.  **Chave de API:** Configure sua `GOOGLE_API_KEY` nos segredos do ambiente Colab.
3.  **Instalação:**
    ```python
    !pip install -q -U google-generativeai ipywidgets
    ```
4.  **Fluxo:** Carregue os dados da pasta [`data/`](./data/) e execute a interface de chat.

---

## 📁 Estrutura do Repositório

```text
📁 lab-agente-financeiro-vigi/
│
├── 📄 README.md (Este arquivo)
├── 📁 data/           # Bases CSV/JSON clicáveis
├── 📁 docs/           # Documentação técnica detalhada
├── 📁 src/            # Código-fonte otimizado (Colab + ipywidgets)
└── 📁 examples/       # Exemplos de interações reais do VIGI
```

---

[!TIP]
Dica de Avaliação: O VIGI brilha em cenários de "limite", onde o cliente tenta forçar uma recomendação de risco alto sendo conservador. O sistema de segurança bloqueia e orienta conforme o perfil.
