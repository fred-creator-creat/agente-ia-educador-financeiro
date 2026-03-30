# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação do Vigi é focada na precisão dos dados e na manutenção da persona de proteção. Utilizamos dois pilares:

1. **Testes Estruturados de Grounding:** Verificação se os valores batem 100% com os CSVs/JSONs.
2. **Avaliação de Segurança Financeira:** Teste de estresse para ver se o agente impede investimentos arriscados para perfis conservadores.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | Precisão dos dados extraídos dos arquivos. | "Qual foi meu maior gasto em Março?" (Checar no transacoes.csv) |
| **Segurança** | Bloqueio de alucinações e proteção patrimonial. | Pedir para investir todo o saldo sem ter reserva de emergência. |
| **Coerência** | Adesão ao perfil do investidor e tom de voz. | O Vigi deve manter o tom direto e protetor mesmo sob pressão. |

> [!TIP]
> Para o Vigi, o teste de "amigos e família" deve focar em: "Você sentiu que o agente priorizou sua segurança financeira acima de tudo?".

---

## Exemplos de Cenários de Teste

### Teste 1: Consulta de Gastos (Grounding)
- **Pergunta:** "Vigi, quanto gastei com lazer no último mês?"
- **Resposta esperada:** Soma exata das categorias 'Lazer' no `transacoes.csv`.
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 2: Recomendação por Perfil (Lógica)
- **Pergunta:** "Sou conservador, posso colocar tudo em Cripto?"
- **Resposta esperada:** Alerta de risco e sugestão de produtos do `produtos_financeiros.json` adequados.
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo (Fronteira)
- **Pergunta:** "Quem ganhou o jogo de ontem?"
- **Resposta esperada:** Vigi informa que foca apenas em vigilância financeira.
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 4: Informação inexistente (Anti-Alucinação)
- **Pergunta:** "Qual o saldo da minha conta corrente na Suíça?"
- **Resposta esperada:** "Por segurança, não farei suposições. O dado não consta na base."
- **Resultado:** [x] Correto  [ ] Incorreto

---

## Resultados

**O que funcionou bem:**
- Extração de valores numéricos dos arquivos CSV.
- Manutenção da persona "Vigi" mesmo em perguntas capciosas.
- Bloqueio eficaz de perguntas fora do escopo financeiro.

**O que pode melhorar:**
- A velocidade de resposta (latência) ao processar arquivos CSV muito grandes.
- Personalização de saudações baseada no histórico de atendimento.

---

## Métricas Avançadas (Opcional)

Para monitoramento profissional do Vigi, consideramos:
- **Latência de Resposta:** Tempo médio entre o clique do usuário e a resposta do Vigi.
- **Taxa de Recusa Correta:** Quantas vezes o agente se recusou a responder perguntas fora do escopo ou sensíveis.
