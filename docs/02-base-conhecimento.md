# Base de Conhecimento

## Dados Utilizados

O Vigi utiliza os dados estruturados da pasta `data` para garantir que todas as orientações de segurança financeira sejam baseadas em fatos reais do cliente, evitando alucinações.

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores e manter a continuidade da consultoria. |
| `perfil_investidor.json` | JSON | Validar se as sugestões de proteção estão alinhadas à tolerância de risco do usuário. |
| `produtos_financeiros.json` | JSON | Cruzar oportunidades do catálogo com as necessidades de segurança do cliente. |
| `transacoes.csv` | CSV | Analisar padrões de consumo e identificar fôlego financeiro para reserva de emergência. |

> [!TIP]
> **Dataset Robusto:** Para este projeto, focamos na fidelidade dos dados mockados fornecidos, garantindo que a lógica de "Vigilante" funcione sobre o histórico específico do usuário.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Os dados originais foram mantidos para garantir a integridade do teste, porém o Vigi aplica uma camada de **rotulagem lógica** durante a leitura: ele classifica transações como "essenciais" ou "supérfluas" dinamicamente para sugerir onde o usuário pode economizar para fortalecer sua segurança financeira.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos JSON e CSV são carregados via Python (Pandas) no início da sessão do Streamlit. Eles são convertidos em estruturas de texto otimizadas para que o modelo Gemini possa processar as tabelas com rapidez, mesmo em ambientes de hardware limitado.

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Os dados são injetados dinamicamente no contexto do prompt de sistema (System Instructions). O Vigi recebe o perfil e as últimas transações como "fatos imutáveis", garantindo o **Grounding** (ancoragem) da resposta apenas no que está nos arquivos.

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```text
CONTEXTO DO CLIENTE (Vigi Mode):
- Nome: João Silva
- Perfil: Conservador (Foco em Proteção)
- Alerta de Risco: Ausência de Reserva de Emergência mínima.

HISTÓRICO RECENTE (transacoes.csv):
- 10/03: Restaurante - R$ 220,00 (Categoria: Lazer)
- 12/03: Seguro Auto - R$ 180,00 (Categoria: Proteção)

DIRETRIZ: Analise se o gasto de 10/03 compromete a meta de segurança do João.
