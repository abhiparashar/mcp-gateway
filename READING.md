# Reading list — how big tech builds AI in real life

Real engineering posts from companies running AI in production.
Each line: company, post, and the one idea to take away.

Links checked on 2026-10-05. Ones marked † block automated checkers but open fine in a browser.

---

## 1. Start here: the basics (read in this order)

| # | Post | Take away |
|---|---|---|
| 1 | Anthropic — [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) | Simple patterns beat complex frameworks; workflow vs agent |
| 2 | Chip Huyen — [Building a Generative AI Platform](https://huyenchip.com/2024/07/25/genai-platform.html) | The parts of an AI platform (context, guardrails, router, gateway, cache) and the order to add them |
| 3 | Eugene Yan — [Patterns for Building LLM-based Systems](https://eugeneyan.com/writing/llm-patterns/) | 7 patterns: evals, RAG, fine-tuning, caching, guardrails, defensive UX, feedback |
| 4 | Hamel Husain — [Your AI Product Needs Evals](https://hamel.dev/blog/posts/evals/) | Failed AI products almost always skipped evaluation |
| 5 | Applied LLMs — [What We've Learned From A Year of Building with LLMs](https://applied-llms.org/) | Practical lessons from many practitioners in one place |
| 6 | LinkedIn — [Musings on building a Generative AI product](https://www.linkedin.com/blog/engineering/generative-ai/musings-on-building-a-generative-ai-product) | The first 80% is fast; the last 20% (quality, evals, calling internal APIs) takes most of the time |

## 2. Agents and tools

| Post | Take away |
|---|---|
| Anthropic — [Writing effective tools for agents](https://www.anthropic.com/engineering/writing-tools-for-agents) | How to design tools an LLM can actually use well |
| Anthropic — [Effective context engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) | Context is a limited budget; spend it carefully |
| Anthropic — [Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) | How to keep agents on track over hours of work |
| Shopify — [Lessons from Shopify Sidekick](https://shopify.engineering/building-production-ready-agentic-systems) | One agent with many tools; "just-in-time" instructions returned with tool results |
| Duolingo — [Building Duolingo's agent platform](https://blog.duolingo.com/production-ready-ai-agent-platform) | Making production-ready agents the default for every team |
| Stripe — [Knowledge AI Platform](https://stripe.dev/blog/meet-stripes-knowledge-ai-platform) | One agent platform for non-coding knowledge work |
| Grab — [LLM-Kit agent framework](https://www.infoq.com/news/2026/09/grab-agent-platform/) (InfoQ) | Shared framework to ship agents faster |
| OpenAI — [Cookbook](https://developers.openai.com/cookbook) | Runnable recipes for agents, tools, RAG, evals |

## 3. MCP and AI gateways (your project)

| Post | Take away |
|---|---|
| Uber — [Designing MCP Gateway](https://www.uber.com/us/en/blog/designing-mcp-gateway/) | The design we are building: registry, proxy, AutoCrawler, Omni MCP |
| Cloudflare — [Scaling MCP adoption: reference architecture](https://blog.cloudflare.com/enterprise-mcp) | Governing MCP across a company; Code Mode to cut tokens |
| Cloudflare — [The AI engineering stack we built internally](https://blog.cloudflare.com/internal-ai-engineering-stack) | All internal AI traffic through one AI gateway |
| Block — [Playbook for designing MCP servers](https://engineering.block.xyz/blog/blocks-playbook-for-designing-mcp-servers) | Lessons from 60+ MCP servers |
| Block — [Build MCP tools like ogres, with layers](https://engineering.block.xyz/blog/build-mcp-tools-like-ogres-with-layers) | Split tools into discovery, planning, execution layers |
| Instacart — [Maple: large-scale LLM batch processing](https://www.instacart.com/company/tech-innovation/simplifying-large-scale-llm-processing-across-instacart-with-maple) | Central batch service + internal AI gateway; ~50% cheaper than real-time calls |

## 4. RAG (giving AI your company's knowledge)

| Post | Take away |
|---|---|
| Dropbox — [Building Dash: RAG and multi-step agents](https://dropbox.tech/machine-learning/building-dash-rag-multi-step-ai-agents-business-users) | Choosing a retrieval system for speed vs freshness |
| Dropbox — [How Dash uses context engineering](https://dropbox.tech/machine-learning/how-dash-uses-context-engineering-for-smarter-ai) | Why plain RAG stopped being enough |
| Slack — [How we built Slack AI to be secure and private](https://slack.engineering/how-we-built-slack-ai-to-be-secure-and-private/) | RAG instead of training on customer data; AI only sees what the user can see |
| DoorDash — [LLM-based Dasher support automation](https://careersatdoordash.com/blog/large-language-modules-based-dasher-support-automation/) † | RAG + guardrail + LLM judge; big drop in hallucinations |
| DoorDash — [Building DoorDash Assistant](https://careersatdoordash.com/blog/building-doordash-assistant-an-engineering-overview/) † | Engineering overview of a consumer AI assistant |

## 5. Text-to-SQL (asking a database in plain English)

| Post | Take away |
|---|---|
| Uber — [QueryGPT](https://www.uber.com/us/en/blog/query-gpt/) | From a hackathon RAG to a multi-agent SQL pipeline |
| Pinterest — [How we built Text-to-SQL](https://medium.com/pinterest-engineering/how-we-built-text-to-sql-at-pinterest-30bad30dabff) † | Finding the right tables is the hard part |
| Pinterest — [Unified context-intent embeddings for Text-to-SQL](https://medium.com/pinterest-engineering/unified-context-intent-embeddings-for-scalable-text-to-sql-793635e60aac) † | The next version, at scale |

## 6. Evaluation (how to know the AI is good)

| Post | Take away |
|---|---|
| Airbnb — [Eval-driven development](https://airbnb.tech/ai-ml/eval-driven-development-lessons-from-evaluating-genai-at-scale/) | Write the eval first, then change prompts or models |
| Notion — [Speed, structure, and smarts: the Notion AI way](https://www.notion.com/blog/speed-structure-and-smarts-the-notion-ai-way) | LLM-as-a-judge run by dedicated AI data specialists |
| Discord — [Developing rapidly with generative AI](https://discord.com/blog/developing-rapidly-with-generative-ai) | Prototype with a big model, judge with an LLM, then scale cheaper |
| Airbnb — [Automation Platform v2](https://medium.com/airbnb-engineering/automation-platform-v2-improving-conversational-ai-at-airbnb-d86c9386e0cb) † | Mixing LLMs with fixed workflows, plus guardrails |

## 7. Coding agents

| Post | Take away |
|---|---|
| Stripe — [Minions: one-shot coding agents](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents) and [Part 2](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents-part-2) | 1000+ merged PRs a week, humans still review |
| Ramp — [Why we built our own background agent](https://engineering.ramp.com/post/why-we-built-our-background-agent) | The agent proves its own work: tests, telemetry, screenshots |
| GitHub — [Meet the new Copilot coding agent](https://github.blog/news-insights/product-news/github-copilot-meet-the-new-coding-agent/) | Agent runs in a throwaway VM via GitHub Actions |
| GitHub — [Working with the LLMs behind Copilot](https://github.blog/ai-and-ml/github-copilot/inside-github-working-with-the-llms-behind-github-copilot/) | How Copilot started: chat failed, in-editor completion won |

## 8. Big models and infrastructure

| Post | Take away |
|---|---|
| Netflix — [Foundation model for personalized recommendation](https://netflixtechblog.com/foundation-model-for-personalized-recommendation-1a0bd8e02d39) † | One big LLM-style model instead of hundreds of small ones |
| Meta — [Building Meta's GenAI infrastructure](https://engineering.fb.com/2024/03/12/data-center-engineering/building-metas-genai-infrastructure/) | Two 24,576-GPU clusters used to train Llama 3 |
| Google — [Looking back at speculative decoding](https://research.google/blog/looking-back-at-speculative-decoding/) | Faster answers, same quality, fewer machines (used in AI Overviews) |

## 9. Keep finding more

| Resource | What it is |
|---|---|
| [ZenML LLMOps Database](https://www.zenml.io/llmops-database) | Hundreds of company AI case studies, searchable |
| [llms-in-production](https://github.com/primaprashant/llms-in-production) | Curated list of engineering blogs on real LLM use |
| [Anthropic Engineering](https://www.anthropic.com/engineering) | New agent engineering posts |
| [DoorDash AI/ML blog](https://careersatdoordash.com/blog/category/data-science-and-machine-learning) † | Frequent production AI posts |
| [Ramp Builders](https://engineering.ramp.com/) | Agents for on-call, data analysis, coding |
