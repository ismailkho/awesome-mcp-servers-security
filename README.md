# 🛡️ Awesome MCP Servers & Security

**A developer's reference guide to the Model Context Protocol (MCP) ecosystem** — 16 categories, 180+ servers, every one security-scored against a public methodology.

This guide is built and maintained by the team behind **[RepoAI](https://repoai.io)**, an independent, editorial MCP directory. Every entry below links to its full security breakdown, install configs, and editorial verdict on RepoAI — that's not hidden, it's the point: we built the scanner, so we're using it to build the list. You can read exactly how the scoring works before you trust a single number — see [How This Guide Works](#-how-this-guide-works) below.

[![Powered by RepoAI](https://img.shields.io/badge/security%20data-RepoAI-1E40AF)](https://repoai.io) [![Methodology](https://img.shields.io/badge/methodology-15%20signals-informational)](https://repoai.io/methodology) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

---

## 📑 Contents

- [How This Guide Works](#-how-this-guide-works)
- [Databases](#-databases) · [Developer Tools](#-developer-tools) · [Cloud & Infrastructure](#️-cloud--infrastructure) · [Security](#-security)
- [Secrets Management](#-secrets-management) · [Identity & Authentication](#-identity--authentication) · [Browser & Automation](#-browser--automation) · [AI & ML](#-ai--ml)
- [Version Control](#-version-control) · [CI/CD](#-cicd) · [Search & Data](#-search--data) · [File Systems](#-file-systems)
- [Communication](#-communication) · [Project Management](#-project-management) · [Monitoring & Observability](#-monitoring--observability) · [Payments & Commerce](#-payments--commerce)
- [Official Reference Servers & What's Archived](#-official-reference-servers--whats-archived)
- [MCP Threat Model](#-mcp-threat-model)
- [Pre-Installation Checklist](#-pre-installation-checklist)
- [Contributing](#-contributing)

---

## How This Guide Works

Every MCP server on this page carries a **0–100 security score**, computed from 15 public signals — 10 about repository health (official maintainer, active commits, contributor count, license, dependency footprint) and 5 about how the MCP itself behaves (read-only mode, OAuth support, how many of its tools can execute/delete/write, whether auth exists at all). It's a plain sum of points, no hidden weighting — the full breakdown of every check is public at **[repoai.io/methodology](https://repoai.io/methodology)**.

**Read this before you trust any score:** it's a *trust signal built from public repository data*, not a penetration test. It doesn't run the code, and dependency/tool-risk detection is currently manual or AI-assisted review rather than fully automated static analysis. Treat 🟢 as "worth a closer look," not "guaranteed safe" — the [checklist](#-pre-installation-checklist) at the bottom is still yours to run.

**Legend used in every table below:**

| Symbol | Meaning |
|---|---|
| 🏛️ | **Official** — maintained by the vendor/platform itself, not a third party |
| 🟢 80–100 | Safe — strong signals across the board |
| 🟡 60–79 | Use with caution — check permissions and auth before connecting |
| 🔴 0–59 | High risk — review the source and scope access tightly, or skip it |

Click any server name to see its full breakdown: exact permission list, which tools are flagged execute/delete/write, auth method, and a plain-English editorial verdict. Rankings below are sorted by security score, high to low, exactly as they rank on RepoAI.

---

## 🗄️ Databases

*Query and manage relational and NoSQL databases. 40 servers tracked — top 12 below.* [See all 40 →](https://repoai.io/category/databases)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Supabase MCP Server](https://repoai.io/mcp/mcp) 🏛️ | 🟢 100 | 2,833 | Supabase project database management through AI assistants. |
| 2 | [ClickHouse MCP Server](https://repoai.io/mcp/mcp-clickhouse) 🏛️ | 🟢 93 | 832 | ClickHouse database queries and chDB engine operations via MCP. |
| 3 | [Qdrant MCP Server](https://repoai.io/mcp/mcp-server-qdrant) | 🟡 73 | 1,485 | Qdrant vector search engine integration for semantic memory and retrieval. |
| 4 | [Neo4j MCP Server](https://repoai.io/mcp/mcp-neo4j) 🏛️ | 🟡 65 | 983 | Graph database management and natural language querying. |
| 5 | [MongoDB MCP Server](https://repoai.io/mcp/mongodb-mcp-server) | 🟡 60 | 1,087 | Query, inspect, and manage MongoDB collections via natural language. |
| 6 | [DBHub MCP Server](https://repoai.io/mcp/dbhub) | 🔴 58 | 3,231 | SQL databases and schema exploration for MCP-compatible clients. |
| 7 | [PostgreSQL MCP Server](https://repoai.io/mcp/postgres-mcp) | 🔴 55 | 3,139 | PostgreSQL health checks, index tuning, and schema analysis for AI agents. |
| 8 | [GraphQL MCP Server](https://repoai.io/mcp/mcp-graphql) | 🔴 54 | 403 | GraphQL API schema introspection and query execution. |
| 9 | [Toolbox MCP Server](https://repoai.io/mcp/mcp-toolbox) | 🔴 53 | 16,034 | Database connectivity with a flexible custom-tools framework. |
| 10 | [SSH Manager MCP Server](https://repoai.io/mcp/mcp-ssh-manager) | 🔴 53 | 431 | SSH remote server management — execute commands, sync files. |
| 11 | [Pg AIGuide MCP Server](https://repoai.io/mcp/pg-aiguide) | 🔴 50 | 1,797 | PostgreSQL manuals and curated best practices for AI-generated schemas. |
| 12 | [Supabase MCP Server (community)](https://repoai.io/mcp/supabase-mcp-server) | 🔴 50 | 830 | Run SQL queries and manage Supabase projects via an alternate implementation. |

---

## 🛠 Developer Tools

*Git, CI/CD, IDEs, and other build-time tooling. 50 servers tracked — top 12 below.* [See all 50 →](https://repoai.io/category/developer-tools)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Context Forge MCP Server](https://repoai.io/mcp/mcp-context-forge) 🏛️ | 🟡 86 | 4,143 | Registry and proxy federating MCP, A2A, and API services for AI observability. |
| 2 | [Xcodebuild MCP Server](https://repoai.io/mcp/xcodebuildmcp) 🏛️ | 🟡 76 | 6,171 | iOS/macOS project builds via AI-driven command execution. |
| 3 | [C# SDK MCP Server](https://repoai.io/mcp/csharp-sdk) 🏛️ | 🟡 76 | 4,414 | Build .NET-based MCP clients and servers with modular libraries. |
| 4 | [MCPC MCP Server](https://repoai.io/mcp/mcpc) 🏛️ | 🟡 76 | 747 | Execute MCP protocol operations directly from your terminal. |
| 5 | [Python SDK MCP Server](https://repoai.io/mcp/python-sdk) 🏛️ | 🟡 71 | 23,896 | Build MCP-compliant servers and clients in Python. |
| 6 | [TypeScript SDK MCP Server](https://repoai.io/mcp/typescript-sdk) 🏛️ | 🟡 71 | 13,076 | Build MCP servers/clients for Node.js, Bun, and Deno. |
| 7 | [Rust SDK MCP Server](https://repoai.io/mcp/rust-sdk) 🏛️ | 🟡 71 | 3,758 | Rust development for MCP servers with full async protocol support. |
| 8 | [Java SDK MCP Server](https://repoai.io/mcp/java-sdk) 🏛️ | 🟡 71 | 3,638 | Java applications interfacing with AI models via MCP. |
| 9 | [QuickBooks Online MCP Server](https://repoai.io/mcp/quickbooks-online-mcp-server) | 🟡 70 | 335 | Financial data and reporting access via the QuickBooks Online API. |
| 10 | [Meta MCP Server](https://repoai.io/mcp/metamcp) | 🟡 68 | 2,555 | Unified aggregator/gateway for MCP services via Docker. |
| 11 | [Ruby SDK MCP Server](https://repoai.io/mcp/ruby-sdk) 🏛️ | 🟡 66 | 877 | Build MCP-compliant servers and clients in native Ruby. |
| 12 | [MCPTools MCP Server](https://repoai.io/mcp/mcptools) | 🔴 64 | 1,614 | CLI for discovering, testing, and managing MCP server tools. |

---

## ☁️ Cloud & Infrastructure

*Cloud providers, containers, and infra APIs. 23 servers tracked — top 13 below.* [See all 23 →](https://repoai.io/category/cloud-infrastructure)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [AWS Labs MCP Server](https://repoai.io/mcp/awslabs-mcp) 🏛️ | 🟡 76 | 9,504 | AWS infrastructure and service management for your local AI context. |
| 2 | [Cloudflare MCP Server](https://repoai.io/mcp/mcp-server-cloudflare) 🏛️ | 🟡 73 | 3,990 | Manage Cloudflare Workers, logs, and services via natural language. |
| 3 | [Microsoft MCP Server](https://repoai.io/mcp/microsoft-mcp) 🏛️ | 🟡 73 | 3,502 | Azure and Microsoft Fabric integration for LLMs. |
| 4 | [Jcodemunch MCP Server](https://repoai.io/mcp/jcodemunch-mcp) | 🔴 58 | 2,225 | GitHub source retrieval using tree-sitter AST parsing to cut token usage. |
| 5 | [FastAPI MCP Server](https://repoai.io/mcp/fastapi-mcp) | 🔴 57 | 11,956 | Expose FastAPI endpoints as MCP tools. |
| 6 | [Agent Scan MCP Server](https://repoai.io/mcp/agent-scan) | 🔴 55 | 2,819 | Scan agent components, MCP servers, and skills for prompt injection and vulnerabilities. |
| 7 | [Azure DevOps MCP Server](https://repoai.io/mcp/azure-devops-mcp) | 🔴 55 | 1,910 | Azure DevOps projects, builds, repos, and wiki content for AI workflows. |
| 8 | [Kubernetes MCP Server](https://repoai.io/mcp/kubernetes-mcp-server) | 🔴 55 | 1,849 | Kubernetes and OpenShift cluster management via MCP. |
| 9 | [StackQL MCP Server](https://repoai.io/mcp/stackql) | 🔴 48 | 866 | Query cloud infrastructure resources using SQL. |
| 10 | [UniFi MCP Server](https://repoai.io/mcp/unifi-mcp) | 🔴 48 | 660 | UniFi network, protect, and access devices via agentic workflows. |
| 11 | [Render MCP Server](https://repoai.io/mcp/render-mcp) | 🔴 48 | 148 | Manage Render services and databases from an LLM interface. |
| 12 | [Buildkite MCP Server](https://repoai.io/mcp/buildkite-mcp-server) | 🔴 45 | 52 | Buildkite pipelines, builds, jobs, and test data for AI agents. |
| 13 | [Grafana MCP Server](https://repoai.io/mcp/mcp-grafana) 🏛️ | 🔴 43 | 3,295 | Grafana dashboards and datasources accessible via MCP. |

---

## 🔓 Security

*Reverse engineering and offensive security tooling. 19 servers tracked — top 12 below.* [See all 19 →](https://repoai.io/category/security)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [PortSwigger MCP Server](https://repoai.io/mcp/portswigger-mcp-server) 🏛️ | 🟡 73 | 1,012 | Burp Suite interactions managed directly within AI clients. |
| 2 | [Security Hub MCP Server](https://repoai.io/mcp/mcp-security-hub) | 🔴 62 | 752 | Nmap, Nuclei, and Radare2 for AI-driven vulnerability assessment. |
| 3 | [Reverse Engineering Assistant MCP Server](https://repoai.io/mcp/reverse-engineering-assistant) | 🔴 55 | 790 | Ghidra reverse-engineering tasks powered by LLM integration. |
| 4 | [CVE MCP Server](https://repoai.io/mcp/cve-mcp-server) | 🔴 53 | 1,095 | Vulnerability intelligence across 24 data sources via 28 tools. |
| 5 | [Snyk MCP Server](https://repoai.io/mcp/snyk) | 🔴 48 | 5,627 | Scan application code, containers, and IaC for vulnerabilities. |
| 6 | [Ghidra MCP Server](https://repoai.io/mcp/ghidramcp) | 🔴 43 | 9,585 | Expose core Ghidra reverse-engineering tools to your AI assistant. |
| 7 | [Apktool MCP Server](https://repoai.io/mcp/apktool-mcp-server) | 🔴 40 | 626 | Android APK analysis and reverse engineering via LLM integration. |
| 8 | [Shodan MCP Server](https://repoai.io/mcp/mcp-shodan) | 🔴 37 | 146 | Query Shodan for IP reconnaissance and device discovery. |
| 9 | [Kali MCP Server](https://repoai.io/mcp/mcp-kali-server) | 🔴 34 | 779 | Execute Linux terminal commands and offensive-security tools via AI. |
| 10 | [IDA Pro MCP Server](https://repoai.io/mcp/ida-pro-mcp) | 🔴 28 | 10,928 | IDA Pro binary reversing integrated into your AI coding environment. |
| 11 | [Ghidra MCP Server (P-code)](https://repoai.io/mcp/ghidra-mcp) | 🔴 25 | 2,959 | Reverse engineering and P-code analysis via AI workflows. |
| 12 | [MCP Shield](https://repoai.io/mcp/mcp-shield) | 🔴 23 | 554 | Detects tool poisoning, exfiltration channels, and cross-origin escalation in MCP configs — worth running against your own config. |

> ⚠️ Offensive-security tooling (Kali, Metasploit, Hexstrike AI, etc.) grants an agent the ability to run real exploitation tools. Never connect this category to an agent without a human confirming every action — see the [threat model](#-mcp-threat-model).

---

## 🔐 Secrets Management

*Credential vaults and secret storage integrations. All 10 tracked servers below.* [See category →](https://repoai.io/category/secrets-management)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Bitwarden MCP Server](https://repoai.io/mcp/bitwarden-mcp-server) 🏛️ | 🔴 36 | 215 | Vault management and organization administration for AI assistants. |
| 2 | [Warden MCP Server](https://repoai.io/mcp/warden-mcp) 🏛️ | 🔴 26 | 12 | Vaultwarden and Bitwarden vault item management. |
| 3 | [Cloak MCP Server](https://repoai.io/mcp/cloakmcp) | 🔴 24 | 5 | Local-first secret sanitization — intercepts credentials before they reach the LLM. |
| 4 | [MCPGuard MCP Server](https://repoai.io/mcp/mcpguard) | 🔴 24 | 4 | Replaces plaintext API keys with secure vault references. |
| 5 | [Secrets Vault MCP Server](https://repoai.io/mcp/mcp-secrets-vault) | 🔴 24 | 4 | Manage API keys and tokens without exposing raw secret values. |
| 6 | [OPGen MCP Server](https://repoai.io/mcp/opgen-mcp-server) | 🔴 18 | 5 | Generate passwords using the 1Password SPG algorithm. |
| 7 | [1Password MCP Server](https://repoai.io/mcp/1password-mcp) | 🔴 8 | 18 | 1Password vault management through a service-account interface. |
| 8 | [Bitwarden MCP Server (Librando)](https://repoai.io/mcp/giuliolibrando-bitwarden-mcp-server) | 🔴 0 | 2 | Bitwarden/Vaultwarden item search, creation, and management. |
| 9 | [OP MCP Server](https://repoai.io/mcp/op-mcp) | 🔴 0 | 2 | 1Password CLI integration for managing secrets, vaults, and users. |
| 10 | [1Password MCP Server (Branco)](https://repoai.io/mcp/rui-branco-1password-mcp) | 🔴 0 | 1 | 1Password vault access with multi-account support, local execution. |

> **Also worth knowing:** [HashiCorp Vault MCP Server](https://github.com/hashicorp/vault-mcp-server) 🏛️ — not yet indexed in this directory at time of writing, but it's HashiCorp's own official server. HashiCorp's own docs flag it as **beta, local-use only**, and explicitly warn it may expose secret material to whatever client/LLM is connected — read that warning before you connect Vault to any agent.
>
> This is the single category where the score should matter least to your decision — permission level and blast radius (read? write? delete? rotate root tokens?) matter more than any 0–100 number. Every entry above is community-maintained except the two flagged 🏛️; read the source before trusting any of them with real credentials.

---

## 🪪 Identity & Authentication

*SSO, identity providers, and access management. 15 servers tracked — top 10 below.* [See all 15 →](https://repoai.io/category/identity-auth)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Auth0 MCP Server](https://repoai.io/mcp/auth0-mcp-server) | 🔴 60 | 112 | Auth0 tenant management for app, action, and user configuration. |
| 2 | [Clerk Tools MCP Server](https://repoai.io/mcp/mcp-tools) | 🔴 50 | 47 | Clerk authentication patterns for MCP clients and servers. |
| 3 | [OIDC Provider MCP Server](https://repoai.io/mcp/mcp-oidc-provider) | 🔴 48 | 13 | OIDC-compliant identity provider middleware for remote MCP authorization. |
| 4 | [Auth Proxy MCP Server](https://repoai.io/mcp/mcp-auth-proxy) | 🔴 45 | 13 | OAuth 2.1 authorization for private MCP servers via OIDC providers. |
| 5 | [SSO MCP Server](https://repoai.io/mcp/mcp-sso) | 🔴 45 | 8 | OAuth 2.1 bridging for MCP servers, replacing static API keys. |
| 6 | [Pipes MCP Server](https://repoai.io/mcp/pipes-mcp) 🏛️ | 🔴 41 | 29 | Third-party API access with human-approved, provider-scoped control. |
| 7 | [MCPKeycloakSPI MCP Server](https://repoai.io/mcp/mcpkeycloakspi) | 🔴 38 | 8 | Keycloak identity event sync for Maritime Connectivity Platform brokers. |
| 8 | [FGA MCP Server](https://repoai.io/mcp/fga-mcp) | 🔴 38 | 8 | OpenFGA and Auth0 FGA authorization models and live server tools. |
| 9 | [Okta MCP Server (Fctr Identity)](https://repoai.io/mcp/fctr-id-okta-mcp-server) | 🔴 37 | 38 | Okta management and risk assessment for AI-powered admin workflows. |
| 10 | [LDAP MCP Server](https://repoai.io/mcp/ldap-mcp) | 🔴 21 | 11 | LDAP directory entries — search, retrieve, and modify via MCP. |

---

## 🌐 Browser & Automation

*Browser control and workflow automation. 19 servers tracked — top 12 below.* [See all 19 →](https://repoai.io/category/browser-automation)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Browser Tools MCP Server](https://repoai.io/mcp/browser-tools-mcp) | 🔴 58 | 7,273 | Chrome browser data capture and analysis for AI-powered MCP apps. |
| 2 | [Ableton MCP Server](https://repoai.io/mcp/ableton-mcp) | 🔴 50 | 2,899 | Ableton Live track and session manipulation via MCP. |
| 3 | [Anytype MCP Server](https://repoai.io/mcp/anytype-mcp) | 🔴 48 | 487 | Access and manage your Anytype knowledge base in natural language. |
| 4 | [Playwright MCP Server (community)](https://repoai.io/mcp/mcp-playwright) | 🔴 47 | 5,620 | Automate browser interactions, capture screenshots, emulate mobile devices. |
| 5 | [Playwright MCP Server](https://repoai.io/mcp/playwright-mcp) 🏛️ | 🔴 46 | 35,509 | Microsoft's official browser automation via structured accessibility snapshots. |
| 6 | [Fetcher MCP Server](https://repoai.io/mcp/fetcher-mcp) | 🔴 42 | 1,069 | Web page extraction using Playwright for dynamic rendering. |
| 7 | [Browser Use MCP Server](https://repoai.io/mcp/browser-use-mcp-server) | 🔴 42 | 826 | Web browser automation using the browser-use framework. |
| 8 | [Browser MCP Server](https://repoai.io/mcp/browsermcp-mcp) | 🔴 36 | 6,884 | Automate existing browser sessions locally for private workflows. |
| 9 | [Playwright MCP Server (Hyhfish)](https://repoai.io/mcp/hyhfish-playwright-mcp) | 🔴 36 | 0 | Browser automation using accessibility trees instead of screenshots. |
| 10 | [Pointer MCP Server](https://repoai.io/mcp/mcp-pointer) | 🔴 34 | 591 | Browser DOM element selection and data extraction for coding agents. |
| 11 | [Selenium MCP Server](https://repoai.io/mcp/selenium-mcp-server) | 🔴 23 | 4 | Automate navigation and clicking via Selenium WebDriver. |
| 12 | [Windows MCP Server](https://repoai.io/mcp/windows-mcp) | 🔴 20 | 6,513 | Windows system control and UI automation across versions 7–11. |

> Every server in this category is a live pipe from the open web (or your OS) into the model's context — treat everything it reads as untrusted input, not just data. See the [threat model](#-mcp-threat-model).

---

## 🧠 AI & ML

*Model inference, embeddings, and ML pipelines. 22 servers tracked — top 12 below.* [See all 22 →](https://repoai.io/category/ai-ml)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Sequential Thinking MCP Server](https://repoai.io/mcp/sequentialthinking) 🏛️ | 🟡 76 | 88,988 | Structured, step-by-step reasoning for complex problem-solving. |
| 2 | [MiniMax MCP Server](https://repoai.io/mcp/minimax-mcp) | 🔴 53 | 1,541 | Access MiniMax AI models directly through MCP. |
| 3 | [HF MCP Server](https://repoai.io/mcp/hf-mcp-server) | 🔴 53 | 269 | Hugging Face Hub and Gradio app access for AI workflows. |
| 4 | [Arkon MCP Server](https://repoai.io/mcp/arkon) | 🔴 49 | 1,096 | Centralize internal documentation into a managed AI knowledge hub. |
| 5 | [Vibe Check MCP Server](https://repoai.io/mcp/vibe-check-mcp-server) | 🔴 48 | 503 | Monitor agent activity with research-backed Chain-Pattern Interrupt oversight. |
| 6 | [Memory MCP Server](https://repoai.io/mcp/memory) 🏛️ | 🔴 46 | 89,054 | Persistent knowledge-graph memory across sessions. |
| 7 | [Client for Ollama MCP Server](https://repoai.io/mcp/mcp-client-for-ollama) | 🔴 45 | 782 | Local LLMs interacting with MCP servers via a Python client. |
| 8 | [Pal MCP Server](https://repoai.io/mcp/pal-mcp-server) | 🔴 44 | 11,703 | Provider Abstraction Layer orchestrating multiple AI models/CLIs. |
| 9 | [MAS Sequential Thinking MCP Server](https://repoai.io/mcp/mcp-server-mas-sequential-thinking) | 🔴 37 | 306 | Multi-agent sequential thinking for deep problem decomposition. |
| 10 | [ElevenLabs MCP Server](https://repoai.io/mcp/elevenlabs-mcp) 🏛️ | 🔴 36 | 1,487 | ElevenLabs text-to-speech and audio processing for AI assistants. |
| 11 | [Memory Bank MCP Server](https://repoai.io/mcp/memory-bank-mcp) | 🔴 36 | 917 | Remote memory-bank management for multi-project file structure. |
| 12 | [Weaviate MCP Server](https://repoai.io/mcp/mcp-server-weaviate) | 🔴 34 | 162 | Weaviate vector collections and search tools, now official-adjacent. |

---

## 🔀 Version Control

*GitHub, GitLab, and other VCS platforms. 15 servers tracked — top 10 below.* [See all 15 →](https://repoai.io/category/version-control)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [GitLab MCP Server](https://repoai.io/mcp/mcp-gitlab-server) | 🟡 68 | 61 | GitLab API access via 86 specialized tools. |
| 2 | [GitHub MCP Server](https://repoai.io/mcp/github-mcp-server) 🏛️ | 🔴 53 | 31,734 | GitHub's official server — repos, issues, PRs, and CI/CD workflows. |
| 3 | [Forgejo MCP Server](https://repoai.io/mcp/forgejo-mcp) 🏛️ | 🔴 52 | 63 | Forgejo and Gitea repository management for AI assistants. |
| 4 | [NixOS MCP Server](https://repoai.io/mcp/mcp-nixos) | 🔴 48 | 776 | NixOS package search/data retrieval to prevent dependency hallucination. |
| 5 | [Bitbucket MCP Server](https://repoai.io/mcp/mcp-bitbucket) | 🔴 35 | 23 | Bitbucket Server/Data Center repo, PR, and project access. |
| 6 | [Gerrit Code Review MCP Server](https://repoai.io/mcp/gerrit-code-review-mcp) | 🔴 21 | 37 | Gerrit code-review workflows — change inspection and feedback. |
| 7 | [GitLab MCP Server (reference)](https://repoai.io/mcp/gitlab) 🏛️ | 🔴 16 | 293 | GitLab API for project management and repository automation. |
| 8 | [Kibana MCP Server](https://repoai.io/mcp/mcp-server-kibana) | 🔴 10 | 76 | Kibana instance data access via API-based integration. |
| 9 | [Atlassian Bitbucket MCP Server](https://repoai.io/mcp/mcp-server-atlassian-bitbucket) | 🔴 6 | 159 | Bitbucket repositories, pull requests, and code management. |
| 10 | [Forgejo MCP Server (Sqcows)](https://repoai.io/mcp/sqcows-forgejo-mcp) | 🔴 5 | 8 | Forgejo/Gitea repository management via 103 integrated tools. |

---

## 🔁 CI/CD

*Build pipelines, deployment automation, and release orchestration. 15 servers tracked — top 10 below.* [See all 15 →](https://repoai.io/category/ci-cd)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [CircleCI MCP Server](https://repoai.io/mcp/mcp-server-circleci) 🏛️ | 🔴 58 | 86 | CircleCI pipeline management and diagnostics for AI-powered IDEs. |
| 2 | [TeamCity MCP Server](https://repoai.io/mcp/teamcity-mcp) | 🔴 48 | 27 | JetBrains TeamCity CI/CD operations for AI assistance. |
| 3 | [Azure DevOps On-Prem MCP Server](https://repoai.io/mcp/azure-devops-mcp-onprem) | 🔴 45 | 10 | Azure DevOps Server 2022.2 access via 48 tools, with TFVC support. |
| 4 | [GitLab MCP Server (CI-focused)](https://repoai.io/mcp/mcp-gitlab) | 🔴 43 | 5 | GitLab REST API via 83 tools for projects and CI/CD workflows. |
| 5 | [Azure DevOps MCP Server](https://repoai.io/mcp/mcp-azure-devops) | 🔴 40 | 10 | Azure DevOps work items, git repos, and pipelines for AI assistants. |
| 6 | [Azure DevOps MCP Server (alt)](https://repoai.io/mcp/azure-devops-mcp-server) | 🔴 35 | 14 | Azure DevOps operations — work items, builds, PR management. |
| 7 | [TeamCity MCP Server (Rukavkov)](https://repoai.io/mcp/itcaat-teamcity-mcp) | 🔴 34 | 12 | TeamCity build pipelines and artifact management. |
| 8 | [Drone CI MCP Server](https://repoai.io/mcp/drone-ci-mcp) | 🔴 33 | 6 | Drone CI build status and step logs within your AI environment. |
| 9 | [ArgoCD MCP Server](https://repoai.io/mcp/argocd-mcp) | 🔴 23 | 12 | ArgoCD application management and sync via natural language. |
| 10 | [For ArgoCD MCP Server](https://repoai.io/mcp/mcp-for-argocd) | 🔴 18 | 547 | Argo CD applications and clusters via natural-language interfaces. |

---

## 🔎 Search & Data

*Web search, scraping, and data retrieval. 26 servers tracked — top 12 below.* [See all 26 →](https://repoai.io/category/search-data)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Fetch MCP Server](https://repoai.io/mcp/fetch) 🏛️ | 🟡 76 | 89,054 | Retrieve and convert web pages into Markdown for AI processing. |
| 2 | [Exa MCP Server](https://repoai.io/mcp/exa-mcp-server) 🏛️ | 🟡 76 | 4,801 | Web, code, and company search capabilities for AI assistants. |
| 3 | [Bright Data MCP Server](https://repoai.io/mcp/brightdata-mcp) 🏛️ | 🟡 76 | 2,536 | Real-time web data and AI search insights without blocking. |
| 4 | [Firecrawl MCP Server](https://repoai.io/mcp/firecrawl-mcp-server) | 🟡 73 | 7,046 | Scrape and search live web data with structured output formats. |
| 5 | [Kagi MCP Server](https://repoai.io/mcp/kagimcp) 🏛️ | 🟡 73 | 458 | Search Kagi and extract full page content as Markdown. |
| 6 | [Context7 MCP Server](https://repoai.io/mcp/context7) | 🟡 68 | 59,782 | Up-to-date documentation and code examples delivered to your AI prompts. |
| 7 | [Tavily MCP Server](https://repoai.io/mcp/tavily-mcp) | 🟡 65 | 2,279 | Real-time web search and automated data extraction. |
| 8 | [Arxiv MCP Server](https://repoai.io/mcp/arxiv-mcp-server) | 🔴 58 | 3,007 | Search arXiv, retrieve LaTeX, follow citation graphs. |
| 9 | [Anysearch MCP Server](https://repoai.io/mcp/anysearch-mcp-server) | 🔴 58 | 1,642 | Web, domain-specific, and parallel search with full-page extraction. |
| 10 | [Paper Search MCP Server](https://repoai.io/mcp/paper-search-mcp) | 🔴 55 | 2,292 | Academic paper retrieval from multiple sources, unified. |
| 11 | [DuckDuckGo MCP Server](https://repoai.io/mcp/duckduckgo-mcp-server) | 🔴 55 | 1,385 | DuckDuckGo search and webpage content extraction. |
| 12 | [GSC MCP Server](https://repoai.io/mcp/mcp-gsc) | 🔴 55 | 1,274 | Google Search Console data analysis via natural-language SEO reporting. |

---

## 📁 File Systems

*Local and remote file/directory access. 15 servers tracked — top 10 below.* [See all 15 →](https://repoai.io/category/file-systems)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Vast Admin MCP Server](https://repoai.io/mcp/vast-admin-mcp) | 🟡 63 | 11 | VAST cluster administration — monitoring and management. |
| 2 | [Dash MCP Server](https://repoai.io/mcp/mcp-server-dash) 🏛️ | 🟡 63 | 10 | Search company content and file metadata via Dropbox Dash. |
| 3 | [AWS S3 MCP Server](https://repoai.io/mcp/sample-mcp-server-s3) 🏛️ | 🔴 52 | 78 | AWS S3 bucket and object access for your AI model context. |
| 4 | [File System MCP Server](https://repoai.io/mcp/filesystem) 🏛️ | 🔴 46 | 89,054 | Read, write, list, and modify local files and directories. |
| 5 | [Ggsrun MCP Server](https://repoai.io/mcp/ggsrun) | 🔴 40 | 171 | Google Apps Script and Drive operations via Go-based CLI. |
| 6 | [Google Drive MCP Server](https://repoai.io/mcp/mcp-gdrive) | 🔴 38 | 283 | Google Drive and Sheets access — search, read, write. |
| 7 | [Rclone MCP Server](https://repoai.io/mcp/rclone-mcp) | 🔴 31 | 10 | Cloud storage management using the Rclone RC API. |
| 8 | [AWS S3 MCP Server (alt)](https://repoai.io/mcp/aws-s3-mcp) | 🔴 29 | 29 | AWS S3 buckets and objects accessible directly via your AI tools. |
| 9 | [Google Drive MCP Server (extended)](https://repoai.io/mcp/google-drive-mcp) | 🔴 28 | 198 | Google Drive, Docs, Sheets, and Calendar management. |
| 10 | [RustFS MCP Server](https://repoai.io/mcp/rustfs-mcp) 🏛️ | 🔴 28 | 15 | S3-compatible object storage access for AI models, in Rust. |

---

## 💬 Communication

*Slack, email, and messaging integrations. 22 servers tracked — top 12 below.* [See all 22 →](https://repoai.io/category/communication)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Slack MCP Server](https://repoai.io/mcp/slack-mcp-server) | 🟢 80 | 1,752 | Slack workspace interactions via Stdio, SSE, and HTTP. |
| 2 | [Telegram MCP Server (Evstafev)](https://repoai.io/mcp/chigwell-telegram-mcp) | 🟡 65 | 1,353 | Telegram chat, contact, and media operations via MCP. |
| 3 | [Twilio Labs MCP Server](https://repoai.io/mcp/twilio-labs-mcp) 🏛️ | 🟡 60 | 108 | Twilio public APIs accessed directly through MCP tools. |
| 4 | [Nest MCP Server](https://repoai.io/mcp/mcp-nest) | 🔴 55 | 694 | Expose NestJS methods and resources as MCP tools via DI. |
| 5 | [Teams MCP Server](https://repoai.io/mcp/teams-mcp) | 🔴 54 | 122 | Microsoft Graph API for Teams chat, message, and user management. |
| 6 | [WhatsApp MCP Server](https://repoai.io/mcp/whatsapp-mcp) | 🔴 46 | 5,960 | WhatsApp personal account messaging and media access. |
| 7 | [Feishu MCP Server](https://repoai.io/mcp/feishu-mcp) | 🔴 45 | 715 | Access and manage Feishu documents, tasks, and profiles. |
| 8 | [WhatsApp MCP Server (Very Good Plugins)](https://repoai.io/mcp/verygoodplugins-whatsapp-mcp) | 🔴 45 | 135 | WhatsApp messages, contacts, and media via AI agents. |
| 9 | [Slack MCP Server (Ubie)](https://repoai.io/mcp/ubie-oss-slack-mcp-server) | 🔴 43 | 110 | List channels, search history, and post messages to Slack. |
| 10 | [Teams MCP Server (alt)](https://repoai.io/mcp/mcp-teams-server) | 🔴 40 | 386 | Microsoft Teams messaging, thread management, member directory. |
| 11 | [Telegram MCP Server](https://repoai.io/mcp/telegram-mcp) | 🔴 39 | 339 | List chats, read messages, and send drafts via Telegram API. |
| 12 | [Google Workspace MCP Server](https://repoai.io/mcp/google-workspace-mcp) | 🔴 38 | 2,912 | Calendar, Drive, Gmail, and Docs access for AI agents. |

---

## 📋 Project Management

*Issue tracking, tickets, and project/task platforms. 18 servers tracked — top 12 below.* [See all 18 →](https://repoai.io/category/project-management)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Atlassian MCP Server](https://repoai.io/mcp/atlassian-mcp-server) 🏛️ | 🟡 86 | 919 | Jira, Confluence, Bitbucket, and Compass via Atlassian Cloud. |
| 2 | [Atlassian MCP Server (Sooperset)](https://repoai.io/mcp/mcp-atlassian) | 🟡 68 | 5,614 | Jira and Confluence access across Cloud and Data Center. |
| 3 | [Trello MCP Server](https://repoai.io/mcp/trello-mcp-server) 🏛️ | 🟡 66 | 21 | Trello boards, lists, and cards via natural-language AI. |
| 4 | [12306 MCP Server](https://repoai.io/mcp/12306-mcp) | 🔴 50 | 1,133 | China Railway 12306 ticket search for AI assistant workflows. |
| 5 | [Asana MCP Server](https://repoai.io/mcp/mcp-server-asana) | 🔴 49 | 145 | Asana tasks, projects, and workspaces for your AI assistant. |
| 6 | [Atlassian DC MCP Server](https://repoai.io/mcp/atlassian-dc-mcp) | 🔴 40 | 85 | Jira, Confluence, and Bitbucket connectivity via MCP. |
| 7 | [Linear MCP Server](https://repoai.io/mcp/linear-mcp-server) | 🔴 36 | 347 | Linear issue management, search, and updates. |
| 8 | [Plane MCP Server](https://repoai.io/mcp/plane-mcp-server) | 🔴 34 | 40 | Plane.so projects and issues for LLM-based workflows. |
| 9 | [Trello MCP Server (community)](https://repoai.io/mcp/m0xai-trello-mcp-server) | 🔴 32 | 55 | Trello board, list, and card management. |
| 10 | [Trello Desktop MCP Server](https://repoai.io/mcp/trello-desktop-mcp) | 🔴 32 | 36 | Trello boards, lists, and cards for local AI workflows. |
| 11 | [Linear MCP Server (GraphQL)](https://repoai.io/mcp/mcp-linear) | 🔴 25 | 144 | Linear project data via the GraphQL API. |
| 12 | [Trello MCP Server (alt)](https://repoai.io/mcp/mcp-server-trello) | 🔴 20 | 427 | Trello boards, cards, and comments via AI agents. |

> **Note:** Linear also runs its own official hosted remote MCP server (OAuth, no self-hosted repo) at `mcp.linear.app` — several community implementations, including some above, have been deprecated by their own authors in favor of it. Prefer Linear's official endpoint where your client supports remote servers.

---

## 📊 Monitoring & Observability

*Application monitoring, alerting, and incident response. 16 servers tracked — top 12 below.* [See all 16 →](https://repoai.io/category/monitoring-observability)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Sentry MCP Server](https://repoai.io/mcp/sentry-mcp) 🏛️ | 🟡 81 | 792 | Sentry error, issue, and performance data for coding assistants. |
| 2 | [DataForSEO MCP Server](https://repoai.io/mcp/mcp-server-typescript) | 🔴 58 | 233 | SERP, keyword, and backlink data from the DataForSEO API. |
| 3 | [Datadog Labs MCP Server](https://repoai.io/mcp/datadog-labs-mcp-server) 🏛️ | 🔴 58 | 43 | Query logs, metrics, and incident data from Datadog. |
| 4 | [Prometheus MCP Server](https://repoai.io/mcp/prometheus-mcp-server) | 🔴 50 | 505 | Query Prometheus metrics and execute PromQL via MCP. |
| 5 | [PagerDuty MCP Server](https://repoai.io/mcp/pagerduty-mcp-server) | 🔴 50 | 74 | PagerDuty incident management, on-call schedules, reporting. |
| 6 | [Apple Docs MCP Server](https://repoai.io/mcp/apple-docs-mcp) | 🔴 47 | 1,348 | Apple Developer Documentation via natural-language queries. |
| 7 | [JFrog MCP Server](https://repoai.io/mcp/mcp-jfrog) | 🔴 45 | 118 | JFrog Platform API for repository management and build tracking. |
| 8 | [Feedback Enhanced MCP Server](https://repoai.io/mcp/mcp-feedback-enhanced) | 🔴 35 | 3,788 | User-validated AI interactions via Desktop and Web UIs. |
| 9 | [Shell MCP Server](https://repoai.io/mcp/shell-mcp) | 🔴 23 | 7 | Shell command execution with whitelist-based safety controls. |
| 10 | [LinkedIn MCP Server](https://repoai.io/mcp/linkedin-mcpserver) | 🔴 18 | 77 | Access LinkedIn profiles, job searches, and messaging. |
| 11 | [Gcloud MCP Server](https://repoai.io/mcp/gcloud-mcp) | 🔴 15 | 870 | Google Cloud CLI commands via natural-language prompts. |
| 12 | [Sentry TS MCP Server](https://repoai.io/mcp/sentry-mcp-ts) | 🔴 15 | 11 | Sentry error data access and project management. |

---

## 💳 Payments & Commerce

*Payment processing, invoicing, and e-commerce APIs. 16 servers tracked — top 10 below.* [See all 16 →](https://repoai.io/category/payments-commerce)

| # | Server | Score | Stars | Description |
|---|---|---|---|---|
| 1 | [Stripe Agent Toolkit MCP Server](https://repoai.io/mcp/agent-toolkit) | 🟡 68 | 1,710 | Stripe billing and infrastructure tools for building AI agents. |
| 2 | [Square MCP Server](https://repoai.io/mcp/square-mcp-server) | 🔴 54 | 103 | Square API integration with support for read-only configs. |
| 3 | [Apify MCP Server](https://repoai.io/mcp/apify-mcp-server) 🏛️ | 🔴 53 | 2,251 | Apify web-scraping tools and automation actors for AI assistants. |
| 4 | [WooCommerce MCP Server](https://repoai.io/mcp/mcp-for-woocommerce) | 🔴 53 | 15 | WooCommerce store catalog and WordPress content access. |
| 5 | [Xero MCP Server](https://repoai.io/mcp/xero-mcp-server) | 🔴 45 | 344 | Xero accounting and business data via standardized MCP endpoints. |
| 6 | [Stokin MCP Server](https://repoai.io/mcp/sv-number-mcp-server) | 🔴 38 | 593 | Automate SMS verification workflows across 200+ countries. |
| 7 | [Shopify MCP Server (Cesarjoquin)](https://repoai.io/mcp/cesarjoquin-shopify-mcp) | 🔴 35 | 135 | Shopify Admin GraphQL API via a typed MCP tool interface. |
| 8 | [Shopify MCP Server (Bengherbi)](https://repoai.io/mcp/amir-bengherbi-shopify-mcp-server) | 🔴 23 | 17 | Shopify store data via direct GraphQL Admin API queries. |
| 9 | [Shopify MCP Server](https://repoai.io/mcp/shopify-mcp) | 🔴 22 | 229 | Shopify store management — products, orders, and customers. |
| 10 | [PayPal Agent Toolkit MCP Server](https://repoai.io/mcp/paypal-agent-toolkit) | 🔴 20 | 188 | PayPal invoices, payments, and disputes via function calling. |

> **Treat every write-access payments server as execute/admin-level, full stop.** Confirm every irreversible action (refund, charge, payout) outside the model's autonomy — see the [checklist](#-pre-installation-checklist).

---

## 🏛 Official Reference Servers & What's Archived

Separate from the RepoAI directory above: the MCP steering group at [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) maintains a small set of **reference implementations**, explicitly documented as educational examples rather than hardened production software. Several were later **archived** — moved to a repository with **no further security guarantees or updates** — once a vendor shipped an official successor. If an older tutorial or list links you to one of the archived ones, use the replacement in the right-hand column instead.

**Currently maintained:** [Everything](https://repoai.io/mcp/everything) · [Fetch](https://repoai.io/mcp/fetch) · [Filesystem](https://repoai.io/mcp/filesystem) · [Git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) · [Memory](https://repoai.io/mcp/memory) · [Sequential Thinking](https://repoai.io/mcp/sequentialthinking) · [Time](https://repoai.io/mcp/time)

| Archived server | Use instead |
|---|---|
| [AWS KB Retrieval](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/aws-kb-retrieval-server) | [AWS Labs MCP](https://repoai.io/mcp/awslabs-mcp) 🏛️ |
| [Brave Search](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/brave-search) | [Brave Search MCP](https://repoai.io/mcp/brave-search) 🏛️ |
| [GitHub](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/github) | [GitHub MCP Server](https://repoai.io/mcp/github-mcp-server) 🏛️ |
| [PostgreSQL](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/postgres) | See [Databases](#-databases) — no single canonical successor, audit any fork's history |
| [Puppeteer](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/puppeteer) | [Playwright MCP](https://repoai.io/mcp/playwright-mcp) 🏛️ — actively maintained by Microsoft |
| [Redis](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/redis) | Check the [official MCP Registry](https://registry.modelcontextprotocol.io/) |
| [Sentry](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/sentry) | [Sentry MCP](https://repoai.io/mcp/sentry-mcp) 🏛️ |
| [Slack](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/slack) | [Slack MCP Server](https://repoai.io/mcp/slack-mcp-server) — designated successor |
| [SQLite](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/sqlite) | See [Databases](#-databases) — no single canonical successor |
| [GitLab](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/gitlab) · [Google Drive](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/gdrive) · [Google Maps](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/google-maps) · [EverArt](https://github.com/modelcontextprotocol/servers-archived/tree/main/src/everart) | Check the [official MCP Registry](https://registry.modelcontextprotocol.io/) |

---

## 🧨 MCP Threat Model

The recurring, concrete failure modes worth knowing before you wire up your first agent:

- **Prompt injection via tool output.** Any server that returns content the model reads — a fetched web page, a file, a Slack message, a support ticket — can carry text engineered to redirect the agent ("ignore previous instructions and…"). The server didn't misbehave; the *content it faithfully returned* did.
- **Tool poisoning / description spoofing.** A malicious or compromised server can describe its own tools in a way that manipulates the model into misusing them, or hides destructive behavior behind an innocuous name. Treat tool descriptions from unfamiliar servers as untrusted input, not documentation.
- **Confused deputy / over-privileged servers.** A server connected with broad credentials (an admin API token, a root Vault token, a full-access GitHub PAT) turns any successful injection into full account compromise. Always scope credentials to the minimum the task needs.
- **Rug-pulls and silent updates.** An `npx`-installed server can change behavior between runs the moment the maintainer pushes a new version, often with no review gate. Pin versions where your tooling allows it, and prefer servers with a visible release process.
- **Secret leakage through logs or context.** Tokens passed via environment variables can end up in server logs, error messages, or echoed back into the model's context window if a server isn't careful about what it returns.
- **Ordinary supply-chain risk.** The MCP layer doesn't remove normal npm/pip supply-chain risk — a compromised dependency of the server is still a compromised dependency.

---

## ✅ Pre-Installation Checklist

- [ ] **Who maintains it?** Official vendor org, or an unrelated individual/company?
- [ ] **What's the real permission level?** Read-only < read-write < execute/admin. Don't grant more than the task needs.
- [ ] **How does it authenticate?** Prefer OAuth (short-lived, revocable, scoped) over a static token pasted into a config file.
- [ ] **Is it actively maintained?** Check last-commit date and open-issue response time.
- [ ] **Does it touch untrusted content?** Web fetch, browser automation, anything reading third-party-authored text — treat its output as untrusted and keep a human in the loop for anything destructive.
- [ ] **Does your client show you the tool call before executing it?** Human-in-the-loop confirmation for write/execute actions is the single most effective mitigation available today.
- [ ] **Check its full breakdown.** Every server above links to its exact permission list, flagged dangerous tools, and auth method — read it, don't just glance at the score.

Want a deeper, on-demand check on a server that isn't listed here yet? **[Run it through the RepoAI scanner →](https://repoai.io/tools/scanner)**

---

## 🤝 Contributing

Pull requests are welcome. Every submission needs:

1. A real, reachable repository URL — checked at submission time.
2. Maintainer status (official/community) with a one-line justification.
3. Permission level and auth method.
4. License and last-commit recency.

New servers are cross-checked against [RepoAI's directory](https://repoai.io/browse) and scored using the [public methodology](https://repoai.io/methodology) before being added to a category table.

---

*This list is maintained by the RepoAI team and provided for informational purposes. Security scores are a trust signal from public repository data, not a penetration test — always independently verify a server's source, maintainer, and permission scope before connecting it to an AI agent with access to real data or credentials.*
