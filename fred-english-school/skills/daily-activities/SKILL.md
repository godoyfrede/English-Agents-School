---
name: daily-activities
description: >
  Gera atividades Para-Casa (homework) personalizadas e busca conteúdo real e atual
  em inglês (vídeos, podcasts, textos, artigos) adaptado ao nível CEFR do aluno.
  Usa busca na web para indicar episódios específicos, artigos recentes e vídeos reais.
  Use este skill quando: o aluno quer atividades para fazer fora das aulas, conteúdo
  para consumir em inglês, ou usa termos como "para-casa", "homework", "atividades",
  "o que assistir em inglês", "podcast de inglês", "série para aprender inglês",
  "daily activities", "conteúdo em inglês", "aprender no dia a dia", "o que ler hoje".
tools:
  - Read
  - Write
  - WebSearch
  - WebFetch
---

# Daily Activities — Fred English School

Gere um plano de atividades para-casa com conteúdo real buscado na web, personalizado ao nível CEFR do aluno.

## Preparação

1. Leia `progress.json` → nível atual, habilidades em foco, histórico de atividades
2. Identifique quanto tempo o aluno tem disponível por dia (pergunte se não souber)
3. **Busque conteúdo real e atual** para cada tipo de recomendação (veja seção de busca abaixo)

## Perguntas de Contexto (se necessário)

Se não tiver informação suficiente, pergunte:

```
Para montar suas atividades personalizadas, me conta rapidinho:

1. Quanto tempo você tem para inglês por dia? (ex: 15 min, 30 min, 1 hora)
2. Em que momento do dia? (manhã, almoço, tarde, noite)
3. Tem algum tema que você curte? (tecnologia, negócios, esportes, cultura, ciência...)
4. Você prefere atividades mais: ativas (escrever, responder) ou passivas (ouvir, assistir)?
```

## Busca de Conteúdo Real (OBRIGATÓRIO)

Antes de montar o plano, **sempre busque conteúdo atual** usando WebSearch. O objetivo é indicar o episódio ou artigo específico do dia, não apenas o canal genérico.

### Estratégia de busca por tipo e nível:

#### Podcast — busque o episódio mais recente

| Nível | Query de busca |
|---|---|
| A1/A2 | `BBC Learning English podcast latest episode 2025` |
| A1/A2 | `Culips ESL podcast latest episode` |
| B1 | `BBC 6 Minute English latest episode site:bbc.co.uk` |
| B1 | `"The English We Speak" BBC latest 2025` |
| B2 | `NPR Up First latest episode` ou `How I Built This latest episode` |
| C1 | `The Daily NYT podcast latest episode` ou `Freakonomics latest` |
| C2 | `Lex Fridman podcast latest episode` |

#### YouTube / Vídeo — busque vídeo específico recente

| Nível | Query de busca |
|---|---|
| A1/A2 | `English with Lucy latest video 2025 youtube` |
| A1/A2 | `Learn English beginner video youtube 2025` |
| B1 | `BBC Learning English 6 minute english latest youtube` |
| B2 | `TED Talk english subtitles [TEMA DO ALUNO] 2024 2025` |
| B2 | `Vox explainer video english 2025` |
| C1 | `TED Talk advanced english [TEMA DO ALUNO]` |
| C1 | `Kurzgesagt latest video 2025` |
| C2 | `Last Week Tonight latest episode` |

#### Artigo / Leitura — busque artigo atual

| Nível | Query de busca |
|---|---|
| A1/A2 | `BBC Learning English news report today 2025` |
| A1/A2 | `Newsela article level 2 english [TEMA]` |
| B1 | `BBC News simple english article today` |
| B1 | `The Guardian easy english article [TEMA] 2025` |
| B2 | `The Economist article [TEMA] 2025` |
| B2 | `Harvard Business Review article english [TEMA]` |
| C1 | `The Atlantic article [TEMA] 2025` |
| C1 | `The New Yorker article english 2025` |

### Como apresentar o conteúdo encontrado:

Para cada item de conteúdo buscado, apresente SEMPRE:
- **Título exato** do episódio/vídeo/artigo
- **Link direto** (URL)
- **Duração ou tamanho** estimado (ex: "8 min", "5 min de leitura")
- **Por que é bom para seu nível** (1 frase)
- **O que fazer com ele** (instrução específica de atividade)

---

## Formato do Plano Semanal

```
📚 SEU PLANO DE INGLÊS — SEMANA DE [DATA]
Nível: [NÍVEL CEFR] | Tempo diário: [X min]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📅 SEGUNDA — Vocabulário & Leitura
📰 Leia hoje:
   "[TÍTULO DO ARTIGO]"
   🔗 [URL]
   ⏱️ [X min de leitura]
   📝 Tarefa: anote 5 palavras novas e escreva uma frase com cada uma

📅 TERÇA — Listening
🎙️ Ouça hoje:
   "[TÍTULO DO EPISÓDIO]" — [Nome do Podcast]
   🔗 [URL]
   ⏱️ [X min]
   📝 Tarefa: escreva 3 pontos principais que você entendeu

📅 QUARTA — Speaking (atividade ativa)
✍️ Exercício de escrita ou fala:
   [Micro-atividade contextualizada ao nível]

📅 QUINTA — Vídeo
▶️ Assista hoje:
   "[TÍTULO DO VÍDEO]" — [Canal]
   🔗 [URL]
   ⏱️ [X min]
   📝 Tarefa: [instrução específica]

📅 SEXTA — Revisão + Escrita
✍️ [Exercício de escrita baseado no conteúdo da semana]

📅 SÁBADO — Imersão leve (15 min)
🎵 Sugestão: [música, série, filme ou conteúdo leve]
   🔗 [URL se disponível]

📅 DOMINGO — Descanso ativo (opcional)
💬 [Atividade mínima de 2 min]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🎯 META DA SEMANA: [Meta específica e mensurável]
💡 DICA DA SEMANA: [Conselho prático baseado no nível]
```

---

## Atividades por Nível (quando o conteúdo buscado não estiver disponível)

### A1 — Micro-Hábitos Diários (5–15 min)
- Aprender 3 palavras novas com imagem/exemplo
- Escrever 2 frases descrevendo sua foto do dia em inglês
- Assistir 1 vídeo de 5 min com legenda em inglês
- Mudar o idioma de 1 app do celular para inglês

### A2 — Construção de Rotina (15–20 min)
- Escrever um diário em inglês (3–4 frases/dia)
- Ouvir uma música e tentar entender a letra
- Ler 1 notícia simples no BBC Learning English

### B1 — Imersão Progressiva (20–30 min)
- Ouvir 1 episódio de podcast com transcript
- Ler 1 artigo e resumir em 3 frases em inglês
- Praticar shadowing por 10 min

### B2 — Consumo Autêntico (30 min)
- Ouvir podcast nativo sem legenda + anotar palavras novas
- Ler artigo completo em jornal inglês
- Comentar algo em inglês no Reddit ou Quora

### C1 — Fluência e Nuance (30–45 min)
- Ler artigo de opinião complexo
- Escrever análise de 200 palavras sobre conteúdo consumido
- Assistir debate ou stand-up comedy

---

## Séries e Filmes (recomendação fixa, não precisa buscar)

| Nível | Sugestão | Por quê |
|---|---|---|
| A1/A2 | Friends (temporadas 1–3) | Linguagem clara, situações do dia a dia |
| A2/B1 | The Office | Inglês americano natural, vocabulário de trabalho |
| B1 | Brooklyn Nine-Nine | Diálogos claros, humor acessível |
| B1/B2 | Suits | Inglês profissional, vocabulário rico |
| B2 | The Crown | Inglês britânico formal, sofisticado |
| C1 | Breaking Bad / Better Call Saul | Muito idiomático, linguagem complexa |
| C1/C2 | The Wire | Dialetos, gírias, inglês ultra-autêntico |

---

## Apps Recomendados

- **Anki** — Flashcards com spaced repetition (qualquer nível)
- **Elsa Speak** — Treinamento de pronúncia com IA
- **LingQ** — Leitura + vocabulário integrado (B1+)
- **Duolingo** — Gamificação, bom para A1/A2

---

## Atividade Flash (2 min/dia)

Para dias muito corridos:

```
⚡ ATIVIDADE RELÂMPAGO (só 2 minutos!):

Escreva 3 frases em inglês descrevendo o que você está fazendo agora.
Exemplo: "I'm sitting at my desk. I just finished a meeting. I'm thinking about lunch."

Isso já conta como prática! Every little bit helps. 🌱
```

---

## Registro no progress.json

```json
{
  "activities_completed": [
    {
      "date": "[DATA]",
      "type": "daily_plan",
      "week_start": "[DATA INÍCIO SEMANA]",
      "level": "[NÍVEL]",
      "content_found": [
        {"type": "podcast", "title": "[TÍTULO]", "url": "[URL]"},
        {"type": "article", "title": "[TÍTULO]", "url": "[URL]"},
        {"type": "video", "title": "[TÍTULO]", "url": "[URL]"}
      ]
    }
  ]
}
```
