# English Agents School

Repositório do **Fred English School Plugin** — time de agentes IA para aprendizado de inglês personalizado, construído para o Claude Cowork.

Desenvolvido por **Fred Godoy**

---

## Sobre

O Fred English School é um plugin de aprendizado de inglês com 3 agentes especializados e 6 skills, usando metodologia **CLT (Communicative Language Teaching)** e o framework de níveis **CEFR** (A1 a C2).

O plugin acompanha sua evolução ao longo do tempo, adapta cada aula ao seu nível atual e decide automaticamente quando você está pronto para avançar.

---

## Conteúdo do Repositório

```
fred-english-school/          ← Plugin pronto para instalar no Cowork
├── .claude-plugin/
│   └── plugin.json           ← Manifesto do plugin
├── agents/
│   ├── principal.md          ← Diretor/Orquestrador
│   ├── supervisor.md         ← Memória e progresso
│   └── professor.md          ← Professor de inglês
├── skills/
│   ├── placement-test/       ← Prova de nivelamento inicial
│   ├── progress-test/        ← Prova mensal de acompanhamento
│   ├── conversation/         ← Prática de conversação (CLT)
│   ├── writing-coach/        ← Coach de escrita com feedback
│   ├── vocabulary-reading/   ← Vocabulário + leitura adaptada
│   └── daily-activities/     ← Atividades para-casa + conteúdo
├── README.md
└── LICENSE
```

---

## Instalação

1. Faça o download do arquivo `fred-english-school.plugin`
2. Abra o Claude Cowork
3. Importe o arquivo `.plugin`
4. Inicie com: `"Quero começar a aprender inglês"`

---

## Documentação

Consulte o [README do plugin](./fred-english-school/README.md) para documentação completa de todas as skills, agentes e metodologia.

---

## Licença

[MIT License](./fred-english-school/LICENSE) — Fred Godoy, 2026
