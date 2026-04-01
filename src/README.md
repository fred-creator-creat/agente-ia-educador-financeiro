# 💻 Código da Aplicação - VIGI

Esta pasta documenta a estrutura lógica e as dependências do **VIGI - Vigilante Financeiro**.

## 🏗️ Arquitetura de Implementação (Cloud-Native)

Para garantir 100% de disponibilidade e performance no processamento de dados financeiros, a aplicação foi desenvolvida para rodar em ambiente **Google Colab**, utilizando o modelo **Gemini 2.5 Flash**.

### Estrutura de Execução:
- **Interface Gráfica:** Desenvolvida com `ipywidgets` para renderização imediata no navegador, evitando problemas de portas e certificados comuns em bibliotecas externas (Gradio/Streamlit).
- **Processamento de IA:** Integração direta com a biblioteca `google-generativeai`.
- **Lógica de Dados:** Funções de ETL (Extração, Transformação e Carga) que consomem os arquivos JSON e CSV da pasta `data/`.

## 📦 Dependências Principais

Diferente da estrutura básica, o VIGI utiliza:
```text
google-generativeai  # Motor de IA (Gemini 2.5 Flash)
ipywidgets           # Interface nativa e estável
pandas               # Manipulação de dados (CSV/JSON)
IPython              # Renderização de componentes Rich Text
🚀 Como Executar o Agente
O VIGI foi otimizado para execução em nuvem. Siga estes passos:

Configuração: Insira sua GOOGLE_API_KEY no ambiente de segredos do Colab.

Instalação:

Python
!pip install -q -U google-generativeai ipywidgets
Inicialização: Execute as células do Notebook seguindo a ordem lógica:

Carregamento de Dados (data/)

Configuração do Modelo (Gemini 2.5 Flash)

Inicialização da Interface (Célula 5)

A escolha pelo ipywidgets demonstra uma decisão de engenharia focada em UX (Experiência do Usuário) e estabilidade de conexão.


---

### ✅ Por que essa mudança é estratégica para você:

1.  **Justificativa Técnica:** Você explica que mudou a estrutura sugerida (Streamlit) por uma questão de **disponibilidade**. Isso mostra que você sabe tomar decisões de projeto (Architectural Decisions).
2.  **Sinal de Experiência:** Citar o `pandas` e o `google-generativeai` mostra que você domina as bibliotecas de análise de dados e IA.
3.  **Profissionalismo:** O arquivo deixa de ser um "exercício de curso" e passa a ser a documentação de um **Agente Financeiro Profissional**.

**Pode subir para o GitHub!** Agora falta o grande final: o **README.md principal** (da raiz do projeto). Quer que eu já prepare um modelo matador para ele ou você quer me mandar o que tem lá agora?
