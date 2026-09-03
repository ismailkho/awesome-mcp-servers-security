# 🛡️ Awesome MCP Servers & Security

A developer's reference guide to the Model Context Protocol (MCP) ecosystem: verified servers, real security criteria, and the risks you need to understand before you connect an AI agent to your data, your cloud account, or your codebase.

Every link below was checked against the source repository at time of writing. Entries are labeled **Official** (maintained by the vendor/platform owner), **Community** (third-party, unaffiliated), or **Archived** (no longer maintained — listed only so you know what to avoid or replace).

![Status: Official](https://img.shields.io/badge/status-official-brightgreen) ![Status: Community](https://img.shields.io/badge/status-community-blue) ![Status: Archived](https://img.shields.io/badge/status-archived-red) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

---

## 📑 Contents

- [Why "security" matters for an MCP list](#why-security-matters-for-an-mcp-list)
- [How entries are evaluated](#how-entries-are-evaluated)
- [Official Reference Servers](#-official-reference-servers)
- [Databases & Data Platforms](#️-databases--data-platforms)
- [Cloud & DevOps Infrastructure](#️-cloud--devops-infrastructure)
- [Security & Secrets Management](#-security--secrets-management)
- [Web & Browser Automation](#-web--browser-automation)
- [Communication & Project Management](#-communication--project-management)
- [Payments & Finance](#-payments--finance)
- [Monitoring & Observability](#-monitoring--observability)
- [Search](#-search)
- [MCP Threat Model — What Can Actually Go Wrong](#-mcp-threat-model--what-can-actually-go-wrong)
- [Pre-Installation Security Checklist](#-pre-installation-security-checklist)
- [Security Scanning Tools](#-security-scanning-tools)
- [Related Lists & Further Reading](#-related-lists--further-reading)
- [Contributing](#-contributing)

---

## Why "security" matters for an MCP list

An MCP server is not a passive integration — it's a set of *tools* that an LLM can decide to call on its own, often with your credentials, inside a loop where the model is also reading untrusted content (web pages, tickets, emails, files). That combination is what makes MCP security meaningfully different from "is this npm package trustworthy": the risk isn't just supply-chain, it's what the agent can be tricked into *doing* with the access you granted it.

A list that just says "500 servers, sorted by stars" doesn't help you make that call. This guide tries to surface the three things that actually matter before you `npx` a server into your agent: **who maintains it**, **what it can touch**, and **how it authenticates**.

---

## How entries are evaluated

Instead of a single proprietary "security score" from one vendor, every entry below carries three plain facts you can verify yourself by opening the repo:

| Field | What to look for |
|---|---|
| **Maintainer** | Official (the platform/company itself), Community (independent), or Archived (unmaintained) |
| **Permission level** | Read-only, Read-write, or Execute/Admin (can it run code, delete data, move money?) |
| **Auth** | OAuth (short-lived, scoped, revocable), static API token/PAT, or none |

This isn't a substitute for reading the code — it's a starting filter. A server can be "Official" and still be over-permissioned for your use case; a "Community" server can be excellent and well-audited. Use the [checklist](#-pre-installation-security-checklist) below before installing anything, regardless of label.

---

## 🌟 Official Reference Servers

Maintained directly by the MCP steering group at [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers). These are explicitly documented by the maintainers as **educational reference implementations, not hardened production software** — treat that warning as real.

| Server | Status | Permission | Description |
|---|---|---|---|
| [Everything](https://github.com/modelcontextprotocol/servers/tree/main/src/everything) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Test/demo | Reference/test server exercising prompts, resources, and tools — used to validate MCP clients, not for real workloads. |
| [Fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read (network) | Fetches and converts web pages to Markdown for the model. **Note:** any server that pipes raw web content into the model context is a prompt-injection surface — see the [threat model](#-mcp-threat-model--what-can-actually-go-wrong). |
| [Filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read/write (local) | Local file access, scoped to directories you explicitly allow at startup. Never point it at your whole home directory. |
| [Git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read/write (local repo) | Read, search, and modify local Git repositories. |
| [Memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read/write (local) | Persistent knowledge-graph memory stored locally between sessions. |
| [Sequential Thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) | ![Official](https://img.shields.io/badge/-official-brightgreen) | None (reasoning only) | Structures multi-step reasoning; touches no external systems. |
| [Time](https://github.com/modelcontextprotocol/servers/tree/main/src/time) | ![Official](https://img.shields.io/badge/-official-brightgreen) | None | Timezone and date/time conversion utility. |

### ⚠️ Archived reference servers — do not use as listed

These were moved to [servers-archived](https://github.com/modelcontextprotocol/servers-archived) and **carry no security guarantees or updates**. If an older "awesome MCP" list, tutorial, or blog post links you to one of these, use the vendor-maintained replacement in the right-hand column instead.

| Archived server | Use instead |
|---|---|
| [AWS KB Retrieval](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/aws-kb-retrieval-server) | [AWS Labs MCP](https://github.com/awslabs/mcp) (see [Cloud & DevOps](#️-cloud--devops-infrastructure)) |
| [Brave Search](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/brave-search) | [brave/brave-search-mcp-server](https://github.com/brave/brave-search-mcp-server) — official |
| [EverArt](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/everart) | — (no maintained successor known at time of writing) |
| [GitHub](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/github) | [github/github-mcp-server](https://github.com/github/github-mcp-server) — official |
| [GitLab](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/gitlab) | — check the [official MCP Registry](https://registry.modelcontextprotocol.io/) for a current GitLab-maintained option |
| [Google Drive](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/gdrive) | — check the official MCP Registry |
| [Google Maps](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/google-maps) | — check the official MCP Registry |
| [PostgreSQL](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/postgres) | Actively-maintained community forks exist; audit the fork's commit history before trusting it with a production database |
| [Puppeteer](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/puppeteer) | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) — official, actively maintained |
| [Redis](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/redis) | — check the official MCP Registry |
| [Sentry](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/sentry) | [getsentry/sentry-mcp](https://github.com/getsentry/sentry-mcp) — official |
| [Slack](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/slack) | [zencoderai/slack-mcp-server](https://github.com/zencoderai/slack-mcp-server) — designated successor |
| [SQLite](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/sqlite) | — check the official MCP Registry |

---

## 🗄️ Databases & Data Platforms

| Server | Status | Permission | Auth | Notes |
|---|---|---|---|---|
| [MongoDB](https://github.com/mongodb-js/mongodb-mcp-server) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Configurable read/write | OAuth (Atlas, remote) or token (self-managed, local) | Ships two modes: a hosted Atlas connector over OAuth (no local process), or a local server for self-managed deployments. Supports a confirmation-required list for destructive tools (`drop-database`, `delete-many`, etc.) — turn that on. |

For PostgreSQL, Redis, and SQLite, see the [archived servers table](#️-archived-reference-servers--do-not-use-as-listed) above — none currently has a single canonical official successor, so vet any community replacement against the [checklist](#-pre-installation-security-checklist).

---

## ☁️ Cloud & DevOps Infrastructure

| Server | Status | Permission | Auth | Notes |
|---|---|---|---|---|
| [GitHub MCP Server](https://github.com/github/github-mcp-server) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Configurable (read code/issues/PRs up to full repo admin) | OAuth (hosted, remote) or PAT (local) | GitHub's own server. Prefer the hosted remote + OAuth mode over a long-lived personal access token where your client supports it. |
| [Cloudflare (Code Mode)](https://github.com/cloudflare/mcp) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Configurable, full API surface | OAuth | Exposes the entire Cloudflare API through a token-efficient "code execution" pattern rather than one tool per endpoint. Scope the API token to only the services you need. |
| [Cloudflare (domain-specific servers)](https://github.com/cloudflare/mcp-server-cloudflare) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Varies by product | OAuth | Separate, narrower servers per Cloudflare product (Workers, observability, browser rendering) — use these instead of the full API surface when you only need one area. |
| [Microsoft MCP (Azure catalog)](https://github.com/microsoft/mcp) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Varies by sub-server | Varies (mostly Entra/Azure AD) | Umbrella catalog of Microsoft's official servers: Azure Resource Graph, Azure DevOps, AKS, Microsoft Entra (read-only IT/security scenarios), Microsoft Learn docs, and more. |
| [AWS Labs MCP](https://github.com/awslabs/mcp) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Varies by sub-server | AWS credentials/IAM | AWS's open-source collection of MCP servers. AWS has signaled this repo is being superseded over time by a separate "Agent Toolkit for AWS" with IAM condition keys to distinguish agent actions from human ones — worth checking their docs for the current recommendation before standardizing on either. |

---

## 🔐 Security & Secrets Management

| Server | Status | Permission | Auth | Notes |
|---|---|---|---|---|
| [HashiCorp Vault MCP Server](https://github.com/hashicorp/vault-mcp-server) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read/write secrets & mounts | Vault token | HashiCorp's own server — and HashiCorp's docs explicitly flag it as **beta, local-use only**, warning that depending on the query it may expose secret material to the connected client/LLM, and to **never point it at untrusted MCP clients or models**. This is exactly the kind of vendor-stated caveat this list exists to surface — read it before connecting Vault to any agent. |

This is the category where a badge or star count tells you the least. If you're evaluating a secrets-manager MCP server, the permission level and blast radius (can it read? write? delete? rotate root tokens?) matters more than anything else on this page.

---

## 🌐 Web & Browser Automation

| Server | Status | Permission | Notes |
|---|---|---|---|
| [Playwright MCP](https://github.com/microsoft/playwright-mcp) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Browser control, optional filesystem access | Microsoft's official browser-automation server, using accessibility snapshots instead of screenshots. Supports flags to restrict allowed hosts/origins and to block unrestricted filesystem or `file://` access — leave those restrictions on unless you specifically need them off. |
| [Fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read (network) | See the [Official Reference Servers](#-official-reference-servers) table above. |

Any browser-automation or web-fetch server is a direct pipe from the open internet into your model's context — assume every page it visits is a potential prompt-injection attempt, not just a data source.

---

## 💬 Communication & Project Management

| Server | Status | Permission | Auth | Notes |
|---|---|---|---|---|
| [Notion](https://github.com/makenotion/notion-mcp-server) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Configurable per-integration | Internal integration token (local) or OAuth (hosted remote) | Notion scopes access per-page/database — an integration only sees what's explicitly shared with it. Notion itself notes there is a non-zero risk to workspace data from exposing it to an LLM and recommends a read-only integration where possible. Notion is prioritizing the hosted remote server going forward; the local server here may eventually be sunset. |
| [Slack](https://github.com/zencoderai/slack-mcp-server) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Configurable (channels/messages) | Slack app token | Designated successor to the original reference implementation after it was archived. Scope the Slack app's OAuth scopes to only the channels/actions you need. |
| [Linear](https://linear.app/changelog/2025-05-01-mcp) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Configurable (issues/projects) | OAuth | Linear hosts its own remote MCP server (no self-hosted repo) — several earlier community implementations have since been deprecated by their own authors in favor of it. Use Linear's official endpoint rather than an unmaintained community fork. |
| Discord | — | — | — | No vendor-official Discord MCP server was found as of this writing. Several community implementations exist (search the [official MCP Registry](https://registry.modelcontextprotocol.io/)); because these require a Discord bot token with server-wide permissions, review scopes carefully and prefer the least-privileged bot role available. |

---

## 💳 Payments & Finance

| Server | Status | Permission | Auth | Notes |
|---|---|---|---|---|
| [Stripe](https://github.com/mcp/com.stripe/mcp) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Configurable (payments, customers, refunds) | OAuth | Stripe hosts an official remote MCP server at `mcp.stripe.com` with OAuth-based access, plus official agent plugins/skills. **Treat any MCP server with write access to a payments API as execute/admin-level, full stop** — confirm every irreversible action (refund, charge, payout) outside the model's autonomy, and never wire a community/unofficial payments server into an agent that can act without confirmation. |

---

## 📊 Monitoring & Observability

| Server | Status | Permission | Auth | Notes |
|---|---|---|---|---|
| [Sentry](https://github.com/getsentry/sentry-mcp) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read (issues, traces, performance) | OAuth (hosted remote) or token (stdio) | Sentry's own server, built as middleware over their API and optimized for coding agents. Prefer the hosted OAuth flow over a long-lived stdio token. |
| [Grafana](https://github.com/grafana/mcp-grafana) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read (dashboards, datasources, incidents) | Grafana API key | Search dashboards, query datasources, and work with incidents through Grafana's ecosystem. |

---

## 🔎 Search

| Server | Status | Permission | Notes |
|---|---|---|---|
| [Brave Search](https://github.com/brave/brave-search-mcp-server) | ![Official](https://img.shields.io/badge/-official-brightgreen) | Read (network) | Official replacement for the archived reference implementation. |

---

## 🧨 MCP Threat Model — What Can Actually Go Wrong

This is not an exhaustive academic treatment — see [Further Reading](#-related-lists--further-reading) for that — but the recurring, concrete failure modes worth knowing before you wire up your first agent:

- **Prompt injection via tool output.** Any server that returns content the model reads — a fetched web page, a file, a Slack message, a support ticket — can carry text engineered to redirect the agent ("ignore previous instructions and…"). The server didn't do anything wrong; the *content it faithfully returned* did.
- **Tool poisoning / description spoofing.** A malicious or compromised server can describe its tools in a way that manipulates the model into calling them incorrectly, or that hides destructive behavior behind an innocuous-sounding name. This is why tool descriptions from untrusted or unfamiliar servers should be treated as untrusted input, not documentation.
- **Confused deputy / over-privileged servers.** A server connected with broad credentials (an admin API token, a root Vault token, a full-access GitHub PAT) turns any successful injection into full account compromise. Always scope credentials to the minimum the task needs.
- **Rug-pulls and silent updates.** An `npx`-installed server can change behavior between runs if the maintainer pushes a new version — there's often no review gate between "it worked yesterday" and "it does something different today." Pin versions where your tooling allows it, and prefer servers with a visible release/changelog process.
- **Secret leakage through logs or model context.** Tokens passed via environment variables can end up in server logs, error messages, or even echoed back into the model's context window if a server isn't careful about what it returns.
- **Supply-chain risk in the underlying package.** The MCP layer doesn't change ordinary npm/pip supply-chain risk — a compromised dependency of the server is still a compromised dependency.

---

## ✅ Pre-Installation Security Checklist

Before you add any MCP server — official or community — to a client that an agent can act through autonomously:

- [ ] **Who maintains it, and can you tell?** Is it the platform's own org, or an unrelated individual/company?
- [ ] **What's the actual permission level?** Read-only is materially safer than read-write, which is materially safer than execute/admin. Don't grant more than the task needs.
- [ ] **How does it authenticate?** Prefer OAuth (short-lived, revocable, scoped) over a long-lived static token pasted into a config file.
- [ ] **Is it actively maintained?** Check the last commit date and open-issue response time — an abandoned server gets zero future security fixes.
- [ ] **Does it touch untrusted content?** Web fetch, browser automation, and anything reading third-party-authored text (tickets, emails, PRs from strangers) is a prompt-injection surface — treat its output as untrusted, and keep a human in the loop for anything destructive it might trigger.
- [ ] **Does your client show you the tool call before executing it?** A human-in-the-loop confirmation step for write/execute actions is the single most effective mitigation available today.
- [ ] **What does the vendor's own docs say?** As with HashiCorp Vault above, vendors sometimes explicitly flag beta status or "don't expose this to untrusted models" — that's not boilerplate, read it.

---

## 🔬 Security Scanning Tools

Independent tools exist that scan MCP server repositories and generate an automated risk score. They're a useful *first pass*, not a replacement for the checklist above — each is a single vendor's methodology, and (as with most badge-based scanners) most actively solicit README badge placements as part of their growth, so treat the score as one data point, not a certification.

- **[RepoAI](https://repoai.io)** — scans MCP servers for permission model, OAuth support, dependency count, and maintenance activity, and issues a 0–100 score with an auto-updating badge.
- **[MCPSafe](https://mcpsafe.io)** — runs a multi-model consensus scan and returns an "AI Vulnerability Severity Score" aimed specifically at agentic-AI threats (prompt injection, tool poisoning, secret exfiltration).

Neither tool is affiliated with this list, and inclusion here isn't an endorsement of either score's accuracy — verify their methodology yourself before relying on a badge as a purchasing/adoption signal.

---

## 📚 Related Lists & Further Reading

**Broader server catalogs** (this list stays intentionally curated and security-focused; for raw breadth, these are more comprehensive):
- [Official MCP Registry](https://registry.modelcontextprotocol.io/) — the canonical, MCP-steering-group-run index of published servers. Start here when a server you need isn't on this page.
- [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers)
- [wong2/awesome-mcp-servers](https://github.com/wong2/awesome-mcp-servers)
- [appcypher/awesome-mcp-servers](https://github.com/appcypher/awesome-mcp-servers)

**Security-specific reading:**
- [Puliczek/awesome-mcp-security](https://github.com/Puliczek/awesome-mcp-security) — curated MCP security research, specs, and mitigation write-ups.
- [slowmist/MCP-Security-Checklist](https://github.com/slowmist/MCP-Security-Checklist) — a detailed checklist from a blockchain/Web3 security firm, covering access control, credential management, and least-privilege server design.
- [modelcontextprotocol/servers — SECURITY.md](https://github.com/modelcontextprotocol/servers/blob/main/SECURITY.md) — how to report a vulnerability in the official reference servers.
- [modelcontextprotocol.io](https://modelcontextprotocol.io/) — the protocol specification itself, including the current authorization/OAuth spec.

---

## 🤝 Contributing

Pull requests are welcome. To keep this list useful (and to avoid repeating the mistakes fixed in this rewrite), every submission must include:

1. **A real, reachable repository URL** — checked at submission time, not copied from another list.
2. **Maintainer status** — Official, Community, or Archived, with a one-line justification (e.g., "published under the vendor's GitHub org").
3. **Permission level and auth method** — as described in [How entries are evaluated](#how-entries-are-evaluated).
4. **License** and last-commit recency.

Submissions that can't answer all four will be asked for clarification before merging — this list is only as useful as the accuracy of what's in it.

---

*This list is community-maintained and provided for informational purposes. Always independently verify a server's source, maintainer, and permission scope before connecting it to an AI agent with access to real data or credentials.*
