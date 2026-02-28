# 🔬 Deep Dive 3: O que Ainda Não Foi Pensado

> Este é o terceiro documento de análise profunda. Cobre ângulos que nem os dois anteriores
> tocaram — desde inconsistências nos seus próprios arquivos até cenários mentais, rotina
> prática semanal, e a pergunta mais importante que ninguém fez ainda.

---

## 🚨 1. Seus Próprios Arquivos Estão Desalinhados

Ao ler todos os arquivos do repositório, encontrei **inconsistências que te prejudicam agora**:

### `generate_cv.py` — Currículo desatualizado

| Campo | O que diz no CV | O que deveria dizer |
|---|---|---|
| TITLE | "Engenheiro de Dados \| Analista de BI \| Automação de TI" | "Data Engineer \| AI Engineering \| Microsoft Fabric" |
| SUMMARY | "11 anos de trajetória no Bradesco" | "12 anos" (fev/2026) |
| SUMMARY | "utilizando Databricks, Python e SQL" | Adicionar Fabric, AI Engineering |
| CERTIFICATIONS | Não lista AZ-900 | Já obtida em Fev/2026 |
| EXPERIENCES titulo | "Analista de Business Intelligence" | LinkedIn diz "Engenheiro de Analytics" |

> ⚠️ Se um recrutador baixar seu PDF e comparar com seu LinkedIn, encontra informações diferentes. Isso gera desconfiança automática.

**Ação imediata:** Atualizar `generate_cv.py` e regenerar os PDFs. **Tempo: 30 minutos.**

### LinkedIn vs README.md vs CV vs career-plan

Seu título muda entre os arquivos:
- LINKEDIN.md: "Data Engineer | Analytics Engineer | IT Automation Specialist"
- README.md: Sem título definido
- CV (generate_cv.py): "Engenheiro de Dados | Analista de BI | Automação de TI"
- Career Plan: "AI Data Engineer estratégico"

**Isso precisa convergir.** Um profissional com 4 identidades diferentes em 4 canais transmite confusão, não versatilidade.

**Sugestão de título unificado (2026):**
> `Data Engineer | Microsoft Fabric & Databricks | AI Engineering`

Use esse **exatamente** no LinkedIn, README, CV e career plan.

---

## 🌐 2. alannascimento.com — Existe ou Não?

No arquivo `LINKEDIN_VERSIONS.md`, linha 3, você lista:
```
[alannascimento.com](https://alannascimento.com)
```

**Isso existe?** Se sim, está atualizado? Se não, é um domínio registrado mas sem conteúdo?

### Por que isso importa MUITO

Um site pessoal é o **único canal que você controla 100%**. LinkedIn muda algoritmo. GitHub é técnico demais para RHs. Seu site é onde tudo converge.

**O que um site de Tech Lead em DE/AI precisa ter (mínimo):**

```
alannascimento.com/
├── / (Home)           → Quem sou, headline, links para LinkedIn/GitHub
├── /projetos          → Portfólio com screenshots e diagramas de arquitetura
├── /blog              → Artigos técnicos (pode começar com 3)
├── /carreira           → Versão interativa do seu career plan (index.html!)
└── /certificacoes     → Lista visual com badges
```

**Ação de alto impacto:**
- Se o domínio existe: hospede seu career plan `index.html` em `alannascimento.com/carreira` agora. Já está pronto.
- Se não existe: registre o domínio (R$40/ano) e use GitHub Pages ou Vercel (gratuito) para hospedar.

---

## 🤖 3. AI Como Acelerador de Aprendizado (não só como tema de estudo)

Você planeja **estudar** AI. Mas já está **usando** AI para acelerar seu aprendizado? Isso é meta, mas é real.

### Como usar AI para aprender DE/AI 3x mais rápido:

| Cenário | Como usar |
|---|---|
| Estudando dbt | Cole o código no Claude/ChatGPT e peça: "Explique cada linha. Depois me dê 3 exercícios para praticar." |
| Lendo Kleppmann (DDIA) | Depois de cada capítulo: "Resuma o capítulo X em 5 pontos. Me dê 3 perguntas de entrevista baseadas nesse conteúdo." |
| Preparando tech talk | Cole seus slides e peça: "Critique esta apresentação. O que está confuso? O que está faltando?" |
| Escrevendo post LinkedIn | Cole o rascunho: "Torne isso mais direto e técnico. Remova fluff." |
| Debugging Python/PySpark | Cole o erro: "Explique o que causou isso e me dê 3 formas de prevenir." |
| Aprendendo Airflow | "Crie um DAG de exemplo que extrai dados de uma API, transforma com Pandas e salva em Parquet." |

> A AI não substitui o estudo. Ela comprime o tempo entre "não entendo" e "sei aplicar".

### Ferramentas específicas para DE/AI:
- **GitHub Copilot** — R$10/mês. Acelera código PySpark e SQL em 30-50%.
- **Claude** — Para explicações profundas e debugging complexo.
- **NotebookLM (Google)** — Cole seus PDFs técnicos e converse com eles. Ideal para os livros do O'Reilly.

---

## 📅 4. A Semana Real: Design de Rotina Prática

Nenhum plano de carreira funciona sem uma rotina semanal que comporte tudo. Vamos ser realistas:

**Premissas:**
- Trabalho integral no Bradesco (~8h/dia, mais deslocamento)
- Pós DSA em andamento
- Cambly 30min/semana
- Vida pessoal, saúde, descanso

### Proposta de Semana Tipo (realista)

| Dia | Manhã (antes do trabalho) | Noite (pós-trabalho) | Notas |
|---|---|---|---|
| **Seg** | 30min: Anki (revisão espaçada) | 1h: Estudo técnico (dbt/Fabric/Databricks) | Deep Work noturno |
| **Ter** | 30min: Podcast técnico (inglês) | 1h: Pós DSA (módulo da semana) | Consumo passivo de manhã |
| **Qua** | 30min: Cambly | 1h: Projeto portfólio (construir algo) | Output > Input |
| **Qui** | 30min: Anki + leitura O'Reilly | 1h: Estudo técnico ou certificação | Variação por prioridade |
| **Sex** | 30min: Podcast técnico (inglês) | Livre ou estudo leve | Evitar burnout |
| **Sáb** | 2h: Deep Work (projeto portfólio) | — | Bloco mais importante da semana |
| **Dom** | 1h: Revisão semanal (Obsidian) | — | Reflexão + planejamento |

**Total semanal:** ~10h de estudo/construção (realista para quem trabalha full-time)

> **A regra mais importante:** Proteja o sábado de manhã. Esse é o bloco que constrói portfólio. Sem portfólio, o resto não multiplica.

---

## 🧠 5. O Segundo Cérebro: Arquitetura do Obsidian

Você menciona Obsidian no plano. Mas tem uma estrutura definida? Sem estrutura, o Obsidian vira um cemitério de notas.

### Estrutura recomendada para DE/AI Tech Lead:

```
Obsidian Vault/
├── 🎯 Carreira/
│   ├── Roadmap.md (link para career plan)
│   ├── Revisão Semanal.md (template)
│   ├── Métricas Pessoais.md (tracking mensal)
│   └── Networking.md (contatos estratégicos)
├── 📚 Aprendizado/
│   ├── Livros/
│   │   ├── AI Engineering - Chip Huyen.md
│   │   ├── Fundamentos DE - Joe Reis.md (notas por capítulo)
│   │   └── DDIA - Kleppmann.md
│   ├── Certificações/
│   │   ├── PL-300 - Notas.md
│   │   └── Databricks DEA - Notas.md
│   └── Conceitos/
│       ├── Delta Lake.md
│       ├── Medallion Architecture.md
│       └── RAG Pattern.md
├── 🔧 Projetos/
│   ├── Fabric Lakehouse.md (diário de progresso)
│   └── dbt Pipeline.md
├── ✍️ Conteúdo/
│   ├── Posts LinkedIn/
│   │   ├── Rascunho - Fabric vs Synapse.md
│   │   └── Publicado - Pipeline Databricks.md
│   └── Tech Talks/
└── 📝 Daily Notes/ (diário rápido, max 5 linhas/dia)
```

### Template de Revisão Semanal (todo domingo, 30-60min):

```markdown
## Revisão Semanal — [Data]

### O que eu aprendi esta semana?
- 

### O que eu construí?
- 

### O que eu publiquei?
- 

### O que travou meu progresso?
- 

### Prioridade #1 da próxima semana:
- 

### Métricas:
- Commits: 
- Horas de estudo real: 
- Post LinkedIn: sim/não
```

---

## 💡 6. Side Projects Como Produtos (não como exercícios)

A diferença entre um portfólio "bom" e um portfólio que **abre portas de verdade**:

| Portfólio comum | Portfólio de Tech Lead |
|---|---|
| "Fiz um pipeline de ETL" | "Criei um template de pipeline que qualquer Data Engineer pode reusar" |
| "Analisei dados do Kaggle" | "Construí uma solução que resolve um problema real que qualquer empresa tem" |
| "Segui um tutorial de dbt" | "Criei um starter kit de dbt para projetos Fabric, com testes e docs inclusos" |

### 3 Side Projects com potencial real de produto:

**Projeto 1: "Fabric Starter Kit"**
- Um repositório template para iniciar projetos de dados no Microsoft Fabric
- Inclui: notebooks pré-configurados, esquema Medallion, testes, README em PT-BR e EN
- **Impacto:** Pode virar referência na comunidade Fabric brasileira (que ainda é pequena)

**Projeto 2: "Data Quality Dashboard Template"**
- Template de Power BI conectado a Great Expectations / Soda para visualizar qualidade de dados
- Inclui: alertas, métricas de SLA, histórico de falhas
- **Impacto:** Todo time de dados precisa disso e poucos têm

**Projeto 3: "RAG sobre Documentação Técnica"**
- Um chatbot que responde perguntas sobre a documentação dos seus próprios pipelines
- Usando Azure OpenAI + LangChain + documentos do dbt docs
- **Impacto:** Demonstra AI Engineering aplicada a um problema real de Data Engineering

---

## 🎭 7. A Jornada Emocional que Ninguém Avisa

Transições de carreira têm um padrão emocional previsível. Saber disso antes evita que você desista no momento errado:

```
Mês 1-2:  "Vou dominar tudo! Estou motivado!" ← Entusiasmo inicial
Mês 3-4:  "Tem tanta coisa... será que consigo?" ← Vale da desilusão
Mês 5-6:  "Estou aprendendo mas não vejo resultado" ← Platô silencioso
Mês 7-9:  "Finalmente algo clicou!" ← Primeiro insight real
Mês 10-12: "Espera, eu sei mais do que achava" ← Competência inconsciente
Mês 12+:  "Agora sei o que não sei — e isso é bom" ← Tech Lead mindset
```

> O mês 3-4 é onde 80% das pessoas desistem. É onde o Anki parece chato, o Cambly parece inútil e o dbt parece impossível. **Quem passa desse ponto ganha**.

---

## 🏗️ 8. ADRs: O Artefato Mais Poderoso para Tech Lead

Architecture Decision Records (ADRs) são documentos curtos que explicam **por que** uma decisão técnica foi tomada.

**Por que isso é tão importante:**
- Tech Leads são julgados pelas decisões, não pelo código.
- ADRs mostram pensamento estruturado. Recrutadores de posições sênior amam isso.
- Publicar ADRs no GitHub mostra maturidade.

### Template de ADR:

```markdown
# ADR-001: Escolher Databricks ao invés de Azure Synapse

## Status: Aceito

## Contexto
Precisávamos de uma plataforma para processar dados de riscos corporativos com
volumes diários de X GB, vindo de fontes Hive, Teradata e Oracle.

## Decisão
Escolhemos Databricks porque:
1. Melhor performance para PySpark interativo
2. Unity Catalog para governança nativa
3. Delta Live Tables para pipelines declarativos

## Alternativas Consideradas
- Azure Synapse: descartado por custo e complexidade de setup
- AWS Glue: descartado por não ser o cloud padrão da empresa

## Consequências
- (+) Time produtivo em 2 semanas
- (+) Custo 30% menor que estimativa Synapse
- (-) Dependência de Databricks para orquestração
```

**Ação:** Para cada projeto que você criar, escreva ao menos 1 ADR. Publique no repo.

---

## 🎤 9. Palestras e Eventos: A Alavanca Ignorada

Você não precisa ir ao AWS re:Invent. Precisa falar em **1 meetup local** por semestre.

**Meetups com curadoria para São Paulo (DE/AI):**
- **Data Hackers** — Maior comunidade de dados do Brasil. Meetups mensais em SP.
- **Microsoft Fabric User Group Brazil** — Comunidade nascente. Palestrantes iniciais ganham visibilidade desproporcional.
- **Databricks User Group SP** — Técnico, relevante para seu stack.
- **Python São Paulo** — Aberto, fácil de propor palestras.

**Formato ideal para primeira palestra (15-20min):**
> "Como construí um pipeline Medallion no Databricks para Riscos Corporativos no Bradesco"

Isso fala sobre: tecnologia real + contexto bancário + escala + decisões. É exatamente o que a audiência quer ouvir.

---

## 🔄 10. O Perigo de Planejar Demais (Meta-Armadilha)

Vou ser honesto: este é o **terceiro documento de análise** que eu crio para você. Você tem:
- 1 career plan interativo
- 1 career plan para impressão
- 1 comunicado pro gestor
- 3 documentos de análise profunda

Isso é **muito planejamento**. O risco real agora é análise-paralysis:

> Quanto mais você planeja, mais sente que está "fazendo algo". Mas planejo não é execução.

**A pergunta mais importante que ninguém fez:**
> Você já abriu o terminal e criou um projeto dbt? Já commitou o primeiro notebook Fabric? Já gravou o primeiro Cambly?

Se a resposta for "ainda não", então **o próximo passo não é outro documento**. É abrir o VS Code e commitar a primeira linha de código de um projeto público.

### O Teste do "Monday Morning"

Na próxima segunda-feira de manhã, antes de abrir qualquer plano ou documento:

```
1. Abra o GitHub
2. Crie um repo chamado "fabric-lakehouse-starter" ou "dbt-learning"
3. Adicione um README com 3 linhas do que você vai construir
4. Commite
5. Pronto. Você começou.
```

O plano perfeito é o que está em execução. O plano imperfeito em execução bate o plano perfeito na gaveta.

---

## 🔑 Checklist Definitivo: O que Fazer Esta Semana

Não este mês. Não "quando tiver tempo". **Esta semana:**

- [ ] Atualizar `generate_cv.py` com título e dados atuais. Regenerar PDFs.
- [ ] Criar primeiro repo público no GitHub (mesmo que vazio + README)
- [ ] Definir título unificado e atualizar no LinkedIn
- [ ] Instalar Anki e criar 10 cards de conceitos DE/AI
- [ ] Baixar 1 podcast de Data Engineering para ouvir no deslocamento
- [ ] Agendar primeiro Cambly (se ainda não fez)
- [ ] Criar pasta "Carreira" no Obsidian com o template de revisão semanal

> **Se você fizer apenas 3 desses 7 itens, já estará à frente de 90% das pessoas que "planejam" a carreira.**

---

> **Última palavra:** Você não precisa de mais análise. Você precisa de 1 commit, 1 post e 1 hora de construção real. O resto se revela no caminho. Comece feio. Melhore em público. Chegue lá.
