# English Agents School — Visão Geral do Projeto

**Autor:** Fred Godoy  
**Versão:** 1.0.0  
**Data:** Abril 2026  
**Repositório:** https://github.com/godoyfrede/English-Agents-School

---

## A Origem

Este projeto nasceu de uma insatisfação pessoal — e de uma crença.

A insatisfação: **o inglês decoreba não funciona**. Apps, cursos e métodos tradicionais ensinam a língua como uma lista de regras a memorizar. Vocabulário para decorar. Gramática para copiar. Exercícios desconectados da vida real. O aluno termina sabendo *sobre* o inglês — mas não consegue *usar* o inglês.

Isso não é um problema de falta de esforço. É um problema de metodologia.

A crença: **a IA pode entregar uma experiência de aprendizado que nenhuma ferramenta convencional consegue** — não porque é mais inteligente, mas porque é infinitamente paciente, completamente adaptável e radicalmente pessoal. Ela não tem um currículo fixo para cumprir. Ela parte de onde você está, fala do jeito que você entende, e evolui com você.

E a segunda crença, talvez a mais importante: **esse tipo de ferramenta não deveria ser privada**. O acesso a uma educação de qualidade é um problema global. Se é possível construir um sistema assim com IA, ele deve ser aberto — para que qualquer pessoa, em qualquer lugar, com qualquer modelo de linguagem disponível, possa usá-lo.

---

## A Solução

**English Agents School** é um time de agentes de IA construído sobre uma metodologia real — CLT (Communicative Language Teaching) — que coloca o uso da língua no centro, não a memorização.

Não é um app. Não é um chatbot único. É um **sistema multi-agente** onde cada agente tem um papel específico — e todos trabalham juntos para criar uma experiência de aprendizado que se adapta ao seu nível, lembra da sua evolução e te desafia a crescer.

A ideia central: **usar a IA não como substituto de professor, mas como a estrutura que faltava** — um sistema que tem método, tem memória, tem critério de progressão e te encontra onde você está. Tudo isso sem precisar pagar por uma escola, um professor particular ou um app de assinatura.

Este projeto tem dois propósitos simultâneos: **aprender inglês de verdade** e **ser livre para a humanidade** — publicado como especificação open source para que qualquer pessoa possa usar, adaptar e construir em cima dele, com qualquer modelo de linguagem.

---

## O Time de Agentes

O sistema é composto por três agentes e seis skills especializadas.

### Principal — O Diretor

O ponto de entrada de toda interação. O Principal lê seu estado atual (nível, histórico, próxima prova), entende o que você quer fazer e direciona para o agente ou skill correto. Nunca ensina diretamente — seu papel é garantir que você sempre chegue ao lugar certo.

```
Você diz: "Quero praticar hoje"
Principal pensa: nível B1, última sessão foi conversação há 3 dias,
                 próxima prova em 12 dias → sugere writing coach
```

### Supervisor — A Memória

O guardião do seu progresso. O Supervisor registra a nota de cada atividade, mantém o histórico completo no `progress.json`, e aplica os critérios de avanço de nível com consistência. É ele quem decide — com base em dados, não em feeling — se você está pronto para o próximo nível CEFR ou se precisa revisar.

**Critério de avanço:** duas provas mensais consecutivas com pontuação ≥ 80% no nível atual.

### Professor — O Educador

O único agente que ensina. O Professor conduz sessões de conversação, escrita e vocabulário/leitura, sempre adaptadas ao seu nível CEFR atual. Usa a metodologia CLT (Communicative Language Teaching): você aprende usando a língua em situações reais, não decorando regras.

---

## As Skills

Além dos três agentes, o sistema tem seis skills especializadas — fluxos completos de trabalho para tarefas específicas:

| Skill | O que faz |
|---|---|
| **Placement Test** | Prova inicial de nivelamento. Define seu nível CEFR (A1 a C2) com base em 100 pontos distribuídos entre vocabulário, escrita e conversação. |
| **Progress Test** | Prova mensal adaptada ao seu nível atual. Compara com provas anteriores e aciona o Supervisor para a decisão de nível. |
| **Conversation** | Sessões de prática de conversação com role-play, storytelling e troca de opiniões. Feedback estruturado ao final. |
| **Writing Coach** | Exercícios de escrita com ciclo V1 → feedback → V2. Correções categorizadas por gramática, vocabulário e estrutura. |
| **Vocabulary & Reading** | Vocabulário apresentado em contexto (nunca em listas), texto de leitura no seu nível, e spaced repetition para fixação. |
| **Daily Activities** | Plano semanal para-casa com conteúdo **real e atual** buscado na web — episódio específico de podcast, vídeo do YouTube, artigo do dia — tudo com link direto e tarefa. |

---

## A Metodologia

O sistema é construído sobre três pilares comprovados da educação em línguas:

### CLT — Communicative Language Teaching

A abordagem mais pesquisada e eficaz no ensino de idiomas. O princípio central: você aprende uma língua **usando**, não estudando regras. Cada sessão é uma situação comunicativa real. A gramática surge do contexto, não de tabelas isoladas.

### CEFR — Common European Framework of Reference

O padrão internacional de referência para níveis de proficiência em idiomas, adotado por universidades e empregadores em todo o mundo. O sistema usa os seis níveis CEFR (A1, A2, B1, B2, C1, C2) como critério objetivo para placement, acompanhamento e decisão de avanço.

### SRS — Spaced Repetition System

Vocabulário aprendido não some. O sistema agenda revisões em intervalos crescentes (3 → 7 → 21 → 60 dias) para maximizar a retenção a longo prazo — o mesmo princípio usado pelo Anki e pelo Duolingo.

---

## Comunicação Bilíngue Adaptativa

O sistema usa um modelo específico de comunicação:

- **Português** → orientações, explicações gramaticais, feedback, relatórios
- **Inglês** → exercícios, conversações, role-plays, encorajamento durante a prática

Isso elimina a barreira de incompreensão nos níveis A1/A2, maximiza a imersão nos exercícios, e garante que o feedback seja sempre completamente entendido.

---

## Como o Progresso Funciona

Todo o estado do aluno vive em um único arquivo: `progress.json`.

```json
{
  "student": "Fred",
  "current_level": "B1",
  "placement_date": "2026-04-25",
  "next_progress_test": "2026-05-25",
  "scores": {
    "placement": { "total": 48 },
    "progress_tests": [
      { "date": "2026-05-25", "score": 71, "decision": "maintain" },
      { "date": "2026-06-25", "score": 83, "decision": "advance" }
    ]
  },
  "skill_sessions": {
    "conversation": { "sessions": 8, "avg_score": 74 },
    "writing": { "sessions": 5, "avg_score": 69 },
    "vocabulary_reading": { "sessions": 6, "avg_score": 82 }
  },
  "level_history": [
    { "date": "2026-06-25", "from": "B1", "to": "B2", "reason": "2 provas consecutivas ≥ 80%" }
  ]
}
```

Nenhuma informação é deletada. Toda a jornada é preservada: desde o primeiro placement até cada sessão, cada prova e cada decisão de nível.

---

## Duas Distribuições

O projeto é publicado em duas formas complementares:

### Claude Cowork Plugin

Arquivo `fred-english-school.plugin` pronto para importar no Claude Cowork. Nenhum código necessário. Basta importar e começar.

**Como usar:**
1. Baixe o arquivo `.plugin` na [página de releases](https://github.com/godoyfrede/English-Agents-School/releases)
2. Importe no Claude Cowork
3. Diga: *"Quero começar a aprender inglês"*

### Especificação Open Source

A pasta `open-source/` contém a especificação completa do sistema em formato agnóstico de framework e modelo. Qualquer desenvolvedor pode usar os arquivos YAML e Markdown para construir sua própria implementação com o modelo e framework de sua escolha.

**Compatível com:** Claude, GPT-4o, Llama 3.1, Mistral, Gemini, e qualquer modelo com suporte a system prompts e tool use.

**Funciona com:** LangChain, CrewAI, AutoGen, Ollama, ou qualquer chamada direta de API.

```python
# Exemplo mínimo — funciona com qualquer provider
from openai import OpenAI
from pathlib import Path

client = OpenAI()  # substitua por anthropic, ollama, gemini, etc.
system = Path("open-source/prompts/professor.md").read_text()

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": system},
        {"role": "user", "content": "Quero praticar conversação"}
    ]
)
```

---

## Arquitetura do Sistema

```
┌─────────────────────────────────────────────┐
│                  ESTUDANTE                   │
└─────────────────────┬───────────────────────┘
                      │
                      ▼
         ┌────────────────────────┐
         │       PRINCIPAL        │  ← entrada única
         │   (Orquestrador)       │    lê progress.json
         └──────┬────────┬────────┘    roteia intent
                │        │
        ┌───────┘        └────────┐
        ▼                         ▼
┌──────────────┐         ┌──────────────────┐
│  SUPERVISOR  │         │    PROFESSOR     │
│              │         │                  │
│ Escreve em   │◄────────│ Envia score      │
│ progress.json│         │ após cada sessão │
└──────────────┘         └──────────────────┘
        │                         │
        └──────────┬──────────────┘
                   ▼
          ┌─────────────────┐
          │  progress.json  │  ← fonte única de verdade
          │  (estado)       │
          └─────────────────┘
                   ▲
                   │ lê/escreve
          ┌────────┴────────┐
          │   SKILLS        │
          │ (stateless)     │
          │ placement-test  │
          │ progress-test   │
          │ conversation    │
          │ writing-coach   │
          │ vocabulary      │
          │ daily-activities│
          └─────────────────┘
```

**Princípios de design:**
- **Separação de responsabilidades** — cada agente faz exatamente uma coisa
- **Estado como fonte única de verdade** — `progress.json` é a memória do sistema
- **Aditividade** — o progresso nunca é deletado, apenas acumulado
- **Agnóstico de modelo** — system prompts em Markdown puro, qualquer LLM executa

---

## Estrutura do Repositório

```
English-Agents-School/
│
├── fred-english-school/          ← Plugin Claude Cowork
│   ├── .claude-plugin/
│   │   └── plugin.json
│   ├── agents/
│   │   ├── principal.md
│   │   ├── supervisor.md
│   │   └── professor.md
│   ├── skills/
│   │   ├── placement-test/
│   │   ├── progress-test/
│   │   ├── conversation/
│   │   ├── writing-coach/
│   │   ├── vocabulary-reading/
│   │   └── daily-activities/
│   ├── README.md
│   └── LICENSE
│
├── open-source/                  ← Especificação Open Source
│   ├── agents/                   ← Specs YAML dos agentes
│   ├── skills/                   ← Specs YAML das skills
│   ├── prompts/                  ← System prompts (Markdown)
│   ├── schemas/                  ← JSON Schema do progress.json
│   ├── implementations/          ← Guias: OpenAI, Anthropic, Ollama
│   └── docs/
│       ├── ARCHITECTURE.md
│       ├── METHODOLOGY.md
│       └── HOW_TO_IMPLEMENT.md
│
├── PROJECT.md                    ← Este documento
├── README.md                     ← Visão geral do repositório
└── .gitignore
```

---

## Decisões de Design

**Por que um arquivo JSON para o estado?**  
Simplicidade e portabilidade. Qualquer linguagem lê e escreve JSON. Nenhuma dependência de banco de dados. Funciona offline. Pode ser versionado com git.

**Por que YAML para as specs dos agentes?**  
Legível por humanos, parseable por qualquer framework (LangChain, CrewAI, AutoGen). Separa a *definição* do agente da sua *implementação*.

**Por que Markdown para os system prompts?**  
O formato mais universal para instruções de LLM. Qualquer modelo entende. Qualquer editor abre. Qualquer dev contribui sem aprender uma nova sintaxe.

**Por que bilíngue e não total imersão?**  
Imersão total é eficaz acima do B1. Para A1/A2, causa frustração e abandono. O modelo adaptativo garante que o aluno sempre entenda o que está fazendo, enquanto a prática acontece totalmente em inglês.

**Por que CEFR e não sistema proprietário de níveis?**  
O CEFR é reconhecido internacionalmente por empregadores, universidades e exames (IELTS, TOEFL, Cambridge). O aluno sabe exatamente o que seu nível significa no mundo real.

---

## Roadmap

### v1.1 — Pronunciação
- Integração com APIs de análise de áudio (ElevenLabs, Whisper)
- Feedback de pronúncia em sessões de conversação
- Exercícios de shadowing com comparação fonética

### v1.2 — Conteúdo Temático
- Módulos especializados: inglês para negócios, inglês técnico, inglês acadêmico
- Professor adapta exemplos e vocabulário ao domínio do aluno

### v1.3 — Multiusuário
- Suporte a múltiplos alunos no mesmo sistema
- Progress.json por aluno, isolado
- Dashboard comparativo (para uso em contexto educacional)

### v2.0 — Memória Vetorial
- Substituir `progress.json` por vector store (Chroma, Pinecone, pgvector)
- Recall semântico de sessões anteriores
- Conexões automáticas entre conteúdos aprendidos

---

## Licença

MIT License — Fred Godoy, 2026

Livre para usar, modificar e distribuir. Atribuição apreciada.

---

*English Agents School — construído com Claude Cowork*  
*Fred Godoy · 2026*
