---
title: "Doubao Work × TRAE On-Premises Deployment: One A-card Infrastructure for Enterprise Dual Agents"
date: 2026-10-05
draft: false
description: "Doubao Coding (TRAE) and Doubao Work share a local model gateway, enterprise knowledge RAG, and an A-card NPU foundation — letting coding and office AI complete tasks, governance, and auditing entirely inside the enterprise domain. This post walks through the business architecture, network topology, inference architecture, and security governance, with a 16:9 animated dual-scene architecture demo."
tags: ["AI Agent", "Doubao", "TRAE", "On-Premises Deployment", "A-card", "Enterprise AI"]
slug: "doubao-local-ai-solution"
cover:
  image: "https://liweicong2016-collab.github.io/my-website/assets/doubao-ascend/cover.png"
  alt: "Doubao Work × TRAE on-premises deployment architecture animation"
  caption: "Dual-scene Agent architecture animation: office (Doubao Work) and coding (TRAE)"
ShowToc: true
---

## The Pitch in One Sentence

> Built on Kunpeng CPUs, **A-card NPUs**, a heterogeneous operator library, and local model services, **Doubao TRAE (for software engineering)** and **Doubao Work (for enterprise office work)** run as two Agent products on one shared foundation — code, documents, task context, vector indexes, and audit logs never leave the enterprise domain.

> 🎬 **Interactive demo (20-section solution + 16:9 architecture animation):** [https://liweicong2016-collab.github.io/my-website/doubao-ascend/](https://liweicong2016-collab.github.io/my-website/doubao-ascend/)
> After opening the page, click "▶ 16:9 Dynamic Architecture Demo" at the top to watch the full execution flow of the Doubao Work (office) and TRAE (coding) Agent scenarios, auto-looped.

---

## Why "One Foundation, Two Products"

The most common form of waste when enterprises adopt AI Agents is buying one stack for engineering, another for office work, and ending up with duplicate model gateways, knowledge bases, and audit systems. This solution is built around **platform capability reuse**:

| Dimension | Doubao TRAE (Coding) | Doubao Work |
|---|---|---|
| Primary users | Software engineers, architects, engineering managers | All-function employees: product, ops, marketing, sales, HR, finance |
| Core tasks | Code generation, super completion, Solo full-cycle development | Documents, spreadsheets, slides, data analysis, research, task automation |
| Workspace | IDE / CLI / plugins + enterprise code context | PC / Web / mobile + project spaces + local/cloud computer execution |
| Governance focus | Code never leaves or trains, command blacklist, MCP whitelist | Resource × Agent dual-layer control, sensitive-action confirmation, egress control |

Both products share: a local model gateway, RAG / vector store, object storage, identity & access (SSO / RBAC), usage analytics, audit logs, and **A-card NPU inference resources**.

---

## Overall Business Architecture: Four Layers

```text
L1 Entry        TRAE (IDE/CLI/plugins) · Doubao Work (PC/Web/mobile/Feishu)
                Admin console · Automation & open APIs (scheduled tasks/Bot/API/MCP)
      ↓
L2 Applications Coding domain (AI Chat / CUE completion / Solo / repo indexing / sandbox)
                Work domain (tasks / skills / connectors / buddies / local & cloud execution)
      ↓
L3 Platform     Agent runtime · Model gateway · Knowledge RAG · Asset & skill library
                Identity & policy · Audit & operations
      ↓
L4 Local infra  Enterprise systems & data (repos / CI-CD / OA / ERP / CRM / data warehouse)
                A-card on-prem foundation (Kunpeng 128C · A-card 910B · dual CE / storage)
```

**Data flow for a single task:** user input → context assembly → identity & policy check → local inference (model gateway / A-card NPU) → tool execution (files / browser / connectors / sandbox) → delivery & audit. The control plane always passes through "identity → permission & classification → egress policy → sensitive-action confirmation → content safety → audit." When permissions or evidence are insufficient, the system refuses or escalates to a human; when local inference fails, it only falls back to pre-approved models — unauthorized outbound transmission is prohibited.

---

## Deployment & Inference Highlights

**On-premises network** (2,000-user, five-node reference): endpoints → edge zone (HA firewalls + WAF/L7 load balancer, HTTPS terminated at a VIP) → dual CE switches in M-LAG (no interruption on single-switch failure) → 3 application/RAG nodes + 2 A-card inference nodes; VLANs segmented into AI-APP / AI-DATA / AI-MODEL / AI-STORAGE / AI-MGMT / OOB, with the model API served over mTLS.

**Resource tiers** (attachment data — to be revalidated by PoC stress tests):

| Scale | Servers | Per-server config | A-card NPU total | HA |
|---|---|---|---|---|
| ≤500 users | 2 | Kunpeng 128C / 512GB / 1.5TB NVMe | 16 × 910B | No |
| 1,000 users | 3 | same | 24 × 910B | Yes |
| 2,000 users (reference) | 5 | same | 16 × 910B | Yes |
| 3,000 users | 7 | same | 24 × 910B | Yes |

**Inference architecture**, exemplified by the GLM5.1 six-node setup: model gateway (authN / routing / rate limiting / degradation) → prefix & cache routing (session affinity · Prefix Cache) → **Prefill cluster (2 nodes, DP4·TP8·EP16)** and **Decode cluster (4 nodes, TP4·EP64)** deployed separately, combined with KV Cache defragmentation / prefix reuse / quantization & compression / cross-node offloading, plus PD disaggregation, expert parallelism, and speculative decoding. Reference metrics: 1,120 engineering users / 112 concurrent, TPOT 33ms with 90% Prefix Cache hit rate.

---

## Security & Governance: Resource × Agent Dual-Layer Control

- **Resource layer:** enterprise identity and object permissions apply directly; documents, messages, and approvals inherit platform security domains; watermarking / DLP / classification labels cover input and output; tenant isolation plus encryption in transit and at rest.
- **Agent layer:** role and scenario definitions, tool / MCP / connector whitelists, network egress control by URL / IP / CIDR, sandbox execution with command blacklists.
- **Unified policy & audit:** allow / ask / deny decisions, secondary confirmation for high-risk actions, four-element logging of "who × agent × resource × action," with bidirectional traceability from both the agent view and the resource view.
- Key principle: **AI has no "dedicated super account"** — an agent can only access resources on behalf of an authorized user, and its access scope converges immediately when permissions change.

---

## The 16:9 Architecture Animation: Two Complete Examples

The demo ships with two animated scenarios. Each uses a real task example: nodes light up stage by stage, connection lines flow, and task steps are checked off one by one.

**Doubao Work Agent (office scenario)** — example: *arrange a cross-department quarterly review meeting, then generate and distribute the minutes.*
Planner (check calendars → coordinate attendees → book a room → draft minutes) → Reasoning → Agent core loop (task orchestration / flow control / execution parameters / state loop waiting on approval) → Reflection (verify receipts; retry, compensate, or escalate failures to a human) → Function aggregation → outputs the meeting arrangement and minutes summary, with artifacts archived and auditable.

**TRAE Agent (coding scenario)** — example: *add an "export report" API to the order service, backfill unit tests, and pass CI.*
Planner (locate modules → plan the API and tests → decompose to files) → Reasoning → core loop (file-level edits / sandbox execution / MCP-whitelisted parameters / Diff awaiting human review) → Reflection (retry, roll back, or escalate on test failure) → outputs a change summary and validation results.

Memory, tools, MCP services, and execution boundaries differ per scenario, but both run on the same local intelligence foundation: **local model services → A-card NPU inference pool → knowledge RAG → object storage / audit. Data never leaves the enterprise domain.**

---

## Delivery Path & Acceptance

Delivery proceeds in six gated phases: discovery & PoC → architecture & BOM → environment deployment → model & data adaptation → joint acceptance → staged rollout & operations. Each phase produces verifiable deliverables, and a failed gate blocks the next phase. Acceptance covers six domains: product functionality, deployment topology, model performance (TPOT / TTFT / concurrency / stability), data & knowledge (permission filtering / citation traceability / fact verification), security governance, and operations.

Two items to lock down early:

1. **Model licensing:** base tiers do not include model weights or licenses by default — choose among a SaaS Model Hub, enterprise-owned models, or third-party models, and list them as separate line items.
2. **Identity ecosystem:** Doubao Work is natively and deeply coupled with Feishu identity and permissions; the adaptation scope for other enterprise IdPs must be validated during the PoC.

---

*This solution is compiled from the Doubao Coding / Doubao Work capability handbook, security framework, admin console documentation, the TRAE joint solution, and the on-premises deployment architecture. Capability statuses and performance figures are subject to the delivered version, PoC stress-test results, and contractual agreements. Compute hardware names are anonymized ("A-card") in this document.*
