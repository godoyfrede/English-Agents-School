# Fred English School

Plugin de aprendizado de inglês com time de agentes IA. Metodologia CLT (Communicative Language Teaching), 6 níveis CEFR (A1–C2), acompanhamento contínuo de progresso.

## O Time

| Agente | Papel |
|---|---|
| **Principal** | Diretor/Orquestrador — ponto de entrada de todas as interações |
| **Supervisor** | Guardião do progresso — notas, níveis, histórico em `progress.json` |
| **Professor** | Professor — conduz aulas de conversação, escrita e vocabulário |

## Skills Disponíveis

| Skill | O que faz |
|---|---|
| `/placement-test` | Prova inicial de nivelamento (determina seu nível CEFR) |
| `/progress-test` | Prova mensal de acompanhamento (decide avanço de nível) |
| `/conversation` | Prática de conversação com role-play e feedback |
| `/writing-coach` | Exercícios de escrita com correção detalhada |
| `/vocabulary-reading` | Vocabulário contextualizado + leitura adaptada |
| `/daily-activities` | Atividades para-casa e recomendações de conteúdo |

## Como Começar

1. Inicie uma conversa com o **Principal** ou use `/placement-test`
2. Faça a prova de nivelamento inicial
3. Seu nível CEFR será salvo em `progress.json`
4. Use as skills para praticar no seu ritmo
5. Faça `/progress-test` mensalmente para acompanhar sua evolução

## Metodologia

- **CLT** — Communicative Language Teaching: você aprende usando a língua, não decorando regras
- **Bilíngue adaptativo** — Exercícios em inglês, explicações e feedback em português
- **Spaced Repetition** — Vocabulário revisitado em intervalos crescentes
- **Avaliação contínua** — Notas registradas pelo Supervisor a cada sessão

## Níveis CEFR

A1 (Iniciante) → A2 (Básico) → B1 (Intermediário) → B2 (Interm. Superior) → C1 (Avançado) → C2 (Proficiente)

## Progresso

Seu progresso é salvo em `progress.json` no diretório de trabalho atual.
O Supervisor usa esse arquivo para acompanhar sua evolução e recomendar quando avançar de nível.

Critérios de avanço: 2 provas mensais consecutivas com pontuação ≥ 80%.
