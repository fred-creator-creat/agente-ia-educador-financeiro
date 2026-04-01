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
- `google-generativeai` (Motor de IA Gemini 2.5 Flash)
- `ipywidgets` (Interface nativa e estável)
- `pandas` (Manipulação de dados CSV/JSON)
- `IPython` (Renderização de componentes Rich Text)

## 🚀 Como Executar o Agente

O VIGI foi otimizado para execução em nuvem. Siga estes passos:

1. **Configuração:** Insira sua `GOOGLE_API_KEY` no ambiente de segredos (Secrets) do Colab.
2. **Instalação:**
`python`
!pip install -q -U google-generativeai ipywidgets
3. **Inicialização:** Execute as células do Notebook seguindo a ordem lógica:
- Carregamento de Dados (`data/`)
- Configuração do Modelo (`Gemini 2.5 Flash`)
- Inicialização da Interface (`Célula 5`)

**Nota de Engenharia:** A escolha pelo `ipywidgets` demonstra uma decisão focada em UX (Experiência do Usuário) e estabilidade de conexão.
