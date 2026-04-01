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
