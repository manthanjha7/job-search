# Foundations Roadmap — Interview-Ready Fundamentals (AI Engineer / AI-PM)

> **Retargeted 1 September 2026.** FDE was ruled out on travel grounds; the target is now the desk-based **AI Engineer / Product Engineer**. The library below needed no content change — Tier 0 (evals, agent anatomy, RAG) *is* the AI-engineering core. Only two things changed: the title, and the practice track (below) now drills an AI-engineering loop — build-with-an-API, debug-a-RAG-pipeline, eval-design — instead of the FDE "vague customer problem" decomposition round.
>
> Created: 18 July 2026 · Parent motion: [[Jobs/FDE/roadmap]] · Horizon: ~1 year (marathon, not sprint)
> Owner: Manthan. This is the **conceptual/theory** layer under the FDE roadmap's **procedural** layer (2 portfolio projects). Projects give you things to build; this gives you the words to explain them cold in an interview.

## The problem this solves
Manthan has **procedural** knowledge (hand him a goal, he ships it with Claude) but a **conceptual/labeling** gap: he's made a thousand GET requests but can't define one. Goal = acquire the **mental models** ("the ways to think") a strong FDE/AI-PM reasons with, so critical/fundamental questions don't catch him.

## Two lanes + one practice track
- **Lane 1 — Fundamentals library (this doc):** durable, compounds, interview-generalizable. ~2 topics/week, sequenced by leverage below.
- **Lane 2 — Context prep (just-in-time, not scheduled):** before a specific interview → study *that* company/product deeply; on a work segment → study *that* domain (e.g. US GAAP). The Peakflo voice-agent miss was a Lane-2 context gap, not a Lane-1 fundamentals gap. Triggered, not pre-learned.
- **Practice track (later, via `/mock-interview`):** the FDE "vague customer problem, 60 min, go" decomposition round is the highest-weight / lowest-pass FDE stage. Drilled closer to applications, not now.

## Hard rules
- **Everything web-sourced and cited** — learn from the real sources below, not from an assistant's memory. Every note carries its source URL. See [[feedback_web_sourced_learning]], [[feedback_research_note_format]].
- Each topic becomes a short first-principles note (like the [[PM/Engineering/System-Design/00-curriculum-overview|System Design]] track), captured in `PM/AI/` or `PM/Engineering/`.
- Foundations ≠ 101. First-principles depth at his level, no beginner hand-holding.

## The insight that set the order
Across FDE, AI-PM, and technical-PM interviews, the #1 most-asked / lowest-faked question is **"How do you know your AI system actually works?"** (evals). That is *also* Manthan's flagged differentiator. So Tier 0 leads with the AI core + his moat, not with "what is a GET request."

---

## Lane 1 — The Fundamentals library (sequenced by leverage)

### Tier 0 — AI core + your moat (start here)
- **Evals & error analysis** — LLM-as-judge (binary, not Likert), golden datasets, offline vs online, error analysis as *the* central activity. [hamel.dev evals FAQ](https://hamel.dev/blog/posts/evals-faq/) · backup [Lenny × Hamel](https://www.lennysnewsletter.com/p/evals-error-analysis-and-better-prompts)
- **Anatomy of an AI agent (agents vs workflows)** — augmented LLM building block; workflow patterns (chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer) vs agentic loops. [Anthropic — Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents)
- **RAG vs fine-tune vs prompt (decision framework)** — when each wins. ⚠️ best treatment is book-gated (Chip Huyen, *AI Engineering* Ch.7); web sourcing thinner. [Pinecone chunking](https://www.pinecone.io/learn/chunking-strategies/) · [Redis: fine-tune embeddings for RAG](https://redis.io/blog/get-better-rag-by-fine-tuning-embedding-models/)

### Tier 1 — The CS floor (the "what is a GET request" gap)
- **HTTP request lifecycle** — DNS → TCP → TLS → request → response, the round trip behind every GET. [MDN — Overview of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview)
- **HTTP methods** — GET (safe/idempotent), POST (create), PUT (replace/idempotent), PATCH. [MDN — Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods)
- **Status codes** — 1xx–5xx, "what actually broke." [MDN — Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status)
- **Headers** — Content-Type, Authorization, Cache-Control, Set-Cookie. [MDN — Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers)
- **Statelessness** — why cookies/tokens exist, why stateless scales. [restfulapi.net — Statelessness](https://restfulapi.net/statelessness/)
- **Client-server model** — clients initiate, servers hold resources. [GeeksforGeeks](https://www.geeksforgeeks.org/system-design/client-server-model/)
- **REST / API design** — resource URLs, verbs, statelessness constraint. [restfulapi.net](https://restfulapi.net/) · [roadmap.sh/api-design](https://roadmap.sh/api-design)
- **DNS** — name → IP, first hop, "why is the site down." [Cloudflare — What is DNS](https://www.cloudflare.com/learning/dns/what-is-dns/)
- **TLS / HTTPS** — the handshake, HTTP over TLS. [Cloudflare — TLS handshake](https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/)
- **Cookies, sessions, tokens** — "how does the server remember me." [MDN — Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Cookies)
- **AuthN vs AuthZ (OAuth / JWT / SAML)** — who you are vs what you can do. [Auth0 — SAML vs OAuth](https://auth0.com/intro-to-iam/saml-vs-oauth)
- **Latency vs throughput** — the tradeoff; near-guaranteed FDE probe. [cs.fyi](https://cs.fyi/guide/latency-vs-throughput)

### Tier 2 — Systems / backend
- **Database (SQL vs NoSQL)** — when to pick which. [AWS — What is a Database](https://aws.amazon.com/what-is/database/)
- **Indexes** — B-tree, why "just add an index" isn't free. [Use The Index, Luke](https://use-the-index-luke.com/sql/anatomy)
- **Transactions / ACID** — all-or-nothing (debit/credit). [Wikipedia — ACID](https://en.wikipedia.org/wiki/ACID)
- **Caching** — cache-aside / write-through / write-behind (Redis). [ByteByteGo — Learn Cache](https://bytebytego.com/guides/learn-cache/)
- **Message queues** — decouple producers/consumers, background work. [AWS — Message Queue](https://aws.amazon.com/message-queue/)
- **Load balancing** — distribute traffic, stay available. [NGINX docs](https://docs.nginx.com/nginx/admin-guide/load-balancer/http-load-balancer/)
- **Horizontal vs vertical scaling** — the two "how would you scale" levers. [GeeksforGeeks](https://www.geeksforgeeks.org/system-design/system-design-horizontal-and-vertical-scaling/)
- **CAP theorem** — CP vs AP under partition. [GeeksforGeeks](https://www.geeksforgeeks.org/system-design/cap-theorem-in-system-design/)
- **Idempotency** — retry-safe; payment idempotency keys (fintech-relevant). [Stripe — Idempotency](https://stripe.com/blog/idempotency)
- **The layers a feature crosses** — frontend → API → service → DB → workers; where a bug/bottleneck lives. [roadmap.sh/backend](https://roadmap.sh/backend)
- **Failure modes / observability** — logging vs monitoring vs observability; Four Golden Signals. [Google SRE Book, Ch.6](https://sre.google/sre-book/monitoring-distributed-systems/)

### Tier 3 — LLM mechanics (deeper)
- **Tokens, context window, temperature** — the "physics": cost, limits, output behavior. [MLQ — Tokens & Context Windows](https://blog.mlq.ai/tokens-context-window-llms/) · [IBM — Context window](https://www.ibm.com/think/topics/context-window)
- **Tokenization from first principles** — why it exists + failure modes. [Karpathy — Let's Build the GPT Tokenizer](https://www.youtube.com/watch?v=zduSFxRajkE)
- **Why hallucination happens** — mechanistic + statistical, not "it makes stuff up." [OpenAI — Why LMs hallucinate](https://openai.com/index/why-language-models-hallucinate/)
- **Embeddings + vector search** — semantic similarity as vector proximity. [HuggingFace — Sentence Transformers](https://huggingface.co/docs/hub/en/sentence-transformers)
- **Chunking** — the first-order RAG lever. [Pinecone — Chunking](https://www.pinecone.io/learn/chunking-strategies/)
- **Context engineering** — curating the whole context window, not just the prompt. [Anthropic — Effective context engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- **Prompt engineering** — the base layer. [Claude — Prompt engineering overview](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview)
- **Tool use / function calling** — how a chatbot becomes an agent that does things (model picks, your code executes). [OpenAI — Function calling](https://developers.openai.com/api/docs/guides/function-calling) · [Claude — Tool use](https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview)
- **MCP** — "USB-C for AI"; tools/resources/prompts. [Anthropic — Introducing MCP](https://www.anthropic.com/news/model-context-protocol) · [modelcontextprotocol.io](https://modelcontextprotocol.io/)
- **Prompt injection / the "lethal trifecta"** — real risk once an agent reads untrusted content + has tools + can act. [Simon Willison — prompt injection series](https://simonwillison.net/series/prompt-injection/)

### Tier 4 — FDE-specific (integration / deploy / cloud / data)
- **What the FDE role actually is** — embedded, ~60-80% customer interaction, 20-50% travel. [Palantir — Day in the life of an FDSE](https://blog.palantir.com/a-day-in-the-life-of-a-palantir-forward-deployed-software-engineer-45ef2de257b1) · [Pragmatic Engineer — FDEs](https://newsletter.pragmaticengineer.com/p/forward-deployed-engineers)
- **Integration patterns (REST / webhooks / polling)** — pull vs push. [freeCodeCamp — API integration patterns](https://www.freecodecamp.org/news/api-integration-patterns/) · [Stripe — Webhooks](https://docs.stripe.com/webhooks)
- **ETL vs ELT / data pipelines** — get the customer's data into the system. [AWS — ETL vs ELT](https://aws.amazon.com/compare/the-difference-between-etl-and-elt/)
- **OAuth 2.0** — delegated authorization, scoped expiring tokens. [Auth0 — What is OAuth 2.0](https://auth0.com/intro-to-iam/what-is-oauth-2)
- **SAML / enterprise SSO** — "sign in with your company account." [WorkOS — SAML explained](https://workos.com/blog/what-is-saml-authentication-sso)
- **API keys & secrets management** — never hardcode; vault, rotate, least privilege. [OWASP — Secrets Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html)
- **VPC** — the isolated network you're handed keys to. [AWS — What is VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- **IAM** — principal → role → resource permissions. [AWS — What is IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- **Containers / Docker** — portable app + deps, solves "works on my machine." [Docker — What is a container](https://docs.docker.com/get-started/docker-concepts/the-basics/what-is-a-container/)
- **Kubernetes** — container orchestration; named in OpenAI's FDE stack. [kubernetes.io — Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- **Deploying into a customer's cloud (single-tenant / customer VPC)** — ⚠️ vendor-sourced (no canonical spec). [Northflank](https://northflank.com/blog/deploy-saas-in-customer-vpc)
- **Dev / staging / prod environments** — the promotion flow. [Northflank](https://northflank.com/blog/what-are-dev-qa-preview-test-staging-and-production-environments)
- **Data warehouse (BigQuery / Snowflake)** — analytical, not transactional. [DataCamp — BigQuery vs Snowflake](https://www.datacamp.com/blog/google-bigquery-vs-snowflake)
- **dbt** — the "T" in ELT, SQL models on the warehouse. [dbt docs — What is dbt](https://docs.getdbt.com/docs/introduction)
- **Apache Airflow** — DAG-based pipeline orchestration. [Airflow docs](https://airflow.apache.org/docs/apache-airflow/stable/index.html)

### Named gap — Voice agents (from the Peakflo interview)
- **Voice agent architecture (STT → LLM → TTS + orchestrator)** — ⚠️ vendor-sourced. [LiveKit — Voice agent architecture](https://livekit.com/blog/voice-agent-architecture-stt-llm-tts-pipelines-explained)
- **Latency budget (~300-500ms) + streaming/overlapping stages.** [Chanl — Voice AI latency budget](https://www.channel.tel/es/blog/voice-ai-pipeline-stt-tts-latency-budget)
- **Interruption / barge-in handling (VAD, backchanneling).** [LiveKit — Adaptive interruption handling](https://docs.livekit.io/agents/logic/turns/adaptive-interruption-handling/)

---

## Weekly log (2 topics/week)
Each week: learn the topics from the sources above, capture a cited note in `PM/AI/` or `PM/Engineering/`, tick here.

- **W30 (18-24 Jul) — Week 1:** [ ] Anatomy of an AI agent (agents vs workflows) · [ ] HTTP request lifecycle
- **W31 (25-31 Jul) — Week 2 (planned):** evals & error analysis · REST / API design
- **W32 — Week 3 (planned):** RAG vs fine-tune vs prompt · HTTP methods + status codes
- *(continue ~2/week; reorder freely as interviews / work pull topics forward)*

## Cadence & fit
- ~2 topics/week, ~1 year to deep coverage. Lives in the **Learning** slot of the weekly plan; interview-readiness is the driver (Career/FDE).
- Reorder on demand: if an interview or a work segment needs a topic, pull it forward (that's Lane 2 bleeding into Lane 1).
