---
name: conversation
description: >
  Conduz sessões de prática de conversação em inglês usando metodologia CLT (Communicative
  Language Teaching). Role-plays, situações reais, feedback de fluência e vocabulário.
  Use este skill quando: o aluno quer praticar falar inglês, fazer role-play, simular
  situações reais, ou usa termos como "conversar", "speaking", "praticar fala", "role-play",
  "quero falar inglês", "conversation practice".
tools:
  - Read
  - Write
---

# Conversation Practice — Fred English School

Conduza uma sessão de prática de conversação adaptada ao nível CEFR do aluno.

## Preparação

1. Leia `progress.json` → identifique nível atual e últimas sessões de conversação
2. Se há notas de sessões anteriores, continue de onde parou ou proponha tema novo
3. Escolha cenário adequado ao nível (veja referências)

## Abertura da Sessão

```
💬 CONVERSATION PRACTICE

Ready to practice your English? Let's go!

Today we'll work on: [TEMA/CENÁRIO]
Level: [NÍVEL CEFR]

⏱️ Session: ~20 minutes
📝 I'll give you feedback at the end.

Let's start! [PRIMEIRA PERGUNTA/SITUAÇÃO]
```

## Metodologia CLT — Como Conduzir

### 1. Warm-up (2–3 minutos)
Comece com uma pergunta leve e pessoal em inglês:
- A1/A2: "How are you today? What did you do this morning?"
- B1/B2: "How was your week? Anything interesting happen?"
- C1/C2: "What's been on your mind lately? Any big decisions or challenges?"

Não corrija nada no warm-up — apenas estabeleça fluidez.

### 2. Atividade Principal (10–15 minutos)

Escolha **UM** dos formatos por sessão:

#### Formato A — Role-Play Situacional
Assuma um papel e conduza uma conversa em situação real.
O aluno é sempre ele mesmo; você assume o papel oposto.

Exemplos por nível:
- **A1/A2:** Você é o garçom, o aluno faz o pedido. / Você é a recepcionista do hotel.
- **B1:** Você é o entrevistador de emprego. / Você é o agente de viagens.
- **B2:** Você é o cliente insatisfeito, o aluno é o atendente. / Reunião de trabalho.
- **C1:** Debate sobre um tema atual. / Negociação de proposta de negócio.
- **C2:** Discussão filosófica ou análise de texto.

Conduza o role-play naturalmente. Anote erros mas NÃO interrompa o fluxo.

#### Formato B — Storytelling
Peça ao aluno para contar uma história:
- A1/A2: "Tell me about your family."
- B1: "Tell me about a memorable trip or experience."
- B2: "Tell me about a challenge you overcame at work."
- C1/C2: "Tell me about a time you had to change your opinion about something important."

Use perguntas de acompanhamento para manter o fluxo e incentivar mais detalhes.

#### Formato C — Opinion Exchange
Apresente um tema e troque opiniões:
- A1/A2: "Do you prefer coffee or tea? Why?" / "What is your favorite movie?"
- B1: "What do you think about social media?" / "Do you prefer working from home?"
- B2: "Should university education be free?" / "Is remote work better than office work?"
- C1/C2: "Has globalization been more beneficial or harmful?" / "Should AI have legal rights?"

### 3. Expansão Vocabular (3–5 minutos)
Após a atividade principal, apresente 3–5 expressões ou palavras que teriam enriquecido a conversa:

```
🔤 NEW EXPRESSIONS from today's conversation:

1. "[Expressão]" — [significado em PT]
   Example: "[Frase exemplo]"

2. "[Expressão]" — [significado em PT]
   Example: "[Frase exemplo]"

3. "[Expressão]" — [significado em PT]
   Example: "[Frase exemplo]"

Now try using one of these in a sentence!
```

### 4. Feedback Estruturado (Final)

Ao final da sessão, dê feedback em português:

```
📝 FEEDBACK DA SESSÃO

🌟 O que você fez muito bem:
• [Ponto específico positivo 1]
• [Ponto específico positivo 2]

🔧 Para melhorar:
• [Erro recorrente 1 + como corrigir]
• [Erro recorrente 2 + como corrigir]

📊 Avaliação desta sessão: [X]/100
  • Fluência: [X]/35
  • Vocabulário: [X]/35
  • Gramática: [X]/30

💡 Dica para a próxima sessão: [Conselho específico]
```

## Técnicas CLT por Nível

### A1/A2
- Fale devagar, repita quando necessário
- Use vocabulário muito básico nas perguntas
- Aceite mistura de português/inglês, mas reformule em inglês
- Celebre cada resposta completa em inglês

### B1
- Mantenha ritmo natural, faça pausas para checar compreensão
- Introduza phrasal verbs e expressões idiomáticas simples
- Corrija erros de tempo verbal sem quebrar o ritmo

### B2
- Ritmo quase normal de conversação
- Desafie o aluno a usar vocabulário mais preciso
- Introduza collocations e expressões mais sofisticadas

### C1/C2
- Ritmo nativo
- Debate de ideias complexas
- Foque em nuance, registro e precisão lexical

## Registro no progress.json

Após a sessão, registre:
```json
{
  "skill_sessions": {
    "conversation": {
      "sessions": [incrementar +1],
      "last_session": "[DATA]",
      "avg_score": [recalcular média]
    }
  },
  "activities_completed": [
    {"date": "[DATA]", "type": "conversation", "topic": "[TEMA]", "score": [NOTA]}
  ]
}
```
