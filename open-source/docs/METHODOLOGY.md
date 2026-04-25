# Methodology — English Agents School

## CLT: Communicative Language Teaching

The English Agents School is built entirely on **Communicative Language Teaching (CLT)**, one of the most widely researched and effective approaches to language instruction.

### Core Principle

> Language is learned by **using** it in real communicative situations — not by memorizing grammar rules or vocabulary lists.

### What CLT Means in Practice

| Traditional approach | CLT approach (this system) |
|---|---|
| Grammar rule → drill → exercise | Real situation → natural use → feedback |
| Vocabulary list to memorize | Words presented in context, in sentences |
| Accuracy first | Fluency first, accuracy refined through feedback |
| Teacher talks, student listens | Student talks, agent facilitates |
| Textbook dialogues | Real-world scenarios (job interview, travel, work) |

---

## CEFR Framework

The **Common European Framework of Reference for Languages (CEFR)** is the international standard for describing language ability. All level decisions in this system are anchored to CEFR.

### Level Descriptors

| Level | Label | Can Do |
|---|---|---|
| **A1** | Beginner | Introduce self, understand/use very basic phrases |
| **A2** | Elementary | Communicate in simple, routine tasks |
| **B1** | Intermediate | Deal with familiar topics, travel, work basics |
| **B2** | Upper-Intermediate | Understand complex texts, interact with fluency |
| **C1** | Advanced | Express ideas fluently, use language for academic/professional purposes |
| **C2** | Proficient | Understand and produce virtually anything |

### How the System Uses CEFR

1. **Placement test** assigns initial level
2. **Every lesson** is calibrated to the current level (vocabulary, complexity, pace)
3. **Monthly progress tests** measure advancement with standardized criteria
4. **Supervisor** applies objective level-change rules (not subjective judgment)
5. **Level history** is always preserved in `progress.json`

---

## Spaced Repetition System (SRS)

Vocabulary acquisition uses a simplified **spaced repetition schedule**:

| Review | Timing |
|---|---|
| 1st review | 3 days after learning |
| 2nd review | 7 days after learning |
| 3rd review | 21 days after learning |
| Long-term | 60 days after learning |

Words are tracked in `activities_completed` with a `review_date` field. The Supervisor or Professor checks this field at the start of each session.

---

## Bilingual Adaptive Mode

The system uses a specific language distribution model:

| Context | Language |
|---|---|
| Navigation, options, greetings | Portuguese (PT-BR) |
| Exercise instructions | English |
| Exercises, conversations, role-plays | English |
| Grammar explanations | Portuguese (PT-BR) |
| Error corrections | PT-BR + English side-by-side |
| Encouragement during exercises | English |
| Progress reports | Portuguese (PT-BR) |

**Rationale:** Total immersion is effective at higher levels but demotivating at A1/A2. The bilingual adaptive model ensures comprehension while maximizing English exposure.

---

## Assessment Design

### Placement Test (one-time)
- **Purpose:** Establish baseline CEFR level
- **Coverage:** Vocabulary/Comprehension (30 pts) + Writing (40 pts) + Conversation (30 pts)
- **Result:** Level assignment + personalized feedback

### Progress Test (monthly)
- **Purpose:** Measure evolution, trigger level decisions
- **Coverage:** Vocabulary/Grammar (30 pts) + Writing (30 pts) + Conversation (40 pts)
- **Adaptation:** Questions calibrated to current level + one level above
- **Outcome:** Level maintained, advanced, or reviewed

### Session Scoring (every session)
- Professor scores every practice session (0–100)
- Scores are averaged by skill in `progress.json`
- Supervisor uses averages as supplementary data for level decisions

---

## Feedback Philosophy

1. **Delayed correction in conversation** — Do not interrupt fluency; collect errors and address at the end
2. **Recast technique** — Naturally repeat the student's utterance with the correction embedded
3. **Error categorization** — Grammar, vocabulary, structure, and recurring errors are separated
4. **Positive anchoring** — Always lead with genuine strengths before corrections
5. **V1 → V2 cycle** — In writing, always request a rewrite after feedback to consolidate learning

---

## References

- Council of Europe. (2001). *Common European Framework of Reference for Languages: Learning, Teaching, Assessment*. Cambridge University Press.
- Littlewood, W. (1981). *Communicative Language Teaching*. Cambridge University Press.
- Richards, J. C., & Rodgers, T. S. (2001). *Approaches and Methods in Language Teaching*. Cambridge University Press.
- Nation, I.S.P. (2001). *Learning Vocabulary in Another Language*. Cambridge University Press.
- Waring, R., & Nation, P. (1997). Vocabulary size, text coverage, and word lists. In N. Schmitt & M. McCarthy (Eds.), *Vocabulary: Description, Acquisition and Pedagogy*.
