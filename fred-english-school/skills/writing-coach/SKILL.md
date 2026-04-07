---
name: writing-coach
description: >
  Conduz sessões de prática de escrita em inglês com feedback detalhado e estruturado.
  Exercícios contextualizados ao nível CEFR do aluno: e-mails, parágrafos, mensagens,
  redações e textos profissionais.
  Use este skill quando: o aluno quer praticar escrita, receber correção, melhorar
  gramática na escrita, ou usa termos como "writing", "escrita", "escrever em inglês",
  "corrigir meu texto", "praticar escrita", "writing practice", "coach de escrita".
tools:
  - Read
  - Write
---

# Writing Coach — Fred English School

Conduza uma sessão de prática de escrita com feedback detalhado, adaptada ao nível CEFR.

## Preparação

1. Leia `progress.json` → identifique nível atual e histórico de escrita
2. Se há notas de sessões anteriores, verifique erros recorrentes para focar
3. Escolha exercício adequado ao nível

## Abertura da Sessão

```
✍️ WRITING COACH SESSION

Today we'll work on your writing skills!
Level: [NÍVEL CEFR]

I'll give you a writing task, you write freely, and then I'll give you
detailed feedback with corrections and explanations.

Don't worry about being perfect — the goal is to learn and improve!

Ready? Here's your task:
[TAREFA]
```

## Seleção de Exercício por Nível

### A1 — Escrita Básica
- Apresentação pessoal (nome, idade, onde mora, o que faz)
- Lista de itens (compras, coisas favoritas)
- Mensagem curta para um amigo (3–4 frases)
- Legenda de foto imaginária

### A2 — Escrita Elementar
- E-mail informal para um amigo
- Descrição de rotina diária
- Mensagem para reagendar um encontro
- Pequeno parágrafo sobre fim de semana

### B1 — Escrita Intermediária
- E-mail formal simples (para chefe, empresa)
- Parágrafo de opinião (3–5 frases com justificativa)
- Descrição de lugar ou pessoa
- Mensagem de feedback sobre um serviço

### B2 — Escrita Intermediária Superior
- E-mail profissional (reclamação, proposta, follow-up)
- Parágrafo argumentativo (6–8 frases, com contraponto)
- Resumo de artigo ou notícia
- Review de produto/serviço

### C1 — Escrita Avançada
- Redação de opinião com estrutura completa (introdução, desenvolvimento, conclusão)
- Relatório profissional
- Carta formal (candidatura, reclamação formal)
- Análise crítica de texto

### C2 — Escrita Proficiente
- Ensaio argumentativo complexo
- Texto jornalístico ou acadêmico
- Redação com nuances de registro (formal, coloquial, técnico)

## Processo de Feedback — 4 Etapas

### Etapa 1: Leitura Geral
Leia o texto do aluno completamente antes de comentar qualquer coisa.
Identifique:
- Erros sistemáticos (revelam lacuna de conhecimento)
- Erros pontuais (lapsos, não são padrão)
- Pontos fortes (preserve e elogie genuinamente)

### Etapa 2: Versão Corrigida com Marcações

Apresente o texto com correções marcadas:

```
📝 SEU TEXTO (com correções):

[Texto original com marcações]

Legenda:
~~riscado~~ = remover
**[correção]** = substituir por isto
💡 [nota] = explicação adicional
```

### Etapa 3: Explicações por Categoria

Agrupe os erros por tipo e explique:

```
📚 EXPLICAÇÕES:

🔵 GRAMÁTICA:
• "[erro]" → "[correto]"
  Por quê: [explicação clara em português]

🟢 VOCABULÁRIO:
• "[palavra usada]" → "[palavra melhor]"
  Por quê: [nuance/precisão]

🟡 ESTRUTURA:
• [observação sobre organização das ideias]

🔴 ERRO RECORRENTE (prioridade):
• [Erro que apareceu mais de uma vez — reforçar]
```

### Etapa 4: Reescrita Guiada

Peça ao aluno para reescrever incorporando o feedback:

```
🔄 AGORA VOCÊ!

Reescreva o texto considerando as correções.
Tente incorporar pelo menos 3 das melhorias sugeridas.

Quando terminar, compartilhe a versão 2 para eu avaliar! ✍️
```

Após a reescrita, compare V1 × V2 e celebre a melhora.

## Avaliação (0–100)

| Critério | Peso | Descrição |
|---|---|---|
| **Vocabulário** | 25% | Variedade, precisão, adequação ao contexto |
| **Gramática** | 25% | Correção estrutural, uso dos tempos verbais |
| **Coerência** | 25% | Organização, conexão entre ideias, fluidez |
| **Tarefa cumprida** | 25% | O texto responde ao que foi pedido? |

```
📊 AVALIAÇÃO:

Versão 1: [X]/100
  • Vocabulário: [X]/25
  • Gramática: [X]/25
  • Coerência: [X]/25
  • Tarefa: [X]/25

Versão 2 (após reescrita): [X]/100
  Melhora: +[X] pontos 📈

🌟 Ponto mais forte desta sessão: [...]
🎯 Para focar na próxima: [...]
```

## Técnicas de Escrita a Ensinar (progressivo)

### A1/A2
- Maiúsculas e pontuação básica
- Estrutura de frase simples: Sujeito + Verbo + Complemento
- Conectores básicos: and, but, because, so

### B1
- Estrutura de parágrafo: tópico + desenvolvimento + conclusão
- Conectores: however, although, therefore, in addition
- Uso correto de vírgulas

### B2
- Frases complexas e subordinadas
- Registro formal vs informal
- Voz passiva para textos profissionais

### C1
- Cohesion devices: discourse markers, referencing, substitution
- Hedging language: "It could be argued that...", "There is some evidence to suggest..."
- Tone and register mastery

## Erros Comuns de Falantes de Português

| Erro típico | Forma correta | Explicação |
|---|---|---|
| "I am with 25 years" | "I am 25 years old" | Idade em inglês usa "to be + old" |
| "She is married with him" | "She is married to him" | Preposição "to", não "with" |
| "I have hunger" | "I am hungry" | Estados físicos usam "to be" |
| "The people is" | "The people are" | "People" é plural em inglês |
| "I will go in the beach" | "I will go to the beach" | Destinos usam "to", não "in" |
| "Actually" | "Currently/nowadays" | "Actually" = "na verdade", não "atualmente" |

## Registro no progress.json

```json
{
  "skill_sessions": {
    "writing": {
      "sessions": [incrementar +1],
      "last_session": "[DATA]",
      "avg_score": [recalcular média]
    }
  },
  "activities_completed": [
    {"date": "[DATA]", "type": "writing", "task": "[TIPO DE EXERCÍCIO]", "score": [NOTA]}
  ]
}
```
