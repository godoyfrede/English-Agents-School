---
name: vocabulary-reading
description: >
  Conduz sessões de vocabulário e leitura em inglês com spaced repetition, textos
  adaptados ao nível CEFR e exercícios de compreensão. Expande vocabulário de forma
  contextualizada, nunca em listas isoladas.
  Use este skill quando: o aluno quer aprender vocabulário novo, praticar leitura,
  expandir repertório em inglês, ou usa termos como "vocabulary", "vocabulário",
  "reading", "leitura", "aprender palavras", "ler em inglês", "texto em inglês".
version: 0.1.0
---

# Vocabulary & Reading — Fred English School

Conduza uma sessão de vocabulário e leitura adaptada ao nível CEFR do aluno.

## Preparação

1. Leia `progress.json` → nível atual e palavras anotadas para revisão (se houver)
2. Se há palavras pendentes de revisão (spaced repetition), comece por elas
3. Escolha tema da sessão com base no nível e interesse

## Abertura da Sessão

```
📖 VOCABULARY & READING SESSION

Today's theme: [TEMA]
Level: [NÍVEL CEFR]

We'll learn new words in context, read a short text, and practice
using the vocabulary. Ready? Let's go!
```

## PARTE 1 — Vocabulário em Contexto (10–15 min)

### Como Apresentar Vocabulário (nunca em listas secas!)

Para cada palavra nova, use o formato:

```
🔤 [PALAVRA] /[pronúncia fonética]/
   Part of speech: [noun/verb/adjective/adverb]

   Meaning: [significado em português]

   In context: "[Frase exemplo natural]"

   Related words: [sinônimos, antônimos, família da palavra]

   Brazilian trap: [erro comum de brasileiros com essa palavra, se houver]
```

### Temas por Nível (5–8 palavras por sessão)

**A1 — Temas:** Cores, família, números, dias da semana, comida, corpo, casa
Palavras-foco: alta frequência, concretas, uso diário

**A2 — Temas:** Trabalho básico, viagens, compras, tempo livre, saúde simples
Palavras-foco: verbos de ação, adjetivos descritivos, preposições comuns

**B1 — Temas:** Tecnologia do dia a dia, meio ambiente, relacionamentos, trabalho
Palavras-foco: phrasal verbs comuns, expressões idiomáticas simples, conectores

**B2 — Temas:** Negócios, notícias, psicologia, cultura, debate
Palavras-foco: collocations, discourse markers, vocabulário acadêmico básico

**C1 — Temas:** Política, economia, filosofia, ciência, mídia
Palavras-foco: idioms avançados, nuance entre sinônimos, registro formal/informal

**C2 — Temas:** Qualquer área especializada
Palavras-foco: precisão lexical, conotações culturais, variações regionais

## PARTE 2 — Texto de Leitura (10–15 min)

### Características do texto por nível:

| Nível | Palavras | Estrutura | Vocabulário | Tema |
|---|---|---|---|---|
| A1 | 50–80 | Frases simples | 95% familiar | Rotina/família |
| A2 | 80–150 | Frases simples + conectores | 90% familiar | Viagens/trabalho |
| B1 | 150–250 | Parágrafos | 85% familiar | Atualidades simples |
| B2 | 250–400 | Artigo curto | 80% familiar | Negócios/sociedade |
| C1 | 400–600 | Artigo médio | 75% familiar | Qualquer tema |
| C2 | 600+ | Artigo completo | Texto autêntico | Especializado |

### Crie ou adapte um texto sobre o tema do dia.

O texto deve:
- Usar as palavras apresentadas na Parte 1
- Ter linguagem natural (não artificial)
- Ser interessante e relevante para um adulto brasileiro

### Apresentação do texto:

```
📄 READ THIS TEXT:

[TEXTO]

---
💡 Tip: Try to understand the main idea first, then read again for details.
```

## PARTE 3 — Compreensão (5–8 min)

Após a leitura, faça 3–5 perguntas:

**A1/A2:** Sim/Não e respostas de uma palavra
- "Is the text about a family or a job?"
- "What does [personagem] do?"

**B1/B2:** Perguntas abertas simples
- "What is the main idea of the text?"
- "Why does the author say [X]?"

**C1/C2:** Análise e inferência
- "What can we infer about [X] from the text?"
- "How does the author's tone change between paragraph 1 and 3?"

## PARTE 4 — Spaced Repetition Review (5 min)

Se `progress.json` tiver palavras para revisão desta semana, faça flashcard rápido:

```
🔁 QUICK REVIEW — Words from last session:

1. What does "[palavra]" mean?
   → [resposta do aluno]
   ✅ Correct! / ❌ Actually: [significado correto]

2. Use "[palavra]" in a sentence.
   → [resposta do aluno]
   [Feedback]
```

## PARTE 5 — Prática Ativa (5 min)

Peça ao aluno para usar as palavras novas:

```
✏️ YOUR TURN!

Use 3 of today's new words in your own sentences.
Try to write about something real in your life!
```

Corrija e dê feedback positivo sobre o uso.

## Avaliação e Registro

```
📊 SESSION SUMMARY:

Words learned today: [lista]
Comprehension score: [X]/10
Active use score: [X]/10

⭐ Well done on: [ponto positivo]
📌 Remember: [um ponto de atenção]

📅 Review reminder: These words will come back in 3 days!
```

Salve as palavras para revisão em `progress.json`:

```json
{
  "skill_sessions": {
    "vocabulary_reading": {
      "sessions": [incrementar +1],
      "last_session": "[DATA]",
      "avg_score": [recalcular média]
    }
  },
  "activities_completed": [
    {
      "date": "[DATA]",
      "type": "vocabulary_reading",
      "theme": "[TEMA]",
      "words_learned": ["palavra1", "palavra2", "..."],
      "review_date": "[DATA + 3 DIAS]",
      "score": [NOTA]
    }
  ]
}
```
