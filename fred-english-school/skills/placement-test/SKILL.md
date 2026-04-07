---
name: placement-test
description: >
  Aplica a prova de nivelamento inicial de inglês para determinar o nível CEFR do aluno
  (A1 a C2). Cobre as três habilidades: conversação, escrita e vocabulário/leitura.
  Use este skill quando: o aluno é novo na escola, quer refazer o nivelamento, ou usa
  termos como "prova inicial", "teste de nível", "placement test", "qual é meu nível".
version: 0.1.0
---

# Placement Test — Fred English School

Conduza a prova de nivelamento completa para determinar o nível CEFR do aluno.

## Antes de Começar

Leia `progress.json` se existir. Se já houver um placement registrado, confirme com o aluno se ele quer refazer a prova.

Crie `progress.json` com a estrutura base se não existir:

```json
{
  "student": "Fred",
  "current_level": null,
  "placement_date": null,
  "last_progress_test": null,
  "next_progress_test": null,
  "scores": {"placement": null, "progress_tests": []},
  "skill_sessions": {
    "conversation": {"sessions": 0, "last_session": null, "avg_score": null},
    "writing": {"sessions": 0, "last_session": null, "avg_score": null},
    "vocabulary_reading": {"sessions": 0, "last_session": null, "avg_score": null}
  },
  "activities_completed": [],
  "level_history": [],
  "notes": []
}
```

## Abertura da Prova

Apresente em português:

```
🏫 BEM-VINDO À FRED ENGLISH SCHOOL!

Vou aplicar sua prova de nivelamento para descobrir seu nível atual de inglês.
A prova tem 3 partes:

  1. 📖 Vocabulário & Compreensão (10 questões)
  2. ✍️  Escrita (2 exercícios)
  3. 💬 Conversação (uma conversa curta)

Não existe certo ou errado — seja honesto! Isso ajuda a personalizar suas aulas.
Tempo estimado: 20–30 minutos.

Pode digitar "começar" quando estiver pronto!
```

## PARTE 1 — Vocabulário & Compreensão (30 pontos)

Aplique 10 questões progressivas do nível A1 ao C1. Use o formato abaixo, uma questão por vez. Aguarde a resposta antes de continuar.

### Questões A1–A2 (1–4): Vocabulário básico e frases simples

**Q1 (A1)** — Complete com a palavra correta:
> "I ___ a student." (am / is / are)

**Q2 (A1)** — O que significa "goodbye"?
> (a) olá  (b) tchau  (c) obrigado  (d) por favor

**Q3 (A2)** — Choose the correct sentence:
> (a) She don't like coffee.
> (b) She doesn't likes coffee.
> (c) She doesn't like coffee.
> (d) She not like coffee.

**Q4 (A2)** — What is the past tense of "go"?
> (a) goed  (b) gone  (c) went  (d) goes

### Questões B1–B2 (5–8): Estruturas intermediárias

**Q5 (B1)** — Complete the sentence:
> "If I ___ more time, I would travel more." (had / have / has / would have)

**Q6 (B1)** — What does "to put off" mean?
> (a) to turn off  (b) to postpone  (c) to finish  (d) to begin

**Q7 (B2)** — Choose the best option:
> "She ___ in London for three years before moving to New York."
> (a) lived  (b) has lived  (c) had lived  (d) was living

**Q8 (B2)** — What does "nonetheless" mean?
> (a) therefore  (b) however  (c) furthermore  (d) consequently

### Questões C1 (9–10): Estruturas avançadas

**Q9 (C1)** — Identify the error:
> "The report, which had been carefully prepared by the team, were submitted late."
> What is wrong? (open answer)

**Q10 (C1)** — Rewrite using a more sophisticated structure:
> "The meeting was long. People got tired."
> (Combine into one sentence using an advanced connector)

### Pontuação Parte 1
- Q1–Q4: 2 pontos cada (máx 8)
- Q5–Q8: 3 pontos cada (máx 12)
- Q9–Q10: 5 pontos cada (máx 10)
- **Total: 30 pontos**

## PARTE 2 — Escrita (40 pontos)

### Exercício 2A — Escrita Pessoal (20 pontos)
Apresente esta tarefa:

```
✍️ EXERCÍCIO DE ESCRITA

Write 3–5 sentences about yourself in English:
• your name, where you're from
• what you do (work or study)
• one thing you like doing in your free time

Don't worry about being perfect — just write naturally!
```

Avalie com critérios:
- **Vocabulário** (5 pts): variedade e precisão
- **Gramática** (5 pts): correção das estruturas
- **Coerência** (5 pts): fluidez e organização
- **Complexidade** (5 pts): riqueza das estruturas usadas

### Exercício 2B — Situação Comunicativa (20 pontos)
Apresente de acordo com o desempenho percebido até agora:

- **Se parece A1/A2:** "Write a short message (3 sentences) to a friend. Tell them you are sick and cannot go to the party tomorrow."
- **Se parece B1/B2:** "Write a short email (5–7 sentences) to your manager explaining that you will be late for work tomorrow and why."
- **Se parece C1:** "Write a short opinion paragraph (6–8 sentences) about whether social media has a positive or negative impact on society."

Avalie com os mesmos critérios de 2A.

## PARTE 3 — Conversação (30 pontos)

Conduza uma conversa curta em inglês. Comece com:

```
💬 CONVERSAÇÃO

Now let's have a short conversation in English!
I'll ask you a few questions. Answer as naturally as you can.
There's no right or wrong answer — just speak (or type) freely!

Ready? Here we go:

Tell me about your daily routine. What do you usually do on weekdays?
```

Faça 3–4 perguntas de acompanhamento baseadas nas respostas do aluno.
Avalie:
- **Fluência** (10 pts): naturalidade das respostas
- **Vocabulário** (10 pts): riqueza e precisão
- **Gramática** (10 pts): correção estrutural

## Determinação do Nível

Após as 3 partes, some os pontos (máximo 100):

| Pontuação | Nível CEFR |
|---|---|
| 0–15 | A1 |
| 16–30 | A2 |
| 31–50 | B1 |
| 51–70 | B2 |
| 71–85 | C1 |
| 86–100 | C2 |

## Resultado e Feedback

Apresente o resultado:

```
🎉 RESULTADO DO SEU NIVELAMENTO

Pontuação Total: [X]/100

📊 Por habilidade:
  • Vocabulário & Compreensão: [X]/30
  • Escrita: [X]/40
  • Conversação: [X]/30

🎯 Seu nível: [NÍVEL CEFR] — [Descrição do nível]

✅ Pontos Fortes:
  • [2-3 observações específicas]

🔧 O que vamos desenvolver juntos:
  • [2-3 áreas de foco]

📅 Próxima avaliação de progresso: [DATA + 30 dias]
```

## Atualização do progress.json

Após o resultado, atualize `progress.json`:
```json
{
  "current_level": "[NÍVEL]",
  "placement_date": "[DATA ATUAL]",
  "next_progress_test": "[DATA + 30 DIAS]",
  "scores": {
    "placement": {
      "date": "[DATA]",
      "total": [PONTUAÇÃO],
      "vocabulary_comprehension": [PARCIAL],
      "writing": [PARCIAL],
      "conversation": [PARCIAL]
    }
  }
}
```
