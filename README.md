# 🛡️ Awesome MCP Servers & Skills (Security Rated)

A curated catalog of Model Context Protocol (MCP) servers and AI agent skills, verified with automated security and compliance scores by [RepoAI](https://repoai.io).

[![RepoAI Directory](https://img.shields.io/badge/Catalog-RepoAI.io-blue)](https://repoai.io)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

---

## 📑 Categories
- [Databases & Storage](#-databases--storage)
- [DevOps & Cloud Infrastructure](#-devops--cloud-infrastructure)
- [Web & Browser Automation](#-web--browser-automation)
- [AI, Memory & Knowledge Retrieval](#-ai-memory--knowledge-retrieval)
- [File System & Local OS](#-file-system--local-os)
- [Communication & Project Management](#-communication--project-management)

---

## 🗄️ Databases & Storage

* [PostgreSQL MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) - A robust, read-only SQL query execution engine designed for Claude Desktop and AI agents. It allows language models to safely inspect database schemas, understand complex table relations, and run parameterized queries to fetch data without risking database integrity.
* [SQLite Explorer](https://github.com/modelcontextprotocol/servers/tree/main/src/sqlite) - A lightweight, local database interaction server providing automatic schema extraction and data querying capabilities. It is highly optimized for local testing environments, allowing agents to instantly analyze local `.db` files and generate reports.
* [MySQL/MariaDB Integration](https://github.com/example/mysql-mcp) - Connects AI agents directly to MySQL databases securely. It provides schema exploration tools, slow query analysis, and data retrieval functions, making it essential for backend debugging and data analytics workflows.
* [MongoDB MCP](https://github.com/example/mongo-mcp) [![MongoDB MCP Server security score, rated on RepoAI](https://repoai.io/api/badge/mongodb-mcp-server)](https://repoai.io/mcp/mongodb-mcp-server) - Enables seamless interaction with NoSQL databases. The server allows agents to inspect collections, run complex aggregation pipelines, and retrieve JSON documents formatted perfectly for the LLM's context window.

---

## ⚙️ DevOps & Cloud Infrastructure

* [GitHub MCP Server](https://github.com/modelcontextprotocol/servers/tree/main/src/github) - A comprehensive GitHub integration that gives AI agents the power to navigate repositories, open or review pull requests, inspect commit histories, and manage issues. It acts as an autonomous developer assistant directly within your IDE or Claude Desktop.
* [GitLab Agent](https://github.com/modelcontextprotocol/servers/tree/main/src/gitlab) - Similar to the GitHub server but tailored for GitLab CI/CD environments. It allows models to fetch repository structures, read CI pipeline logs, and help debug failing builds by analyzing code changes directly.
* [Docker Manager MCP](https://github.com/example/docker-mcp) - A powerful tool to manage container lifecycles safely. AI agents can use this server to list running containers, inspect specific Docker images, fetch real-time container logs, and troubleshoot docker-compose stacks without manual terminal input.
* [Kubernetes Cluster Inspector](https://github.com/example/k8s-mcp) - Provides read-only access to Kubernetes clusters. Agents can query pod statuses, fetch logs from failing deployments, and inspect ConfigMaps, making it a powerful SRE (Site Reliability Engineering) companion.

---

## 🌐 Web & Browser Automation

* [Puppeteer MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer) - A headless browser automation server that brings the real web to your AI. It can capture visual screenshots of web pages, execute custom JavaScript, click on dynamic elements, and extract text from complex Single Page Applications (SPAs).
* [Fetch Web MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) - An ultra-fast, lightweight tool that fetches static web pages and instantly converts them into clean, well-structured Markdown. This ensures that the AI receives web data in the most token-efficient and context-friendly format possible.
* [Brave Search API](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search) - Connects agents to the live internet using the Brave Search engine. It allows models to perform web searches, retrieve the latest news, find technical documentation, and ground their answers in real-time factual data.

---

## 🧠 AI, Memory & Knowledge Retrieval

* [Memory MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) - A foundational server that provides persistent memory capabilities to AI agents using a local Knowledge Graph. It allows the model to remember facts, user preferences, and previous context across different chat sessions permanently.
* [Sequential Thinking Server](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) - A logical reasoning framework that forces the AI to break down complex problems into step-by-step thoughts. It acts as a cognitive scaffolding tool, significantly reducing hallucinations during complex coding or mathematical tasks.
* [Obsidian Vault Reader](https://github.com/example/obsidian-mcp) - Bridges the gap between your personal knowledge base and the AI. This server indexes local Obsidian Markdown files, allowing the agent to search through your personal notes, connect ideas, and write new content based on your existing knowledge.
* [Google Drive / Docs Integration](https://github.com/modelcontextprotocol/servers/tree/main/src/gdrive) - Grants the AI the ability to search, read, and summarize documents stored in Google Workspace. Perfect for retrieving company policies, technical specs, or meeting notes directly into the conversation.

---

## 📂 File System & Local OS

* [Local File System (FS)](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) - A crucial utility that provides controlled, sandboxed access to your local machine's directories. It allows the AI to read code files, write new scripts, create directories, and perform batch text replacements across multiple files safely.
* [Node.js & NPM Environment](https://github.com/example/node-mcp) - Allows the agent to inspect `package.json` files, run npm scripts, check for outdated dependencies, and even execute small Node.js snippets locally to test logic before committing code.
* [Time & Date Utility](https://github.com/modelcontextprotocol/servers/tree/main/src/time) - A simple but essential utility that provides the AI with the exact current local time, date, and timezone data, enabling it to set accurate reminders, calculate durations, and understand cron jobs.

---

## 💬 Communication & Project Management

* [Slack Workspace Server](https://github.com/modelcontextprotocol/servers/tree/main/src/slack) - Connects your AI assistant directly to Slack. The model can read specific channels, summarize long threads, find messages from specific users, and even draft replies to team members.
* [Linear / Jira Issue Tracker](https://github.com/example/linear-mcp) - Integrates with project management tools to allow the AI to fetch active sprints, read ticket descriptions, update issue statuses, and write code directly aimed at solving assigned bugs.
* [Discord Bot MCP](https://github.com/example/discord-mcp) - Enables interaction with Discord servers for community management. The AI can pull chat history for moderation analysis, respond to common support questions, or summarize community feedback directly to the developer.

---

## 🛡️ Add Your MCP Server & Badge

Want to list your MCP server or display your real-time security badge?

1. Submit or find your tool on [RepoAI.io](https://repoai.io).
2. Add this snippet to your project's `README.md`:

```markdown
[![RepoAI Security](https://repoai.io/api/badge/security/YOUR-SLUG)](https://repoai.io/mcp/YOUR-SLUG)
