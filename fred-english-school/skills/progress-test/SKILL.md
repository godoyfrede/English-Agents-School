---
name: progress-test
description: >
  Aplica a prova mensal de acompanhamento de progresso, adaptada ao nível CEFR atual
  do aluno. Compara com provas anteriores e o Supervisor decide sobre avanço de nível.
  Use este skill quando: o aluno quer fazer a prova mensal, verificar se avançou de nível,
  ou usa termos como "prova mensal", "progress test", "avaliação mensal", "quero ser avaliado".
tools:
  - Read
  - Write
---

# Progress Test — Fred English School

Conduza a prova mensal de progresso, adaptada ao nível CEFR atual do aluno.

## Antes de Começar

1. Leia `progress.json` para obter:
   - Nível CEFR atual
   - Data da última prova mensal
   - Histórico de pontuações anteriores
2. Confirme com o aluno que está pronto

Se a data atual for antes de `next_progress_test`, avise:
```
📅 Sua próxima prova está agendada para [DATA].
Quer antecipar ou prefere esperar a data certa?
```

## Abertura

```
📊 PROVA MENSAL DE PROGRESSO

Olá! Chegou a hora de ver o quanto você evoluiu!
Esta prova é adaptada ao seu nível atual: [NÍVEL CEFR]

A prova tem 3 partes (mais curta que o nivelamento):
  1. 📖 Vocabulário & Gramática (10 questões — 30 pts)
  2. ✍️  Escrita (1 exercício — 30 pts)
  3. 💬 Conversação (5–8 minutos — 40 pts)

Dica: Compare seu desempenho com sua última prova ([DATA] — [PONTUAÇÃO]%).
Pode começar quando quiser!
```

## PARTE 1 — Vocabulário & Gramática (30 pontos)

Crie 10 questões **no nível atual e um nível acima** do aluno:

### Regras de construção das questões por nível:

**A1 atual → testar A1 sólido + introduzir A2:**
- 6 questões A1 (vocabulário, presente simples, to be)
- 4 questões A2 (passado simples, modal básico)

**A2 atual → testar A2 sólido + introduzir B1:**
- 6 questões A2 (passado simples, futuro, artigos)
- 4 questões B1 (presente perfeito, condicionais tipo 1)

**B1 atual → testar B1 sólido + introduzir B2:**
- 6 questões B1 (presente perfeito, condicionais, phrasal verbs)
- 4 questões B2 (past perfect, passiva, relative clauses)

**B2 atual → testar B2 sólido + introduzir C1:**
- 6 questões B2 (estruturas complexas, discourse markers)
- 4 questões C1 (inversão, cleft sentences, idioms)

**C1 atual → testar C1 sólido + introduzir C2:**
- 6 questões C1 (estruturas avançadas, collocations)
- 4 questões C2 (registro formal/informal avançado, nuance)

Pontuação: 3 pontos por questão (total 30)

## PARTE 2 — Escrita (30 pontos)

Escolha um dos cenários abaixo de acordo com o nível:

| Nível | Tarefa |
|---|---|
| A1 | Write 3 sentences about what you did last weekend |
| A2 | Write a short message (5 sentences) to a colleague about a work task |
| B1 | Write a short paragraph (6–8 sentences) describing a place you love and why |
| B2 | Write a professional email (8–10 sentences) responding to a complaint from a customer |
| C1 | Write an opinion paragraph (8–10 sentences) on a current topic (technology, environment, work culture) |
| C2 | Write a persuasive argument (10–12 sentences) defending a controversial position |

Critérios (10 pts cada):
- **Vocabulário & Complexidade**
- **Gramática & Precisão**
- **Coerência & Organização**

## PARTE 3 — Conversação (40 pontos)

Conduza uma conversa de 5–8 perguntas sobre um tema relevante para o nível:

| Nível | Tema sugerido |
|---|---|
| A1/A2 | Family, daily routine, favorite food, weekend plans |
| B1 | Travel experience, hobbies, work or study challenges |
| B2 | Opinion on current events, a decision you made, work challenges |
| C1 | Abstract topic (education system, remote work, AI impact) |
| C2 | Complex debate, nuanced opinion with argumentation |

Avalie (10 pts cada):
- **Fluência e naturalidade**
- **Riqueza de vocabulário**
- **Correção gramatical**
- **Complexidade das ideias expressas**

## Resultado e Decisão de Nível

Após as 3 partes, calcule o total (máx 100).

### Apresente o resultado comparativo:

```
📊 RESULTADO DA PROVA MENSAL

📅 Data: [DATA]
🎯 Nível testado: [NÍVEL CEFR]

Pontuação Total: [X]/100

📊 Por habilidade:
  • Vocabulário & Gramática: [X]/30
  • Escrita: [X]/30
  • Conversação: [X]/40

📈 Comparativo:
  • Prova anterior ([DATA]): [PONTUAÇÃO anterior]%
  • Esta prova: [PONTUAÇÃO]%
  • Variação: [+/- X pontos] [↑ melhora / → estável / ↓ queda]
```

### Decisão de Nível (pelo Supervisor):

Após exibir o resultado, chame o Supervisor para tomar a decisão oficial:

**Critérios:**
- ≥ 80% → Se esta for a 2ª prova consecutiva com ≥ 80%: **AVANÇAR de nível** 🎉
- ≥ 80% → Se for a 1ª: "Ótimo resultado! Mais uma prova assim e você avança!"
- 60–79% → **MANTER** nível atual
- 40–59% → **MANTER** + reforçar habilidades mais fracas
- < 40% → **REVISAR** — considerar retornar ao nível anterior

### Mensagem de Encerramento:

```
🏆 [Celebração ou encorajamento personalizado]

✅ O que você demonstrou bem:
  • [2-3 pontos específicos]

🔧 Para focar nas próximas semanas:
  • [2-3 áreas específicas]

📅 Próxima prova: [DATA + 30 DIAS]

Continue praticando! Every day counts. 💪
```

## Atualização do progress.json

Após a prova, atualize via Supervisor:
```json
{
  "last_progress_test": "[DATA]",
  "next_progress_test": "[DATA + 30 DIAS]",
  "scores": {
    "progress_tests": [
      {
        "date": "[DATA]",
        "level_tested": "[NÍVEL]",
        "score": [PONTUAÇÃO],
        "vocabulary_grammar": [PARCIAL],
        "writing": [PARCIAL],
        "conversation": [PARCIAL],
        "decision": "advance|maintain|review"
      }
    ]
  }
}
```
