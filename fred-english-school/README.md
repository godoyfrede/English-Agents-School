# Fred English School

Plugin de aprendizado de inglês com time de agentes IA. Metodologia **CLT (Communicative Language Teaching)**, 6 níveis CEFR (A1–C2), acompanhamento contínuo de progresso e atividades personalizadas para o dia a dia.

Desenvolvido por **Fred Godoy** · v0.1.0

---

## O que este plugin faz

1. **Avalia seu nível atual** com uma prova de nivelamento completa (A1 a C2)
2. **Ensina com o Professor** usando situações reais, role-play e feedback imediato
3. **Acompanha sua evolução** com o Supervisor — notas, histórico e decisões de avanço
4. **Gera atividades para-casa** personalizadas ao seu nível e rotina
5. **Recomenda conteúdo** — vídeos, podcasts, séries e textos para aprender no dia a dia
6. **Avalia seu progresso** mensalmente e decide se você avança, mantém ou revisa o nível

---

## O Time de Agentes

| Agente | Papel |
|--------|-------|
| **Principal** | Diretor e orquestrador — ponto de entrada de todas as interações. Sabe quem chamar para cada situação. |
| **Supervisor** | Guardião da memória — registra notas, mantém `progress.json`, decide avanços de nível baseado em critérios claros. |
| **Professor** | O professor de inglês — conduz aulas de conversação, escrita e vocabulário com metodologia CLT e feedback detalhado. |

---

## Skills Disponíveis

### `/placement-test`
Prova inicial de nivelamento (100 pts) cobrindo as três habilidades:
- Vocabulário & Compreensão (30 pts)
- Escrita (40 pts)
- Conversação (30 pts)

Ao final, define seu nível CEFR e cria `progress.json` com seu perfil completo.

---

### `/progress-test`
Prova mensal de acompanhamento, adaptada ao seu nível atual. Compara com provas anteriores e o Supervisor decide:

| Resultado | Decisão |
|-----------|---------|
| ≥ 80% por 2 provas seguidas | Avançar de nível 🎉 |
| 60–79% | Manter nível atual |
| < 60% | Revisar pontos fracos |

---

### `/conversation`
Sessões de prática de conversação com metodologia CLT:
- Role-plays em situações reais (trabalho, viagem, social)
- Storytelling e troca de opiniões
- Feedback estruturado de fluência, vocabulário e gramática
- 3–5 expressões novas por sessão

---

### `/writing-coach`
Exercícios de escrita com correção detalhada:
- Tarefa contextualizada ao seu nível (A1 a C2)
- Feedback por categoria (gramática, vocabulário, coerência)
- Ciclo V1 → correção → reescrita V2
- Pontuação comparativa entre versões

---

### `/vocabulary-reading`
Vocabulário contextualizado + leitura adaptada:
- 5–8 palavras novas apresentadas em frases reais (nunca em listas)
- Texto de leitura no seu nível exato
- Exercícios de compreensão
- Spaced repetition — palavras revisitadas em 3 e 7 dias

---

### `/daily-activities`
Plano semanal para-casa e recomendações de conteúdo:
- Micro-atividades de 5–30 min adaptadas à sua rotina
- Recomendações de podcasts, vídeos, séries e apps por nível
- Atividade relâmpago de 2 min para dias corridos
- Meta semanal mensurável

---

## Como Começar

```
1. Abra uma conversa com o Principal
2. Diga: "Quero começar a aprender inglês"
3. Faça o /placement-test para descobrir seu nível
4. Use as skills para praticar no seu ritmo
5. Faça /progress-test todo mês para acompanhar sua evolução
```

---

## Metodologia

**CLT — Communicative Language Teaching**

> A língua é aprendida USANDO, não decorando regras. Situações do dia a dia são a base de todo exercício. Erros são oportunidades de aprendizado.

- **Bilíngue adaptativo** — Exercícios em inglês, explicações e feedback em português
- **Spaced Repetition (SRS)** — Vocabulário revisitado em intervalos crescentes para fixação
- **Avaliação contínua** — Cada sessão é registrada e contribui para a decisão de nível
- **Progressão CEFR** — Critérios internacionais claros para medir e comunicar seu nível

---

## Níveis CEFR

| Nível | Descrição | O que você consegue fazer |
|-------|-----------|--------------------------|
| **A1** | Iniciante | Frases básicas, apresentação pessoal |
| **A2** | Básico | Situações simples do cotidiano |
| **B1** | Intermediário | Tópicos familiares, viagens, trabalho básico |
| **B2** | Interm. Superior | Textos complexos, fluência em temas variados |
| **C1** | Avançado | Expressão fluente, textos profissionais e acadêmicos |
| **C2** | Proficiente | Equivalente a falante nativo culto |

---

## Arquivo de Progresso

Seu progresso é salvo em `progress.json` no diretório de trabalho:

```json
{
  "student": "Fred",
  "current_level": "B1",
  "placement_date": "2026-04-07",
  "next_progress_test": "2026-05-07",
  "scores": { ... },
  "skill_sessions": { ... },
  "level_history": [ ... ]
}
```

O Supervisor lê e atualiza esse arquivo automaticamente após cada prova e atividade avaliada.

---

## Referências de Skills

| Arquivo | Conteúdo |
|---------|----------|
| `skills/placement-test/references/cefr-rubric.md` | Descritores completos de cada nível CEFR + rubricas de avaliação |
| `skills/conversation/references/clt-techniques.md` | Técnicas CLT, cenários de role-play, erros comuns de brasileiros |

---

*Fred English School Plugin v0.1.0 — Criado por Fred Godoy*
