# OpenClaw Ecosystem Digest 2026-06-27

> Issues: 500 | PRs: 500 | Projects covered: 13 | Generated: 2026-06-27 08:27 UTC

- [OpenClaw](https://github.com/openclaw/openclaw)
- [NanoBot](https://github.com/HKUDS/nanobot)
- [Hermes Agent](https://github.com/nousresearch/hermes-agent)
- [PicoClaw](https://github.com/sipeed/picoclaw)
- [NanoClaw](https://github.com/qwibitai/nanoclaw)
- [NullClaw](https://github.com/nullclaw/nullclaw)
- [IronClaw](https://github.com/nearai/ironclaw)
- [LobsterAI](https://github.com/netease-youdao/LobsterAI)
- [TinyClaw](https://github.com/TinyAGI/tinyagi)
- [Moltis](https://github.com/moltis-org/moltis)
- [CoPaw](https://github.com/agentscope-ai/CoPaw)
- [ZeptoClaw](https://github.com/qhkm/zeptoclaw)
- [ZeroClaw](https://github.com/zeroclaw-labs/zeroclaw)

---

## OpenClaw Deep Dive

Here is the OpenClaw project digest for **2026-06-27**.

---

## OpenClaw Project Digest: 2026-06-27

### 1. Today's Overview

The OpenClaw project is experiencing a period of extremely high activity, with 500 issues and 500 PRs updated in the last 24 hours. The vast majority of this activity is on open items, indicating a massive, active backlog but also a healthy level of community and maintainer engagement. A significant portion of discussion and development is focused on security hardening, session state management, and reliability, with a high volume of "diamond lobster" severity items being triaged. While there were no new releases today, the intense PR activity, including non-trivial fixes for OOM crashes, race conditions, and data loss, suggests a major stability-focused release may be imminent.

### 2. Releases

**None.** No new releases were published on 2026-06-27.

### 3. Project Progress

Based on the data, 36 PRs were merged or closed today. Key advancements and fixes observed in the PR queue include:

- **Security & Resource Management:**
    - Multiple PRs focused on bounding Server-Sent Events (SSE) response reads to prevent Out-of-Memory (OOM) conditions. These include fixes for the OpenAI, Azure OpenAI, and generic proxy providers (PRs [#97217](https://github.com/openclaw/openclaw/pull/97217), [#97191](https://github.com/openclaw/openclaw/pull/97191), [#97139](https://github.com/openclaw/openclaw/pull/97139)).
    - A fix was merged for the TLS self-signed certificate generation to include `subjectAltName` (fixes [#96910](https://github.com/openclaw/openclaw/pull/97085)), which is critical for local gateway communication on Node.js ≥17.
    - A PR adding comprehensive sandbox escape prevention tests for the skill loader was submitted (PR [#97192](https://github.com/openclaw/openclaw/pull/97192)).
- **Bug Fixes:**
    - A fix was prepared for JSON Schema `anyOf` validation, where `null` was being coerced to an empty string (PR [#97212](https://github.com/openclaw/openclaw/pull/97212)).
    - A critical fix for a V8 dictionary mode degradation in stream hot paths was proposed to resolve a gateway OOM crash over time (PR [#97211](https://github.com/openclaw/openclaw/pull/97211)).

### 4. Community Hot Topics

The most active discussions highlight deep-seated concerns around security, state management, and platform support.

- **#75 - Linux/Windows Clawdbot Apps** ([Link](https://github.com/openclaw/openclaw/issues/75))
    - **Activity:** 109 Comments, 81 👍
    - **Analysis:** The single most requested feature. Users are clearly demanding parity for non-macOS platforms. This is a long-standing issue (created Jan 2026) and is a major blocker for wider adoption.
- **#25592 - Text between tool calls leaks to messaging channels** ([Link](https://github.com/openclaw/openclaw/issues/25592))
    - **Activity:** 32 Comments
    - **Analysis:** A critical UX and security issue. Internal agent processing or error messages are being broadcast to users on Slack/iMessage. This is rated "diamond lobster" and highlights a fundamental flaw in the agent's output routing.
- **#39604 - Add `tools.web.fetch.allowPrivateNetwork`** ([Link](https://github.com/openclaw/openclaw/issues/39604))
    - **Activity:** 13 Comments, 9 👍
    - **Analysis:** A feature request to allow agents to access private/internal networks. The high ratio of upvotes to comments suggests a wide user base is blocked by the current restrictive default, preventing agents from being useful in enterprise or home-lab environments.
- **#22676 - Signal daemon race condition on restart** ([Link](https://github.com/openclaw/openclaw/issues/22676))
    - **Activity:** 17 Comments
    - **Analysis:** A critical "diamond lobster" bug causing orphaned processes and send failures. This indicates fragility in the core gateway restart logic, a major reliability concern for always-on deployments.

### 5. Bugs & Stability

The project is facing a significant number of high-severity bugs. Below are the most critical reported recently, many with associated fix PRs in progress.

- **Critical (Diamond Lobster):**
    - **OOM Crash: V8 dictionary mode degradation** ([#97211](https://github.com/openclaw/openclaw/pull/97211)). A fix PR is already open.
    - **Process/State Corruption:**
        - Race condition on Signal daemon restart (Issue [#22676](https://github.com/openclaw/openclaw/issues/22676)).
        - Telegram DMs misrouting to the main session (Issue [#41165](https://github.com/openclaw/openclaw/issues/41165)).
    - **Data Loss:**
        - `write` tool lacks append mode, causing cron sessions to overwrite shared files (Issue [#40001](https://github.com/openclaw/openclaw/issues/40001)).
        - Telegram group messages losing media data (Issue [#40440](https://github.com/openclaw/openclaw/issues/40440)).
- **High (Platinum Hermit):**
    - **Regression:**
        - Google Vertex/Gemini provider crash ("Cannot convert undefined or null to object") after updating to v2026.3.2 (Issue [#38327](https://github.com/openclaw/openclaw/issues/38327)).
        - Webchat avatar endpoint returning 404 (Issue [#38439](https://github.com/openclaw/openclaw/issues/38439)).
    - **Configuration Ignored:**
        - `cacheRetention` ignored for LiteLLM-proxied Anthropic models (Issue [#37966](https://github.com/openclaw/openclaw/issues/37966)).

### 6. Feature Requests & Roadmap Signals

User demand is clearly steering towards "Enterprise Readiness." Key requests predict the next version will focus on:

- **Security Hardening:** Features like **Masked Secrets** ([#10659](https://github.com/openclaw/openclaw/issues/10659)), **Filesystem Sandboxing** ([#7722](https://github.com/openclaw/openclaw/issues/7722)), and **Path-scoped RWX permissions** ([#39979](https://github.com/openclaw/openclaw/issues/39979)) are all high-priority "diamond lobster" items.
- **Operational Control:**
    - **Per-agent cost budgets** ([#42475](https://github.com/openclaw/openclaw/issues/42475)) and a **Tokenomics plugin** ([#97149](https://github.com/openclaw/openclaw/pull/97149)) indicate a strong need for cost governance.
    - **Backup/Restore utilities** ([#13616](https://github.com/openclaw/openclaw/issues/13616)) and **auto-update** ([#12855](https://github.com/openclaw/openclaw/issues/12855)) show a push for better lifecycle management.
- **Agent Collaboration & UX:**
    - **Tiered bootstrap loading** ([#22438](https://github.com/openclaw/openclaw/issues/22438)) to manage token costs.
    - **Slack Block Kit support** ([#12602](https://github.com/openclaw/openclaw/issues/12602)) and **Tool-level progress indicators** in Slack ([#33413](https://github.com/openclaw/openclaw/issues/33413)) point to a need for richer user interfaces.
    - **Multi-agent collaboration enhancements** ([#35203](https://github.com/openclaw/openclaw/issues/35203)) are being actively discussed.

### 7. User Feedback Summary

The community is highly engaged but showing signs of frustration due to persistent stability issues.

- **Pain Points:**
    - **Reliability:** Users are frustrated by silent data loss in cron jobs ([#40001](https://github.com/openclaw/openclaw/issues/40001)), race conditions on restart ([#22676](https://github.com/openclaw/openclaw/issues/22676)), and OOM crashes ([#97211](https://github.com/openclaw/openclaw/pull/97211)).
    - **Security Concern:** A strong desire for hardening tools against injection and leakage is evident, with users wanting to prevent agents from seeing raw API keys ([#10659](https://github.com/openclaw/openclaw/issues/10659)) and to block internal processing text from leaking to channels ([#25592](https://github.com/openclaw/openclaw/issues/25592)).
    - **Platform Support:** The top-voted issue [#75](https://github.com/openclaw/openclaw/issues/75) shows significant dissatisfaction from Linux and Windows users who feel left behind.
- **Use Cases:**
    - Users are deploying agents in real-world scenarios like CRM summaries and daily briefings (Slack Block Kit feature [#12602](https://github.com/openclaw/openclaw/issues/12602)).
    - There is a clear desire to use agents in a "private cloud" or enterprise setting, as evidenced by the requests for private network access ([#39604](https://github.com/openclaw/openclaw/issues/39604)) and Telegram Business Bot support ([#20786](https://github.com/openclaw/openclaw/issues/20786)).
- **Satisfaction:** While the feature community is creative and demanding, the high volume of open "diamond lobster" bugs and regressions suggests overall satisfaction is being tempered by reliability issues.

### 8. Backlog Watch

Several critical issues and PRs are languishing, requiring maintainer review and product decisions. Their continued open status represents a risk to project stability.

- **Issue #25592 - Text leaks to messaging channels** ([Link](https://github.com/openclaw/openclaw/issues/25592))
    - **Status:** Open "diamond lobster" P1 since Feb 2026. Needs a product decision on how to handle internal agent text.
- **Issue #22676 - Signal daemon race condition** ([Link](https://github.com/openclaw/openclaw/issues/22676))
    - **Status:** Open P1 since Feb 2026. This is a core stability issue with an open PR that has not been merged.
- **Issue #40001 - Write tool lacks append mode** ([Link](https://github.com/openclaw/openclaw/issues/40001))
    - **Status:** Open P1 causing data loss. A workaround may exist, but a clean fix is required.
- **PR #73365 - Allow steer messages during active runs** ([Link](https://github.com/openclaw/openclaw/pull/73365))
    - **Status:** Open, "waiting on author" for over two months. This fix is blocking a known P1 issue.
- **PR #89039 - Prevent silent message loss** ([Link](https://github.com/openclaw/openclaw/pull/89039))
    - **Status:** Open since June 1st. A large fix for a critical "diamond lobster" problem. The size and scope may be causing the delay in review.

---

## Cross-Ecosystem Comparison

Here is the cross-project comparison report based on the provided digests.

---

### Cross-Project Ecosystem Report: 2026-06-27

**Report Type:** Open-Source AI Agent & Personal Assistant Ecosystem Analysis
**Date:** 2026-06-27
**Audience:** Technical Decision-Makers & Developers

---

### 1. Ecosystem Overview

The open-source personal AI assistant ecosystem is currently in a phase of intense activity and maturation, characterized by a clear pivot from experimental features toward production-grade reliability and security. Key projects are consolidating gains via major refactoring sprints (v2.0 betas, "Reborn" stack porting) while simultaneously addressing a backlog of critical bugs related to memory management, message delivery, and context overflow. A significant trend is the community's growing demand for enterprise features such as supply-chain signing (ZeroClaw), per-group model overrides (NanoClaw), and cross-platform parity (OpenClaw). The landscape is bifurcating between projects like Hermes Agent and OpenClaw, which are dealing with the pain of high-scale adoption, and smaller projects like NullClaw and Moltis, which appear to be in maintenance or low-velocity phases.

### 2. Activity Comparison

| Project | Issues (24h) | PRs (24h) | Release Status | Health Score* |
|---|---|---|---|---|
| **OpenClaw** | 500 | 500 | Stalled (none, major release imminent) | **Moderate** |
| **Hermes Agent** | 50 | 50 | Stalled (none, >30 days since last) | **Moderate** |
| **IronClaw** | 23 | 50 | Stalled (PR #5311 blocked, 0.24→0.29) | **High** |
| **ZeroClaw** | 50 | 50 | Stalled (v0.8.3 milestone active) | **High** |
| **NanoBot** | 21 | 51 | Stalled (none, likely v0.3.0 soon) | **High** |
| **LobsterAI** | 2 | 11 | **Active** (v2026.6.26 just released) | **High** |
| **CoPaw** | 12 | 40 | **Active** (v2.0.0-beta.1 out) | **High** |
| **PicoClaw** | 4 | 13 | Stalled (none) | **Moderate** |
| **NanoClaw** | 3 | 5 | Stalled (none) | **Low** |
| **NullClaw** | 1 | 0 | Stalled (none, since April) | **Low** |
| **TinyClaw** | 0 | 0 | No data | **Low** |
| **ZeptoClaw** | 0 | 0 | No data | **Low** |
| **Moltis** | 0 | 1 | No data | **Low** |

***Health Score:** A qualitative assessment based on development velocity, maintainer engagement, and the ratio of bug-fixing to feature work. Projects with active triage, frequent merges, and clear milestones score higher.*

### 3. OpenClaw's Position

**Advantages vs. Peers:**
- **Community Size:** OpenClaw operates at a scale unmatched by peers, with 500 issues/PRs updated in 24 hours. This reflects a massive user base and contributor pool.
- **Technical Approach:** It is positioned as the "core reference" implementation, meaning its architectural decisions (e.g., the "Claw" runtime, skill loader) likely set standards for the broader ecosystem.
- **Feature Depth:** It has the deepest feature request pipeline, covering everything from "Masked Secrets" to "Multi-agent collaboration," indicating it is the primary target for enterprise feature requests.

**Technical Differences:**
- Unlike NanoBot’s explicit focus on "ultra-lightweight" (though contested) or IronClaw’s "Reborn" architectural rewrite, OpenClaw appears to be evolving a highly complex monolithic gateway with hundreds of moving parts (proxy providers, tools, channels). This creates a higher surface area for bugs like OOM crashes and race conditions but also enables maximum flexibility.

**Community Size Comparison:**
- OpenClaw’s community dwarfs all others in raw activity. Projects like NullClaw (1 issue) and NanoClaw (3 issues) are orders of magnitude smaller. Only ZeroClaw and IronClaw (50 issues each) approach its level of engagement, but they do so with a much lower total backlog.

### 4. Shared Technical Focus Areas

The following requirements are emerging across multiple projects, signaling a shared industry pain point:

| Requirement | Projects Involved | Specific Needs |
|---|---|---|
| **Memory & Context Management** | OpenClaw, Hermes Agent, ZeroClaw, CoPaw | Preventing memory over-prioritization, solving context budget overflow, preventing data loss, improving de-duplication. |
| **Channel Reliability & UX** | OpenClaw, Hermes Agent, NanoBot, ZeroClaw | Fixing message delivery failures (Telegram, WhatsApp), eliminating duplicate messages, adding delivery status indicators. |
| **Security Hardening** | OpenClaw, Hermes Agent, NanoBot, IronClaw, ZeroClaw | Preventing shell command injection, blocking authorization bypasses, implementing `tool_override` safeguards, migrating to modern crypto/SPA. |
| **Cross-Platform Parity** | OpenClaw, Hermes Agent | Support for non-macOS platforms (Linux/Windows apps) and consistent behavior across desktop, TUI, and headless modes. |
| **Automation Lifecycle** | OpenClaw, IronClaw, CoPaw | Reliable cron/scheduled tasks, solving process leakage on restart, adding failure notification channels. |

### 5. Differentiation Analysis

| Feature Axis | Project Leaders | Key Differences |
|---|---|---|
| **Target User** | **Developers/Engineers:** OpenClaw, ZeroClaw, Hermes Agent. **End-Users/Consumers:** LobsterAI, CoPaw. | The "Claw" family is complex and requires configuration. LobsterAI and CoPaw are shipping desktop apps with GUIs, suggesting a focus on non-technical adoption. |
| **Technical Architecture** | **Monolithic/Ref:** OpenClaw, CoPaw. **Plugin/Wasm-first:** ZeroClaw. **Lightweight/Modular:** NanoBot. | ZeroClaw is betting on Wasmtime for a new plugin runtime to remove Node.js dependencies, while CoPaw is deep in an AgentScope 2.0 refactor. NanoBot prioritizes a small footprint. |
| **Feature Focus** | **Enterprise/Governance:** ZeroClaw (supply chain, SLSA). **Chat Integrations:** NanoBot (WhatsApp, TTS). **Security:** Hermes Agent (high-severity bugs). | ZeroClaw is building for a security-conscious enterprise. NanoBot is improving the conversational UX. Hermes Agent is fighting fires at scale. |
| **Development Lifecycle** | **Refactoring & Porting:** IronClaw, CoPaw. **Bug Fixing & Hardening:** Hermes Agent, OpenClaw, PicoClaw. | IronClaw is porting tests to a new UI stack ("Reborn"). CoPaw is migrating to a new core library (AgentScope 2.0). Mature projects are in a "harden" phase. |

### 6. Community Momentum & Maturity

- **Tier 1: Rapidly Iterating (High Velocity, Active Releases)**
    - **LobsterAI:** Just shipped a release, merged a large stale backlog, high satisfaction among testers.
    - **CoPaw:** Shipped a major v2.0 beta, sprinting to improve test coverage.

- **Tier 2: High Activity, Stabilizing (Many PRs/Issues, Blocked Releases)**
    - **IronClaw:** Intense development on the "Reborn" stack but blocked by a large pending release. Very high-quality, architecture-focused work.
    - **ZeroClaw:** High feature velocity (Wasm plugins, security) with robust RFC governance. Release is probably imminent.
    - **NanoBot:** Merged several highly-requested features in the last 24 hours. The rapid velocity suggests a release is being built.

- **Tier 3: High Activity, Bug-Fixing (High issue count, low PR merger rate)**
    - **OpenClaw:** Extremely high bug volume is slowing down progression. The massive backlog of "diamond lobster" issues suggests the project is struggling with stability at scale.
    - **Hermes Agent:** A high volume of bugs with a low merge rate for fix PRs. The project appears reactive rather than proactive, lagging behind its community's reporting speed.

- **Tier 4: Low Activity / Maintenance Phase**
    - **NullClaw, TinyClaw, ZeptoClaw, Moltis:** Near-zero activity. These projects may be abandoned, in a quiet period, or are complete for their specific use case.

### 7. Trend Signals

Based on community feedback and feature requests, the following industry trends are visible:

- **The "Memory Trust Gap":** There is a widespread user frustration that persistent agent memory is not smart enough. Users in **ZeroClaw (#5844)** and **OpenClaw (#25592)** report that memory is either over-prioritized (hogging the context) or leaking internal processing text to channels. The industry needs a "memory firewall" that is both more context-aware and better isolated.
- **The "Automation Reliability Crisis":** As agents are trusted with cron jobs and background tasks, users in **OpenClaw (#22676)**, **IronClaw (#5320, #5322)**, and **CoPaw (#5566)** are hitting silent failures, data loss, and process leaks. The value for developers is clear: building robust, self-healing lifecycle management for background agents is a critical, unsolved problem.
- **The "Cross-Platform Gap":** The most-upvoted issue in the entire ecosystem remains **OpenClaw's #75** (Linux/Windows apps). A significant portion of the developer market is locked out of the premier open-source agent. Delivering seamless, native desktop experiences on all platforms is a key competitive differentiator.
- **Security as a Foundational Requirement, Not a Feature:** The volume of security-related bugs (Shell injection, SSRF bypasses, silent authorization no-ops) is an order of magnitude higher than security feature requests. The community is not just asking for new security features; they are demanding that the existing security architecture is **enforced by default** and cannot be silently bypassed.

---

## Peer Project Reports

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

Here is the project digest for **NanoBot** (github.com/HKUDS/nanobot) for **2026-06-27**.

---

## NanoBot Project Digest — 2026-06-27

### 1. Today's Overview
NanoBot is experiencing a period of **very high development velocity and deep community engagement**. In the last 24 hours alone, **51 pull requests** were updated—half of which were merged or closed—indicating a major push to close out long-standing feature gaps and security issues. Activity is concentrated on **trusting LLM parallel tool calls**, building a **plugin system**, adding **external agent delegation**, implementing **text-to-speech**, and addressing critical **`exec` security bypasses**. The issue tracker shows **21 updated issues**, with maintainer focus shifting toward stability and merging transformation branches. The project’s health is strong, though the sheer volume of concurrent changes (26 open PRs) suggests a near-term release candidate is being assembled.

### 2. Releases
**No new releases** were published today. The latest version remains unreleased following this burst of activity. Given the volume of merged PRs (25 closed/merged), a new version (likely 0.3.0) is expected soon.

### 3. Project Progress
Today saw the closure/merging of **25 PRs**, with several flagship features advancing to the main branch:
- **PR #4558** (closed) — **Plugin system** (fixes #2231). Adds `plugin.json` manifest loading from `~/.nanobot/plugins/` and entry_points, supporting tools, skills, and MCP server configs.
- **PR #4559** (closed) — **`agent_delegate` tool** (fixes #3436, #3024). Allows delegation to external AI agents (Claude Code, Codex, opencode).
- **PR #4560** (closed) — **TTS tool** (fixes #4010). Supports `edge-tts`, macOS `say`, `espeak-ng`, and Windows SAPI.
- **PR #4557** (closed) — **Parallel tool execution** (fixes #3096). Drops static serialization; trusts LLM parallel tool calls.
- **PR #4562** (open) — **Security fix** for `exec.allowPatterns` bypass (see Bugs & Stability).
- **PR #4527** (open) — **`ask_clarification` tool** — adds a built-in tool for agent-to-user clarification loops.
- **PR #4371** (open) — **Prompt caching optimization** — adds a breakpoint in `ContextBuilder` to enable stable system prefix caching.
- **PR #4554** (open) — **Memory de-duplication guard** — prevents Dream from creating duplicate skills.
- **WhatsApp channel** saw multiple merged fixes: fromMe message handling (PR #1450, #2411), group reply suppression (#3051), typing indicators (#3761), neonize-native cues (#4563), and JID device-suffix stripping (#3514).

### 4. Community Hot Topics
- **Issue #660** (closed, 12 comments, 5 👍) — *"Project claims ultra-lightweight but includes Node.js"* — remains a lingering branding debate despite being closed.
- **Issue #4521** (closed, security advisory) — **`exec.allowPatterns` bypass** — triggered a focused flurry of fix PRs (#4526, #4562). The community responded rapidly.
- **Issue #4518** (closed, security advisory) — **Login-shell execution leaks secrets** — another high-severity shell security issue with broad agreement on the fix.
- **Issue #4419** (open, 3 comments) — **Automatic reasoning effort escalation** — user request for multi-tier model reasoning, relevant to upcoming model usage optimizations.
- **Issues #4418, #1899** — **Heartbeat session isolation** — multiple users raising that Heartbeat tasks should deliver to the originating channel, not the most recent chat. This is a UX pain point with consistent community feedback.

### 5. Bugs & Stability
New issues focus primarily on **shell execution safety and platform consistency**:

| Severity | Issue # | Title | Fix PR Exists? |
|----------|---------|-------|----------------|
| **Critical** | #4521 (closed) | `exec.allowPatterns` shell-chain bypass — chained commands like `echo allowed && rm -rf /` pass the allowlist | Yes (#4526, #4562) |
| **Critical** | #4518 (closed) | Login-shell execution introduces secrets from `.bashrc`/`.zshrc` | Yes (#4562) |
| **High** | #4544 (open) | Windows `exec` uses `cmd.exe` for single-line, `PowerShell` for multi-line — inconsistent semantics | No |
| **Medium** | #4511, #4513 (open) | Windows gateway service management bugs: `/restart` behavior with `nssm` and `--background` — stale PID files, port conflicts | No |
| **Low** | #4539 (closed) | Telegram messages not rendering on Web UI | Closed (fixed) |

### 6. Feature Requests & Roadmap Signals
The following requests are likely **candidates for the next version** given active development patterns:

- **Plugin system** (PR #4558, merged) — now in main, a response to #2231.
- **External agent delegation** (PR #4559, merged) — addresses #3436, #3024.
- **TTS / voice output** (PR #4560, merged) — completes the conversational loop.
- **`ask_clarification` tool** (PR #4527, open) — likely to merge soon.
- **Reasoning effort escalation** (#4419) — aligns with existing `reasoningEffort` config; may merge with adjusted model override logic.
- **Heartbeat model override** (#4431) — lightweight addition, likely part of session-model-override feature.
- **Crawl4AI integration** (#2700) — less active but still open; may appear as a community contribution.
- **OpenAI API authentication** (#4490) — security-conscious feature with WS gateway parity.

### 7. User Feedback Summary
**Pain points & dissatisfaction:**
- Windows users report **exec shell inconsistency** (#4544) and **service/bg-mode bugs** (#4511, #4513).
- Several users express frustration over **Heartbeat session isolation** (#1899, #4418) — "why is Heartbeat locked to its own session?"
- The branding criticism (#660) — "ultra-lightweight" despite Node.js dependency — remains a minor trust issue.

**Satisfaction signals:**
- High engagement on **WhatsApp UX improvements** (typing indicators, group suppression, fromMe fixes) — bridging UX is improving measurably.
- Strong positive sentiment on **plugin system** and **external agent delegation** — users are eager for extensibility.
- The **`ask_clarification` tool** (#4527) is well-received as an important UX improvement.

### 8. Backlog Watch
- **Issue #4539** (fixed/closed) — Telegram web rendering — was worth watching but resolved.
- **Issue #2700** (open, updated Apr 1) — *Crawl4AI support* — no maintainer response; last comment is from April. May need a champion.
- **Issue #4029** (open, updated May 27) — *Provider override for dream-specific model* — low engagement but a clear, reasonable ask.
- **Issue #4082** (open, updated May 29) — *Cron jobs reuse fixed cron: session context* — related to #1899/#4418; duplicate context issue merits alignment.
- **Issue #4490** (open, updated Jun 24) — *API auth for non-loopback interfaces* — no maintainer response yet; security-sensitive.
- **PR #2295** (closed Mar 20, merged only today) — *Async error handling in bridge server* — unusually long delay between creation and merge; suggests review bottleneck.

</details>

<details>
<summary><strong>Hermes Agent</strong> — <a href="https://github.com/nousresearch/hermes-agent">nousresearch/hermes-agent</a></summary>

# Hermes Agent Project Digest — 2026-06-27

## Today's Overview

Hermes Agent saw high activity today with **50 issues** and **50 PRs** updated in the last 24 hours, though only **5 closed/merged** each, indicating a heavy open-bug backlog. The project has **no new releases** — the last release appears to be before June 2026. Activity is concentrated on bug triage and minor patches, with a notable cluster of Windows platform issues (console flashing, orphaned processes) and several duplicate reports suggesting user frustration with known problems. The community is actively submitting fix PRs for newly reported bugs, showing healthy contributor engagement.

---

## Releases

**None** — No new releases were published in the last 24 hours. The project's last release appears to predate the latest features (v0.17.0 referenced in issues like #52060).

---

## Project Progress

**Merged/Closed PRs today (5):**

| PR | Title | Summary |
|---|---|---|
| [#53429](https://github.com/NousResearch/hermes-agent/pull/53429) (P1) | `fix(gateway): centralize agent cleanup pipeline with executor offload` | Refactored 7 scattered synchronous cleanup calls into an async pipeline with config-driven timeouts — addresses event-loop blocking on `agent.close()` |
| [#53481](https://github.com/NousResearch/hermes-agent/pull/53481) (P3) | `docs: add loop engineering kanban pipeline` | Added a Kanban-style development pipeline doc and task template for gated workflow |
| [#25260](https://github.com/NousResearch/hermes-agent/pull/25260) (P2, closed) | `fix(agent): honor provider timeout config in streaming API calls` | Fixes `stale_timeout_seconds` and `request_timeout_seconds` being silently ignored due to hardcoded `httpx.Timeout` values |

**Closed Issues today (5):**
- [#34120](https://github.com/NousResearch/hermes-agent/issues/34120) (P2) — **cronjob tool** "schedule required" bug (7 comments, 2 👍)
- [#52919](https://github.com/NousResearch/hermes-agent/issues/52919) (P1) — **Nix build broken** by `package-lock.json` update (6 comments)
- [#50106](https://github.com/NousResearch/hermes-agent/issues/50106) (P2) — Silent message loss when `agent_status` is a directory

---

## Community Hot Topics

### Most Active Issues

| Issue | Comments | Summary |
|---|---|---|
| [#38240](https://github.com/NousResearch/hermes-agent/issues/38240) (P3) | **20 comments** | **Skills index stale/degraded** — automated freshness probe failing (github API returns 0 vs expected 30). This is a continuous integration health issue affecting `/docs/skills` |
| [#34120](https://github.com/NousResearch/hermes-agent/issues/34120) (P2, CLOSED) | **7 comments** | **cronjob tool** consistently fails with "schedule is required" — using Grok 4.3, affects recurring news digest creation. High user impact (2 👍) |
| [#18646](https://github.com/NousResearch/hermes-agent/issues/18646) (P2) | **7 comments** | **WhatsApp group targeting broken** — `send_message` with `@g.us` JID routes to home channel instead of group |
| [#52919](https://github.com/NousResearch/hermes-agent/issues/52919) (P1, CLOSED) | **6 comments** | **Nix build broken** — regression from package-lock.json update, affecting all Nix users |
| [#31733](https://github.com/NousResearch/hermes-agent/issues/31733) (P1) | **6 comments** | **Telegram image delivery mismatch** — generated images in new cache path don't deliver via MEDIA, but legacy cache works |

### Analysis
The most commented issues cluster around **message delivery reliability** (Telegram, WhatsApp, cron) and **CI/infrastructure health** (skills index, Nix build). The high comment count on long-standing issues (#38240, 24 days open) suggests maintainers are engaging but fixes are complex. The cronjob tool bug (#34120) was resolved today, which should reduce user frustration.

---

## Bugs & Stability

### Critical/High Severity (P1) Bugs

| Issue | Description | Fix PR Exists? |
|---|---|---|
| [#31733](https://github.com/NousResearch/hermes-agent/issues/31733) | **Telegram image delivery** — new cache path not recognized by MEDIA delivery | No |
| [#40170](https://github.com/NousResearch/hermes-agent/issues/40170) | **Security: Honcho memory leak** — customer-facing gateway injects user's memory into API calls via `<memory-context>` block | No |
| [#52919](https://github.com/NousResearch/hermes-agent/issues/52919) (CLOSED) | **Nix build broken** by dependency changes | ✅ Closed |
| [#2743](https://github.com/NousResearch/hermes-agent/issues/2743) | **Command injection** via `shell=True` in subprocess calls (3+ affected files) | No (PR [#2830](https://github.com/NousResearch/hermes-agent/pull/2830) for CI audit, not fixing injection) |

### Medium Severity (P2) Bugs Reported Today

| Issue | Description | Fix PR Exists? |
|---|---|---|
| [#53461](https://github.com/NousResearch/hermes-agent/issues/53461) | `_count_skills rglob` blocks asyncio event loop >10s on Windows → WS disconnect → gateway restart | ✅ PR [#53490](https://github.com/NousResearch/hermes-agent/pull/53490) |
| [#53449](https://github.com/NousResearch/hermes-agent/issues/53449) | **Telegram message duplication** — short replies delivered twice when stream flags lost | No |
| [#53424](https://github.com/NousResearch/hermes-agent/issues/53424) | **Windows console flashing** — `conhost.exe` from missing `CREATE_NO_WINDOW` | No (but related PR [#53475](https://github.com/NousResearch/hermes-agent/pull/53475) fixes WSL path issue) |
| [#53443](https://github.com/NousResearch/hermes-agent/issues/53443) | **QQ bot** `connect()` missing `is_reconnect` kwarg → TypeError on startup | No |
| [#53477](https://github.com/NousResearch/hermes-agent/issues/53477) | **Feishu/Lark websocket** — keepalive timeout → silent deaf agent (process stays up) | No |
| [#53425](https://github.com/NousResearch/hermes-agent/issues/53425) | **Windows desktop** — Python backend orphan on exit, port conflict (Chinese locale) | No (duplicate) |
| [#53370](https://github.com/NousResearch/hermes-agent/issues/53370) | **Windows console flash** — `gh auth token` spawns console window | ✅ PR in progress |
| [#53403](https://github.com/NousResearch/hermes-agent/issues/53403) | **Skill install crash** — `Path.relative_to` fails on symlinked paths | ✅ PR [#53493](https://github.com/NousResearch/hermes-agent/pull/53493) |

### Low Severity (P3) Bugs

- [#53432](https://github.com/NousResearch/hermes-agent/issues/53432) — `_expand_tilde()` mishandles `~//foo` (consecutive slashes) → ✅ PR [#53487](https://github.com/NousResearch/hermes-agent/pull/53487)
- [#53455](https://github.com/NousResearch/hermes-agent/issues/53455) — `vision_analyze` passes invalid temperature to `kimi-k2.7-code` → ✅ PR [#53495](https://github.com/NousResearch/hermes-agent/pull/53495)
- [#53441](https://github.com/NousResearch/hermes-agent/issues/53441) — Desktop audio endpoints ignore active profile config → ✅ PR [#53488](https://github.com/NousResearch/hermes-agent/pull/53488)
- [#53224](https://github.com/NousResearch/hermes-agent/issues/53224) — Desktop updater dirties source checkout

### Stability Pattern
**Windows platform issues dominate today's bug reports** — at least 6 distinct Windows-specific bugs. The `CREATE_NO_WINDOW` missing flag appears in multiple reports (#33424, #33070, #53016). Several duplicates suggest users are independently hitting the same issue and creating separate reports.

---

## Feature Requests & Roadmap Signals

| Issue | Feature | Likely Next Version? |
|---|---|---|
| [#13490](https://github.com/NousResearch/hermes-agent/issues/13490) | **Configurable TUI status bar** — fields, layout, skin colors (2 comments, 24 days old) | **Unlikely** — no maintainer engagement |
| [#53402](https://github.com/NousResearch/hermes-agent/pull/53402) | **Task-engine prerequisite baseline** — new `tools/task_engine_contracts.py` and `task_engine_primitives.py` | **50%** — first PR of a stack, but merging shows interest |
| [#53486](https://github.com/NousResearch/hermes-agent/pull/53486) | **Hide memory tool when built-in memory disabled** — UX polish | Likely (small, focused) |
| [#53477](https://github.com/NousResearch/hermes-agent/issues/53477) | **Feishu websocket reconnect** — in-process reconnection, not process supervision | **Likely** — P2, affects production Lark agents |

### Roadmap Prediction
The **Windows stability** issues (console flashing, orphan backends) are likely to receive priority given the volume of reports. The **task-engine** PR (#53402) signals a new subsystem in development. The **i18n** PR [#38846](https://github.com/NousResearch/hermes-agent/pull/38846) (15 languages, 861 keys) has been open since June 4 with updates — may land in next release.

---

## User Feedback Summary

### Pain Points (High Frequency)
1. **Windows desktop experience** — Console flashing (#53016, #53424, #53370), orphaned processes (#53425), WSL path breakage (#53475)
2. **Message delivery failures** — Telegram duplicates (#53449), WhatsApp group routing (#18646), Feishu silent deaf agent (#53477)
3. **Build/CI breaks** — Nix build regression (#52919), skills index stale (#38240)

### Use Cases
- **Recurring news digests** via cron (Issue #34120) — user using Grok 4.3, Discord integration
- **Multi-platform chat** — Telegram, WhatsApp, Feishu/Lark, QQ bot
- **Local/self-hosted** — vLLM + dual A6000 setup (Issue #20840)

### Satisfaction Signals
- High contributor engagement — 50 PRs updated, many with "fix" in title
- Users reporting bugs with fixes already attached (#53493, #53495, #53487) suggests active developer community
- Desktop i18n PR (#38846) with 15 languages showing international user interest

### Dissatisfaction Signals
- Multiple duplicate bugs for same Windows issues (user frustration)
- No new releases — users reporting bugs that may already be fixed in main but unreleased
- P1 security issue (#40170 Honcho memory leak) open for 22 days without fix PR

---

## Backlog Watch

### Critical Issues Needing Maintainer Attention

| Issue | Days Open | Last Updated | Why Critical |
|---|---|---|---|
| [#2743](https://github.com/NousResearch/hermes-agent/issues/2743) (P1, security) | **95 days** | 2026-06-27 | Command injection via `shell=True` — multiple files affected, no fix merged |
| [#40170](https://github.com/NousResearch/hermes-agent/issues/40170) (P1, security) | **22 days** | 2026-06-27 | Honcho memory provider leaks user recall into API calls — customer-facing |
| [#31733](https://github.com/NousResearch/hermes-agent/issues/31733) (P1) | **33 days** | 2026-06-27 | Telegram image delivery broken for new cache path |
| [#20840](https://github.com/NousResearch/hermes-agent/issues/20840) (P3) | **52 days** | 2026-06-27 | Hardware setup question (dual A6000, vLLM) — unanswered, user likely blocked |
| [#38240](https://github.com/NousResearch/hermes-agent/issues/38240) (P3) | **24 days** | 2026-06-27 | Skills index degraded — CI/CD pipeline issue affecting docs |

### Long-Standing PRs

| PR | Days Open | Summary |
|---|---|---|
| [#2830](https://github.com/NousResearch/hermes-agent/pull/2830) (P2, security) | **95 days** | Expand supply chain CI audit beyond base64 — 20 new checks, no merge activity |
| [#38846](https://github.com/NousResearch/hermes-agent/pull/38846) (P3) | **23 days** | Desktop i18n with 15 languages — major UX improvement, last synced 2026-06-06 |
| [#49549](https://github.com/NousResearch/hermes-agent/pull/49549) (P2, security) | **7 days** | 13 Electron security fixes — crash handling, SSRF, IPC gaps |
| [#29249](https://github.com/NousResearch/hermes-agent/pull/29249) (P1, security) | **38 days** | Require operator opt-in for plugin `tool_override` — prevents silent tool replacement |

### Analysis
Three P1 security issues (#2743, #40170, #29249 PR) remain unaddressed for extended periods, suggesting either resource constraints or prioritization of feature work over security hardening. The 95-day-old command injection issue (#2743) is particularly concerning given the project's production use in multi-platform deployments.

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

# PicoClaw Project Digest — 2026-06-27

## Today's Overview
PicoClaw shows **moderately high activity** in the past 24 hours. 4 issues were updated (3 remain open, 1 closed) and **13 pull requests** were touched (8 merged/closed, 5 open). No new releases were published. The majority of PRs focus on **error-handling hygiene** (explicitly ignoring `resp.Body.Close()` and `json.Encode` errors across multiple subsystems) and minor infra cleanup (bumping Docker base images, deduplicating `.gitignore` entries). One security-related fix (SSRF guard for ISATAP IPv6 literals, #3143) was merged. Overall, the project is in a **maintenance and polish phase** with active community reporting of both bugs and feature requests.

## Releases
**None** — no new versions were published in the last 24 hours.

---

## Project Progress (Merged/Closed PRs Today)
**8 PRs were merged/closed**, covering:

| PR | Area | Summary |
|----|------|---------|
| [#3181](https://github.com/sipeed/picoclaw/pull/3181) | Gateway | Guard startup info assertions against missing/malformed sections |
| [#3143](https://github.com/sipeed/picoclaw/pull/3143) | Web (SSRF) | Block private IPv4 embeds in ISATAP IPv6 literals (security fix) |
| [#3187](https://github.com/sipeed/picoclaw/pull/3187) | Tests | Explicitly ignore `resp.Body.Close()` errors in `pkg/utils` tests |
| [#3188](https://github.com/sipeed/picoclaw/pull/3188) | Health | Explicitly ignore `json.Encode` errors in health handler responses |
| [#3186](https://github.com/sipeed/picoclaw/pull/3186) | Membench | Ignore `resp.Body.Close()` after `io.ReadAll` in LLM retry loop |
| [#3185](https://github.com/sipeed/picoclaw/pull/3185) | Updater | Ignore `resp2.Body.Close()` error after checksum download |
| [#3184](https://github.com/sipeed/picoclaw/pull/3184) | Channels | Ignore `resp.Body.Close()` errors in websocket dial cleanup (Pico, WhatsApp) |
| [#3183](https://github.com/sipeed/picoclaw/pull/3183) | OneBot | Ignore `resp.Body.Close()` after websocket dial |

**Key advancement**: The ISATAP SSRF fix (#3143) closes a bypass vector reported in issue #3074, improving the security of `web_fetch`.

---

## Community Hot Topics

### Most Discussed Issues
1. **[#3150](https://github.com/sipeed/picoclaw/issues/3150) [OPEN] [stale] — "它给自己整失忆了" (It gave itself amnesia)**
   - 3 comments, author svier0
   - User reports unexpected memory loss behavior. The stale label suggests it has been open for a week without resolution. Likely relates to context retention or conversation history management.

2. **[#3088](https://github.com/sipeed/picoclaw/issues/3088) [OPEN] [help wanted, priority: high] — Use vodozemac instead of libolm**
   - 3 comments, 2 reactions 👍
   - Community strongly supports replacing the unmaintained/insecure `libolm` with `vodozemac` (the official Matrix replacement). This is the **highest-priority open feature request** and signals a security-driven migration.

3. **[#3094](https://github.com/sipeed/picoclaw/issues/3094) [CLOSED] [stale] — Duplicate messages from async subagent spawn**
   - 3 comments, author v2up-32mb
   - Closed — the `ForUser` field was being used for both direct push and main agent summary, causing duplicate messages on channels (Feishu/Telegram). Now resolved.

### Underlying Needs
- **Memory/context retention** (#3150) — users expect persistent agent memory across sessions.
- **Cryptographic dependency modernization** (#3088) — security-conscious users want to move off deprecated libolm.
- **Message deduplication** (#3094) — users running multi-agent workflows need clean, non-redundant output.

---

## Bugs & Stability

### New Bugs (reported today)
| Issue | Severity | Description | Fix PR? |
|-------|----------|-------------|---------|
| [#3182](https://github.com/sipeed/picoclaw/issues/3182) | **High** | Android version: service won't launch; full permissions granted but path configuration fails (user-provided screenshot shows error) | None yet |

### Stability Trends
- The **large wave of error-handling PRs** (#3183–3189) indicates maintainers are systematically addressing lint warnings and potential panics from unhandled `Close()` errors across HTTP/websocket paths. This is proactive **hardening work**, not a response to user-reported crashes.
- The **ISATAP SSRF bypass fix** (#3143) addresses a genuine security vulnerability in the web fetch tool.
- Issue **#3150** (memory loss) remains open and stale — could indicate a harder-to-reproduce bug.

---

## Feature Requests & Roadmap Signals

### Active Feature Requests
| Issue | Feature | Status | Likelihood for Next Release |
|-------|---------|--------|---------------------------|
| [#3088](https://github.com/sipeed/picoclaw/issues/3088) | Replace `libolm` with `vodozemac` | **Help wanted, priority: high** | **High** — labeled priority, maintainer attention, clear migration path |
| [#3150](https://github.com/sipeed/picoclaw/issues/3150) | Persistent memory (anti-amnesia) | Stale bug → could become feature request | **Medium** — depends on root cause analysis |

### Predicted Next Features
- **vodozemac integration** (Issue #3088) — likely to land in the next minor release given its security impact and maintainer prioritization.
- **Improved Android compatibility** — Issue #3182 may trigger a targeted fix for Android path handling and service startup.

---

## User Feedback Summary

### Pain Points
1. **Android launch failure** (#3182) — new user blocked entirely from using PicoClaw on Android; path configuration error despite full permissions.
2. **Agent memory loss** (#3150) — Chinese-language user reports the agent's context disappears ("失忆了"), impacting conversation continuity.
3. **Duplicate messages in async workflows** (now fixed, #3094) — previously affected users relying on spawn subagents for complex tasks.

### Use Cases
- **Multi-agent collaboration** (#3094) — users are running asynchronous subagent workflows (spawn tool), indicating advanced usage beyond simple chat.
- **Cross-platform deployment** (#3182, #3188) — users expect Android and cloud server (health endpoints) support.

### Satisfaction Signals
- The high-priority **vodozemac request** (#3088) received 2 👍 reactions in a low-traffic issue, suggesting community alignment with maintainer priorities on security modernization.
- No widespread dissatisfaction expressed — the error-handling PRs are preemptive rather than reactive.

---

## Backlog Watch

| Issue/PR | Age | Status | Concern |
|----------|-----|--------|---------|
| [#3150](https://github.com/sipeed/picoclaw/issues/3150) | 8 days | Open, stale | Memory loss bug with no maintainer response — could be latent regression |
| [#3088](https://github.com/sipeed/picoclaw/issues/3088) | 18 days | Open, help wanted | High-priority feature with clear solution — needs assignee or implementation plan |
| [#3182](https://github.com/sipeed/picoclaw/issues/3182) | <1 day | Open, no comments | Android launch blocker — needs immediate triage |

**Maintainer Attention Needed:**
- **#3088** (vodozemac) — assign a maintainer and set milestone to avoid stagnation.
- **#3150** (memory loss) — request reproduction steps or environment details from the reporter.
- **#3182** (Android) — first-response triage (ask for logs, device info, suggest workaround).

---

*Digest generated 2026-06-27 from sipeed/picoclaw GitHub data. All links to sipeed/picoclaw Issue/PR URLs.*

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

# NanoClaw Project Digest — 2026-06-27

## Today's Overview
NanoClaw shows **moderate activity** today with 3 issues updated (1 open, 2 closed) and 5 pull requests updated (4 open, 1 merged/closed). No new releases are reported. The project is progressing steadily, with two notable feature PRs targeting per-group model overrides for OpenCode agents and a new dashboard push mechanism. One fix PR addressing WhatsApp group encryption was just submitted but is still pending merge. A critical bug was identified where the `/update-skills` command silently fails to refresh adapter code or pinned dependencies for already-installed channels, which undermines the CHANGELOG-recommended migration path.

## Releases
*None — no new versions published today.*

## Project Progress
- **Fixed (Merged):**
  - [#2859 — fix(migrate-v2): don't SELECT is_main from v1 registered_groups](https://github.com/nanocoai/nanoclaw/pull/2859) (closed/merged 2026-06-26): Resolves a crash in the v2 migration step (`1b-db`) for older v1 installs (e.g. 1.1.0) where the `is_main` column does not exist. Previously blocked database creation and cascading failure into sessions/tasks steps.

## Community Hot Topics
- **#2868 — [OPEN] `/update-skills` is a silent no-op for installed channels** ([Issue](https://github.com/nanocoai/nanoclaw/issues/2868)) — *1 comment, 0 reactions.* This bug is the most critical open issue today; the pre-flight logic skips the code and dependency refresh steps for already-installed channels, meaning the CHANGELOG directive to "re-run `/add-<channel>`" cannot be followed via `/update-skills`. User pain: they are left without a clear migration path.
- **#2872 — [OPEN] feat: per-group model override via container_configs.model** ([PR](https://github.com/nanocoai/nanoclaw/pull/2872)) — This feature PR proposes enabling each OpenCode agent group to run a different model by reading `container_configs.model` at spawn time and injecting it as `OPENCODE_MODEL`. No comments yet, but addresses a common multi-tenant scalability request.
- **#2871 — [OPEN] feat: dashboard pusher with OpenCode support** ([PR](https://github.com/nanocoai/nanoclaw/pull/2871)) — Adds a periodic state snapshot push to a dedicated dashboard server. No comments yet; likely early-stage infrastructure work.

## Bugs & Stability
| Severity | Bug | Fix PR Exists? | Notes |
|---|---|---|---|
| **Critical** | [#2868 — `/update-skills` silent no-op for installed channels](https://github.com/nanocoai/nanoclaw/issues/2868) (open) | No | Blocks CHANGELOG migration path; maintainer attention recommended. |
| **Low** | [#2860 — libsignal session debug spam (incl. key material)](https://github.com/nanocoai/nanoclaw/pull/2860) (open PR) | Yes (in review) | Not a functional bug but a privacy/security concern—console-inspectable session key material in logs. |
| **Info** | [#2869 — filed in error, closed](https://github.com/nanocoai/nanoclaw/issues/2869) | N/A | Closed as wrong-repo noise. |

## Feature Requests & Roadmap Signals
- **Per-group model overrides** (PR #2872) and **dashboard push infrastructure** (PR #2871) are the most concrete signals for the upcoming version. Both originate from the same contributor (grantland) and are likely planned for the next minor release.
- **Auto-prompt registration on new group join** ([Issue #1275](https://github.com/nanocoai/nanoclaw/issues/1275), closed 2026-06-26 after 99 days) was finally closed today without resolution — suggesting it may have been shelved or deprioritized. This feature would have improved first-time user experience but is not currently on the roadmap.

## User Feedback Summary
- **Pain points:**
  - The `/update-skills` silent no-op (Issue #2868) leaves users unable to reliably upgrade installed channels, creating a trust gap in the migration process.
  - The v2 migration crash for older v1 installs (PR #2859 fix) frustrated users on version 1.1.0 who attempted database upgrade — now resolved.
- **Use cases:**
  - Multi-group OpenCode deployment with per-group model tuning (PR #2872) suggests real demand for heterogeneous agent configurations.
  - Dashboard integration (PR #2871) indicates a need for centralized monitoring.
- **Satisfaction:** No strong positive signals today; the community is primarily engaged in bug reporting and infrastructure feature work.

## Backlog Watch
- **#2868** (open 1 day, critical bug) — needs immediate maintainer attention to fix the `/update-skills` skip logic.
- **#1275** (auto-prompt on group join, closed without resolution after 99 days) — no longer active, but represents a gap in onboarding UX that may resurface.
- **#2859** (merged fix for v2 migration) is resolved and can be removed from watchlist.

**Overall health:** Moderate. Active development is happening (two feature PRs, one fix merge), but a critical bug (#2868) with no fix in progress is a risk for users relying on the migration path. Community engagement is low (few comments/reactions). The project appears to be in a **feature-building phase** with infrastructure expansion (dashboard, per-group models) alongside bug fixing.

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

Here is the NullClaw project digest for June 27, 2026.

---

## NullClaw Project Digest – 2026-06-27

### 1. Today's Overview
The NullClaw project is in a **low-activity maintenance phase** as of June 27, 2026. Over the past 24 hours, only one issue received updates, while zero pull requests were updated or merged, and no new releases were published. The single active item is a long-standing build failure bug on Android/Termux, which received its first comment in over two months today. With no PRs or releases advancing the codebase, project momentum appears stalled, though the maintainer did engage with the open issue.

### 2. Releases
**No new releases** were published in the last 24 hours. The latest stable version remains **v2026.4.17** (released April 17, 2026).

### 3. Project Progress
**No pull requests** were updated, merged, or closed today. No features, fixes, or improvements advanced through the PR pipeline.

### 4. Community Hot Topics
- **[#868] [bug] zig build fails on Android/Termux (aarch64) with AccessDenied** ([link](https://github.com/nullclaw/nullclaw/issues/868))
  - **Status:** Open (since 2026-04-23)
  - **Activity:** 1 comment today, 4 total, 0 reactions
  - **Analysis:** This is the most active (and only active) thread today. The underlying need is cross-platform build reliability, specifically for ARM64 Android environments (Termux). The user reported a `linkat` permission error during compilation with Zig 0.16.0. The community is likely waiting for either a build script patch or guidance on alternative build methods. This issue has remained open for over two months without a fix, which may indicate a low priority or a challenging environment-specific problem.

### 5. Bugs & Stability
- **Critical:** **Issue #868 – Zig build fails on Android/Termux (aarch64)** ([link](https://github.com/nullclaw/nullclaw/issues/868))
  - **Severity:** High (blocks builds on a significant mobile platform)
  - **Details:** Running `zig build -Doptimize=ReleaseSmall` fails with `AccessDenied` when trying to link a temporary file into `.zig`. No fix PR exists.
  - **Impact:** Users on Termux (Android) cannot compile NullClaw from source. This may affect developers and self-hosters on mobile devices.
  - **Note:** This is a regression introduced post-v2026.4.17, not a daily regression.

### 6. Feature Requests & Roadmap Signals
No new feature requests were raised today. The single open issue is a build bug, not a feature request. No roadmap signals or feature hints were observed in the last 24 hours.

### 7. User Feedback Summary
- **Pain Point:** The primary user feedback this period is the frustration of a broken build on Android/Termux. The reporter has waited two months for a resolution.
- **Use Case:** Users are attempting to compile NullClaw for personal use on mobile ARM64 devices (Redmi Note 9, LineageOS). The failure blocks local development and testing.
- **Satisfaction:** Likely low for Termux/aarch64 users, as the issue is stale and unresolved.

### 8. Backlog Watch
- **[Issue #868]** – This issue has been open for **65 days** with no maintainer assignment, no fix, and only 4 comments. It is the top item requiring maintainer attention. Without a response or a workaround, it risks becoming a permanent blocker for Android-based contributors. A maintainer comment or a temporary build instruction would be valuable.

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

# IronClaw Project Digest — 2026-06-27

## Today's Overview

IronClaw shows high development velocity with 50 PRs updated and 23 issues active in the last 24 hours. The project is deep into a "codex" phase, porting legacy Playwright browser test coverage to the Reborn WebUI v2 stack, with multiple massive XL-sized PRs advancing in parallel. A major release (0.29.1) is pending review, bringing breaking API changes to core crates. The project continues to surface and fix stability issues around tool approval, automation lifecycle, and OAuth channel setup, while performance teams are actively hill-climbing benchmarks on DeepSeek-V4-Flash.

## Releases

**No new releases published today.** The release PR #5311 (`ironclaw: 0.24.0 → 0.29.1`) remains open under review. If merged, it includes:
- **Breaking changes** in `ironclaw_common` (0.4.2→0.5.0) and `ironclaw_skills` (0.3.0→0.4.0) — consumers should review API changes before upgrading
- **Compatible changes** in `ironclaw_safety` (0.2.2→0.2.3)
- No migration notes available yet

## Project Progress

**16 PRs merged/closed today**, dominated by the codex porting effort:

- **#5347 (closed)** — Ported Reborn Responses API input handling and workflow contracts
- **#5346 (closed)** — Aligned Reborn runtime tool surface for migrated coverage needs
- **#5366 (closed)** — Flipped "Always allow eligible tools" to **default ON** (merged, closes #5364)
- **#5197 (closed)** — Fixed disabled tool causing invocation of unrelated tools
- **#5227 (closed)** — Fixed run failure messages attaching to wrong conversation turns
- **#5283 (closed)** — Fixed "Approve & always allow" persistence for `nearai.web_search`
- **#5009 (closed)** — Brought live Slack OAuth path to structural DM-parity (security fix)

Several large open PRs are nearing completion in the codex series: #5374 (extensions management), #5375 (projects/settings), #5372 (auth/approval UX), #5373 (channel pairing), #5371 (chat history), and #5376 (E2E documentation).

## Community Hot Topics

| Item | Type | Comments | Key Signal |
|------|------|----------|------------|
| [#5009](https://github.com/nearai/ironclaw/issues/5009) — Slack OAuth DM-parity | Closed Issue | 2 | Security fix landed after review |
| [#5283](https://github.com/nearai/ironclaw/issues/5283) — Approval persistence | Closed Issue | 2 | UX regression fixed |
| [#5331](https://github.com/nearai/ironclaw/issues/5331) — Tool auto-approve flakiness | Open Issue | 1 | Medium-confidence engine bug, needs owner |
| [#2355](https://github.com/nearai/ironclaw/issues/2355) — Multi-identity browser via CDP | Open Epic | 1 | Persistent architectural effort ongoing |
| [#5320](https://github.com/nearai/ironclaw/issues/5320) — Automation stops after planning | Open Issue | 1 | Product workflow gap |

The most commented PRs are all codex ports (#5374, #5375, #5372, #5373, #5371) — these represent the core team's focused push to bring legacy E2E coverage to the Reborn stack.

## Bugs & Stability

### High Severity
- **#5331** — Tool-approval "always" may not auto-approve the next same-tool call (engine v2). *Medium confidence; no fix PR yet.*
- **#5320 / #5322 / #5323** — Automation creation fails due to: planning stopping prematurely, runner lease expiry, and general timeouts. *Cluster of automation reliability issues.*

### Medium Severity
- **#5337** — Wasm-channel OAuth setup can't start first-time OAuth flow (auth descriptor never seeded). *Blocks fresh extension configuration.*
- **#5332** — Coverage `--all-features` auto-enables forward-feature gates, running deferred security tests that fail. *Structural gating bug affecting CI.*
- **#5330** — E2E skills-tab tests assert v2 SPA while harness serves legacy gateway. *Test/harness mismatch.*
- **#5333** — Reborn composer keeps submitted message visible briefly after send. *UX polish issue.*

### Lower Severity
- **#5329** — Mock-LLM post-tool-summary matcher too broad (10 tests failing). *Test-side only.*
- **#5319** — Automations created with UTC schedule without timezone confirmation. *UX confusion.*
- **#5221** — Harness backlog for deepseek-v4-flash — 9 open candidates tracked.

*Note: #5366 (fix: default "always allow" to ON) directly addresses the approval-prompt fatigue reported in #5364 and #5283, reducing friction for new users.*

## Feature Requests & Roadmap Signals

| Request | Issue | Likelihood for Next Release |
|---------|-------|---------------------------|
| Default "Always allow eligible tools" to ON | #5364 (closed) | ✅ **Already merged** |
| Persistent multi-identity Chrome + CDP browsing | #2355 | Medium — epic in progress |
| Non-Slack channel personal pairing (WebUI) | #5368 | High — opened today, follow-up to #5362 |
| Admin-shared tools & skills with per-user auth (Reborn only) | #5261 | High — epic actively tracked |
| Automation timezone confirmation before scheduling | #5319 | Medium — UX pain point |
| Reborn harness fixes from benchmark hill-climbing | #5350 | High — active performance work |

The codex porting surge (#5370–#5376) signals that the team is prioritizing feature parity between Reborn and legacy stacks, which will unblock future development on the new architecture.

## User Feedback Summary

**Pain points (reported by sunglow666 across multiple issues):**
- Automation reliability is a primary frustration — creation fails by planning stops, runner lease expiry, and timeouts
- Gmail extension discovery is inconsistent — same prompt sometimes reports no extension available
- UTC scheduling without timezone confirmation creates confusing "Next Run" displays
- Tool-disabled state causes the assistant to invoke unrelated tools instead of reporting unavailability
- Run failure messages appear under wrong conversation turns, making the timeline misleading

**Satisfaction signals:**
- "Always allow eligible tools" default flip (#5364) directly addresses the most common new-user complaint about approval prompt fatigue
- The codex porting (enabling legacy test coverage on Reborn) shows investment in stability

## Backlog Watch

| Item | Type | Created | Last Updated | Days Stale | Notes |
|------|------|---------|-------------|------------|-------|
| [#2355](https://github.com/nearai/ironclaw/issues/2355) — Multi-identity Chrome/CDP | Epic | 2026-04-12 | 2026-06-26 | 76 days | Low activity on major architectural feature |
| [#4108](https://github.com/nearai/ironclaw/issues/4108) — Nightly E2E failure | Failure | 2026-05-27 | 2026-06-27 | 31 days | Recurring failure, no comments from maintainers |
| [#5221](https://github.com/nearai/ironclaw/issues/5221) — Harness backlog (deepseek-v4-flash) | Backlog | 2026-06-25 | 2026-06-26 | 2 days | 9 candidates, 8 hillclimb steps spent |
| [#5315](https://github.com/nearai/ironclaw/issues/5315) — Daily failure taxonomy | Meta | 2026-06-26 | 2026-06-26 | 1 day | Fresh — keep watching |
| [#5271](https://github.com/nearai/ironclaw/issues/5271) — Dependency bump (47 updates) | PR | 2026-06-25 | 2026-06-27 | 2 days | High-risk (XL, risk: high), includes refinery 0.8→0.9 |

**Notable:** The nightly E2E failure (#4108) has gone 31 days without maintainer follow-up — this may indicate test infrastructure debt. The dependency bump PR #5271 is labeled `risk: high` with 47 updates including major version bumps for `refinery` (0.8→0.9), requiring careful review before merge.

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

# LobsterAI Project Digest — 2026-06-27

## Today's Overview
Project activity is **high**, with 11 PRs updated in the last 24 hours (10 closed/merged, 1 open) and 2 new open issues. The release of **LobsterAI 2026.6.26** brings significant enhancements to the OpenClaw runtime and introduces a new "plan mode" workflow for cowork sessions. The team is actively cleaning up stale PRs from April, merging 8 long-pending fixes today, while also shipping two critical renderer stability patches. The two new bug reports highlight Windows-specific installation and backup freezes that require urgent attention.

## Releases
**New version: LobsterAI 2026.6.26** — released 2026-06-26

### What's Changed
- **feat(openclaw):** Upgraded runtime to v2026.6.1 ([PR #2209](https://github.com/netease-youdao/LobsterAI/pull/2209))
- **feat(cowork):** Added "plan mode" workflow for collaborative sessions ([PR #2183](https://github.com/netease-youdao/LobsterAI/pull/2183))
- **fix(openclaw):** Support for upgraded IM plugin instantiation (details truncated in changelog)

**⚠️ Migration Notes:**
- The OpenClaw runtime upgrade (v2026.6.1) may require updating any custom IM plugins to use the new instantiation API.
- The new "plan mode" in cowork sessions is additive; existing workflows should continue to work without changes.

**No breaking changes reported.**

## Project Progress
**Today's merged/closed PRs (10 of 11 updated):**

| PR | Area | Description | Status |
|----|------|-------------|--------|
| [#1446](https://github.com/netease-youdao/LobsterAI/pull/1446) | openclaw | Fix gateway infinite restart loop (race condition + zombie process) | ✅ Closed (stale, merged) |
| [#1448](https://github.com/netease-youdao/LobsterAI/pull/1448) | i18n | Agent settings page delete button & skill selector now localized | ✅ Closed (stale, merged) |
| [#1449](https://github.com/netease-youdao/LobsterAI/pull/1449) | cowork | Scheduled task execution records now grouped/folded in sidebar | ✅ Closed (stale, merged) |
| [#1453](https://github.com/netease-youdao/LobsterAI/pull/1453) | skills | Stopped disabled skill prompts from being injected into conversations | ✅ Closed (stale, merged) |
| [#1454](https://github.com/netease-youdao/LobsterAI/pull/1454) | scheduled-tasks | Fixed silent failure when creating non-repeating tasks with cleared date | ✅ Closed (stale, merged) |
| [#1456](https://github.com/netease-youdao/LobsterAI/pull/1456) | shortcuts | Added duplicate keybinding detection to prevent silent conflicts | ✅ Closed (stale, merged) |
| [#2065](https://github.com/netease-youdao/LobsterAI/pull/2065) | agent | Replaced name-based Agent IDs with short UUIDs to prevent data resurrection | 🔴 Open (stale) |
| [#2213](https://github.com/netease-youdao/LobsterAI/pull/2213) | renderer, cowork, artifacts | Fix Mermaid error SVG leaking; keep skill search popover open on focus | ✅ Closed |
| [#2212](https://github.com/netease-youdao/LobsterAI/pull/2212) | renderer, cowork | Prevent skill submenu from closing when focus remains inside | ✅ Closed |
| [#2211](https://github.com/netease-youdao/LobsterAI/pull/2211) | openclaw | Sort imports in final patch decision test (housekeeping) | ✅ Closed |
| [#2210](https://github.com/netease-youdao/LobsterAI/pull/2210) | renderer, artifacts | Validate Mermaid content before rendering; clean up DOM after error | ✅ Closed |

**Key observations:**
- 8 stale PRs from April 2026 were finally merged today, clearing a significant maintenance backlog.
- Renderer stability (Mermaid, skill popover) received two targeted fixes in the last 24 hours.
- Agent ID generation (UUID-based) is the only open PR; it may be waiting for additional cleanup commits as noted in its summary.

## Community Hot Topics
**#2215** [OPEN] — "[Installer] Resource extraction failed: could not start extractor process" ([Issue](https://github.com/netease-youdao/LobsterAI/issues/2215))
- **Author:** woxinsj | **Created:** 2026-06-27 | **Comments:** 0 | **👍:** 0
- **Analysis:** The reporter has conducted an exceptionally thorough root-cause analysis, tracing the error from a misleading C:\ path to the actual installation at G:\. They identified the error code `ERROR_BAD_ENVIRONMENT (-2147450726)` and even unpacked the NSIS installer to inspect the installation script. This suggests a **long-standing environmental issue** (possibly corrupt registry keys, drive-letter mismatch, or a Windows sandbox feature) that the installer does not gracefully handle. The underlying need is for better error messaging and automatic detection of previous installations in non-default paths.

**#2214** [OPEN] — "Desktop: 'Data Backup' feature causes main process to freeze (not responding)" ([Issue](https://github.com/netease-youdao/LobsterAI/issues/2214))
- **Author:** woxinsj | **Created:** 2026-06-26 | **Updated:** 2026-06-27 | **Comments:** 0 | **👍:** 0
- **Severity:** **High** — 100% reproducible, user must force-kill the process. The database is **71.6 MB in WAL mode** with continuous writes from hundreds of daily messages.
- **Analysis:** The backup operation is likely performing a blocking file copy or VACUUM operation on the SQLite database while the gateway is still writing to it. This is a classic **long-running synchronous I/O in the main process** antipattern. The fix should either: (a) perform backup asynchronously in a worker thread, (b) lock the database before backup, or (c) take a snapshot via SQLite backup API.

## Bugs & Stability
| Severity | Issue | Description | Fix Status |
|----------|-------|-------------|------------|
| **🔴 Critical** | [#2214](https://github.com/netease-youdao/LobsterAI/issues/2214) | Data backup → main process freeze (100% repro, force-kill required) | ❌ No fix PR yet |
| **🟡 High** | [#2215](https://github.com/netease-youdao/LobsterAI/issues/2215) | Installer fails with `ERROR_BAD_ENVIRONMENT` on non-C: drives | ❌ No fix PR yet |
| **🟡 Medium** | [#1453](https://github.com/netease-youdao/LobsterAI/pull/1453) | Disabled skills still inject prompts (fixed today) | ✅ Fixed in PR #1453 |
| **🟠 Medium** | [#1446](https://github.com/netease-youdao/LobsterAI/pull/1446) | Gateway infinite restart loop (race condition) | ✅ Fixed in PR #1446 |
| **🟢 Low** | [#1454](https://github.com/netease-youdao/LobsterAI/pull/1454) | Non-repeating task creation silently fails | ✅ Fixed in PR #1454 |
| **🟢 Low** | [#1456](https://github.com/netease-youdao/LobsterAI/pull/1456) | Duplicate shortcuts saved without warning | ✅ Fixed in PR #1456 |

**Renderer stability improvements today:**
- [#2213](https://github.com/netease-youdao/LobsterAI/pull/2213) — Prevents Mermaid error SVGs from leaking into the DOM; keeps skill search popover open when focus is inside the menu.
- [#2210](https://github.com/netease-youdao/LobsterAI/pull/2210) — Validates Mermaid syntax via `mermaid.parse()` before rendering, using the controlled error UI instead of raw error SVG.

## Feature Requests & Roadmap Signals
**Recently delivered:**
- **Plan mode for cowork sessions** ([PR #2183](https://github.com/netease-youdao/LobsterAI/pull/2183) in 2026.6.26 release) — suggests the team is investing in structured collaborative workflows.
- **Scheduled task grouping** ([PR #1449](https://github.com/netease-youdao/LobsterAI/pull/1449)) — addresses user pain point of sidebar clutter from recurring tasks.

**Likely in next release:**
- **UUID-based Agent IDs** ([PR #2065](https://github.com/netease-youdao/LobsterAI/pull/2065)) — This is open and awaiting additional cleanup for deleted agent data (workspace, sessions). It will likely land in the next release once the follow-up fix for orphaned cowork sessions is implemented.
- **Data backup stability** — Issue #2214 will almost certainly trigger a fix that moves backup I/O off the main thread.

## User Feedback Summary
**Positive signals:**
- The team merged 9 bug fixes today, showing strong commitment to stability.
- The new plan mode and task grouping are direct responses to user workflow complaints.

**Pain points:**
1. **Windows installation fragility** ([#2215](https://github.com/netease-youdao/LobsterAI/issues/2215)) — Users on non-default drives or with unusual environments face silent failures with no clear error guidance.
2. **Data backup freezes app** ([#2214](https://github.com/netease-youdao/LobsterAI/issues/2214)) — A major trust issue: users cannot safely back up their data without killing the process. This is especially risky for users with large SQLite databases (>50 MB) in WAL mode.
3. **Stale PR cleanup** — The fact that 8 fixes from April were only merged in late June suggests the review pipeline was backed up for ~3 months, potentially frustrating contributors.

**Satisfaction indicators:**
- The reporter of #2215 demonstrated exceptional technical depth in their analysis — a sign they care deeply about the product but feel the installer lacks robustness.

## Backlog Watch
**Issues/PRs needing maintainer attention:**

| Item | Age | Status | Why it matters |
|------|-----|--------|----------------|
| [#2065](https://github.com/netease-youdao/LobsterAI/pull/2065) — UUID Agent IDs | 30 days | Open (stale) | Core data integrity fix; author notes follow-up needed for orphaned session cleanup. Blocking merged? |
| [#1446](https://github.com/netease-youdao/LobsterAI/pull/1446) — Gateway restart loop | 85 days | Closed today | Was stale for 3 months before merging; check if any open issues remain on this bug class |
| [#1400](https://github.com/netease-youdao/LobsterAI/issues/1400) — (referenced by #1446) | ~90 days | Not visible in today's data | Original issue for gateway crash; verify it was closed alongside the fix PR |
| [#1439](https://github.com/netease-youdao/LobsterAI/issues/1439) — (referenced by #1453) | ~85 days | Not visible in today's data | Original issue for disabled skill injection; verify closed status |
| [#1437](https://github.com/netease-youdao/LobsterAI/issues/1437) — (referenced by #1454) | ~85 days | Not visible in today's data | Original issue for non-repeating task silent failure; verify closed status |

**Recommendation:** The maintainer should prioritize fixing the data backup freeze (#2214) and the installer extraction error (#2215) as they directly affect user trust and onboarding. The pending UUID Agent ID PR (#2065) should be unblocked by implementing the orphaned session cleanup noted in its summary.

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

No activity in the last 24 hours.

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

# Moltis Project Digest — 2026-06-27

## Today's Overview
Moltis experienced a quiet day with no new issues, no releases, and zero merged or closed pull requests. A single open pull request (#1135) was updated within the last 24 hours, representing the only visible activity. The project appears to be in a low-activity phase, with no bug reports, no regressions, and no community discussion threads surfacing today. While this may indicate stability, the absence of any merged work or issue resolution also suggests a possible pause in development velocity.

## Releases
No new releases were published today. The project has no recorded release history in the observed window.

## Project Progress
No pull requests were merged or closed today. No issues were resolved. The single open PR (#1135) remains under review but has not advanced to merge.

## Community Hot Topics
The only active item today is:

- **PR #1135 — browser: optional auto-screenshot after each action**  
  *Author: resumeparseeval | Created: 2026-06-26 | Updated: 2026-06-26 | Comments: 0 | 👍: 0*  
  [View PR](https://github.com/moltis-org/moltis/pull/1135)  
  This PR proposes capturing an automatic screenshot after every state-changing browser action, attaching it to the action's tool result so chat clients can render a per-step screenshot timeline. The implementation is placed at the single dispatch chokepoint in `BrowserManager::execute_action`.  
  **Analysis:** This feature addresses a clear user need for visual traceability in browser automation workflows. Zero comments or reactions suggest the PR may have been very recent or has not yet attracted reviewer attention.

## Bugs & Stability
No bugs, crashes, or regressions were reported today. The project experienced zero issue activity, indicating no new stability concerns have surfaced.

## Feature Requests & Roadmap Signals
The only feature signal today is **PR #1135** (auto-screenshot after each action), which is an enhancement rather than a bug fix. If accepted, this would likely land in the next minor release. No other feature requests or roadmap signals were observed.

## User Feedback Summary
No user feedback, pain points, or satisfaction signals were recorded today. The absence of issue reports, feature requests, or discussion comments makes it impossible to assess user sentiment from this window.

## Backlog Watch
No stale or long-unanswered issues or PRs were identified in this snapshot. The single open PR (#1135) is only one day old. No items require maintainer attention at this time.

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

Here is the structured project digest for **CoPaw (github.com/agentscope-ai/CoPaw)**, generated for **2026-06-27**.

---

## CoPaw Project Digest: 2026-06-27

### 1. Today's Overview
Activity is **very high**, dominated by the v2.0.0-beta.1 release and a coordinated sprint to improve backend/frontend unit test coverage. There are **40 open Pull Requests** and **12 open Issues** actively discussed. While the new beta introduces breaking changes (intended for developers), the community is flagging several pain points regarding stability, message delivery, and crashes, particularly with third-party model endpoints. The project is in a clear phase of industrializing its architecture while responding to real-world deployment friction.

### 2. Releases
**New Release: v2.0.0-beta.1**
- **Tag:** v2.0.0-beta.1
- **Status:** ⚠️ Early beta for QwenPaw 2.0.0, not for production.
- **Changelog:** `refactor: migrate agent`
- **Impact:** This release signals a major internal refactor (likely related to AgentScope 2.0). It is verified via a dedicated release-duty issue ([#5571](https://github.com/agentscope-ai/QwenPaw/issues/5571)) which tracks installation verification across platforms.
- **Migration Notes:** Users must expect breaking changes. A companion PR ([#5576](https://github.com/agentscope-ai/QwenPaw/pull/5576)) bumps the `agentscope` dependency to version `2.0.3`, suggesting deep integration changes.

### 3. Project Progress
**14 PRs were merged/closed today (from the data set of 40).** Key advancements include:
- **AgentScope 2.0 Cleanup:** PR [#5440](https://github.com/agentscope-ai/QwenPaw/pull/5440) (closed) fixed post-merge bugs, removing 1493 lines of code (+4 added) by cleaning up cancelled error handling and agent memory indexing.
- **Desktop & Tauri Stability:** PR [#5265](https://github.com/agentscope-ai/QwenPaw/pull/5265) (closed) added a graceful shutdown endpoint and fixed a Tauri lifecycle bug. PR [#5578](https://github.com/agentscope-ai/QwenPaw/pull/5578) (open) further patches the Tauri desktop verification flow.
- **UI/UX:** PR [#5436](https://github.com/agentscope-ai/QwenPaw/pull/5436) (closed) enabled drag-and-drop file upload onto the chat sender area. PR [#5213](https://github.com/agentscope-ai/QwenPaw/pull/5213) (closed) improved the MCP access policy layout for better responsiveness.
- **Model Management:** PR [#5297](https://github.com/agentscope-ai/QwenPaw/pull/5297) (closed) added batch test & batch delete for models, addressing a direct community pain point.

### 4. Community Hot Topics
- [#5563](https://github.com/agentscope-ai/QwenPaw/issues/5563) **(Feature Request - High Activity):** Users are frustrated by fragmented message spam during multi-step agent tasks. A fix PR [#5577](https://github.com/agentscope-ai/QwenPaw/pull/5577) is already open to add opt-in reply aggregation.
- [#5550](https://github.com/agentscope-ai/QwenPaw/issues/5550) **(Bug - High Activity):** A detailed report of Remote SSH plugin dependency loops and process residue on macOS. This points to a significant gap for users trying to manage remote infrastructure.
- [#5567](https://github.com/agentscope-ai/QwenPaw/issues/5567) **(Community Tooling - High Activity):** A user-created Skill that helps format GitHub issues. Shows strong community engagement and a desire for better self-service.
- **Test Coverage Sprint (hanson-hex):** A series of PRs ([#5409](https://github.com/agentscope-ai/QwenPaw/pull/5409), [#5423](https://github.com/agentscope-ai/QwenPaw/pull/5423), [#5434](https://github.com/agentscope-ai/QwenPaw/pull/5434), [#5438](https://github.com/agentscope-ai/QwenPaw/pull/5438), [#5581](https://github.com/agentscope-ai/QwenPaw/pull/5581)) are adding hundreds of unit tests (backend and frontend) to lock down the 2.0 contracts. This is a clear signal of the project maturing.

### 5. Bugs & Stability
Several critical and high-severity bugs were reported today:
- **Critical:** [#5579](https://github.com/agentscope-ai/QwenPaw/issues/5579) - **Conversation loss on abnormal interruption.** User reports that if the host reboots during an agent task, the entire conversation is lost. No checkpoint persistence exists. No fix PR yet.
- **High:** [#5573](https://github.com/agentscope-ai/QwenPaw/issues/5573) - **400 errors on DeepSeek V4 thinking mode** when using non-official API endpoints. This is a major blocker for users relying on proxy or third-party providers. No fix PR yet.
- **High:** [#5566](https://github.com/agentscope-ai/QwenPaw/issues/5566) - **Cron tasks generate silent but unwanted notifications**, and `channels send` CLI fails from background scripts. This undermines a key automation use-case. No fix PR yet.
- **Medium:** [#5561](https://github.com/agentscope-ai/QwenPaw/issues/5561) - **Feishu (Lark) bot drops long replies**, only sending as a file. No fix PR yet.
- **Medium:** [#5550](https://github.com/agentscope-ai/QwenPaw/issues/5550) - **Remote SSH plugin install loop** and zombie backend processes (macOS). No fix PR yet.
- **Medium:** [#5328](https://github.com/agentscope-ai/QwenPaw/issues/5328) - **Agent thinking hangs** when using DeepSeek models; requires manual "stop" and "continue". A persistent issue with no confirmed fix.

### 6. Feature Requests & Roadmap Signals
- **Aggregated Replies (Likely next patch):** PR [#5577](https://github.com/agentscope-ai/QwenPaw/pull/5577) directly addresses the high-demand issue [#5563](https://github.com/agentscope-ai/QwenPaw/issues/5563). This is almost certainly landing in the next point release.
- **Model Auto-Fallback (Feature Request):** [#5572](https://github.com/agentscope-ai/QwenPaw/issues/5572) requests automatic switching to a backup model upon quota/timeout. Given the beta release and model provider bugs, this is a likely candidate for v2.0.0 stable.
- **Streaming File Write (Feature Request):** [#4865](https://github.com/agentscope-ai/QwenPaw/issues/4865) asks for live-streaming display when an agent writes large files. This is a key UX gap that is likely to be tackled for 2.0.
- **DingTalk @Mention Support (Feature Request):** [#5564](https://github.com/agentscope-ai/QwenPaw/issues/5564) requests `@mention` support in DingTalk for multi-agent coordination. Signals enterprise adoption.

### 7. User Feedback Summary
- **Satisfaction:** Users appreciate the automation potential (cron tasks, channels). The community is proactively creating tooling (e.g., the GitHub issue skill [#5567](https://github.com/agentscope-ai/QwenPaw/issues/5567)).
- **Dissatisfaction/ Pain Points:**
    - **"Message Spam"**: Multi-step agents flood chat with individual messages ([#5563](https://github.com/agentscope-ai/QwenPaw/issues/5563)).
    - **"Silent Failures"**: Cron jobs fail silently, and background scripts cannot send notifications ([#5566](https://github.com/agentscope-ai/QwenPaw/issues/5566)).
    - **"Data Loss"**: Conversations are fragile and lost on crash/reboot ([#5579](https://github.com/agentscope-ai/QwenPaw/issues/5579)).
    - **"Model Fragility"**: Agents hang or error out with popular third-party models (DeepSeek) ([#5328](https://github.com/agentscope-ai/QwenPaw/issues/5328), [#5573](https://github.com/agentscope-ai/QwenPaw/issues/5573)).
    - **"Integration Gaps"**: Channel delivery is unreliable (Feishu long messages, DingTalk @mentions missing).

### 8. Backlog Watch
- [#4865](https://github.com/agentscope-ai/QwenPaw/issues/4865) **([Open] since 2026-06-01):** The "non-streaming file write" issue has 2 👍 and no maintainer response. This is a critical UX issue for technical users generating code/HTML.
- [#5328](https://github.com/agentscope-ai/QwenPaw/issues/5328) **([Open] since 2026-06-19):** The "DeepSeek thinking hang" is a persistent problem with multiple user reports. While the community is active, this bug remains unresolved, signaling a possible deep issue with the model provider integration layer.
- **PRs needing review:** The large first-time contributor PRs, such as [#4622](https://github.com/agentscope-ai/QwenPaw/pull/4622) (DataPaw plugin, 51 comments) and [#5321](https://github.com/agentscope-ai/QwenPaw/pull/5321) (Scroll context manager), are still under review after weeks. These represent significant new features and require maintainer attention to avoid community burnout.

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

No activity in the last 24 hours.

</details>

<details>
<summary><strong>ZeroClaw</strong> — <a href="https://github.com/zeroclaw-labs/zeroclaw">zeroclaw-labs/zeroclaw</a></summary>

# ZeroClaw Project Digest — 2026-06-27

## Today's Overview
ZeroClaw remains in an intense development phase, with 50 issues and 50 PRs updated within the last 24 hours. The project is actively executing against the v0.8.3 milestone, with significant work progressing on WASM plugin infrastructure, supply-chain security, and channel integrations. Open issue count (37) substantially outpaces closed items (13), indicating a high volume of active work rather than a maintenance lull. Three major RFC-driven initiatives — Wasm-first plugin runtime, supply-chain signing, and goal-mode autonomous sessions — are in accepted status and receiving implementation attention. The absence of new releases suggests the team is consolidating changes for a future cut rather than shipping incrementally.

---

## Releases
No new releases were published in the last 24 hours. The last release was v0.8.2, with the v0.8.3 milestone actively tracked in issue [#7320](https://github.com/zeroclaw-labs/zeroclaw/issues/7320) and its child trackers.

---

## Project Progress
Six PRs were merged or closed today:

- **#8381** — `fix(tools): drop unwrap from hardware_memory_read chip lookup` (closed/merged) — Safety hardening in hardware memory tool
- **#8330** — `fix(zerocode): render only the viewport in long sessions` (closed/merged) — Performance fix for long conversation rendering in the TUI
- **#8378** through **#8371** (8 issues closed) — All labeled `invalid`, these were user-story sub-tasks (`[002-dms-gst-extraction]`) for a DMS GST extraction feature, systematically closed after completion

Active PRs showing significant forward movement:
- **#8389** (new) — `feat(channels): add passive WhatsApp group context` — Implements feature requested in #8379
- **#8384** (new) — `feat(inkbox): add a native Inkbox channel` — New channel integration (email/SMS/voice/iMessage)
- **#8382** (new) — `feat(memory): persist embedding identity and auto-migrate vectors on model change` — Solves a long-standing memory model-mismatch problem
- **#8368** (new, DO NOT MERGE) — `feat(plugins): wasmtime component-model host` — Major plugin runtime rewrite replacing extism
- **#8277** (new) — `ci(workflows): add SLSA provenance attestation to release pipeline` — Security supply-chain hardening
- **#8355** — `fix(channels): fire message_sent hooks after delivery` — Proper hook integration for channel messages
- **#8343** and **#8344** — CI release workflow fixes for feature registry alignment and tag deployment

---

## Community Hot Topics

### Most Active Issues

1. **#6808** (11 comments) — `RFC: Work Lanes, Board Automation, and Label Cleanup` — Governance RFC for routing work. Now in rollout phase. Cross-cutting concern affecting how 50+ daily issues get triaged.

2. **#8177** (10 comments) — `RFC: Supply chain signing - hardware PGP, hermetic builds, and SLSA provenance` — Security-focused RFC with high risk. PR [#8277](https://github.com/zeroclaw-labs/zeroclaw/pull/8277) already implements the SLSA attestation phase. Active implementation alongside RFC discussion.

3. **#5844** (7 comments, CLOSED) — `[Bug]: Too much emphasis on memory` — Closed today after resolution. Addressed a pain point where system prompts prioritized stored memories over current conversation context, particularly affecting cron jobs.

4. **#5808** (6 comments) — `[Bug]: Default 32k context budget is exceeded by system prompt + tool definitions on iteration 1` — S1 severity bug. PR [#7440](https://github.com/zeroclaw-labs/zeroclaw/pull/7440) exists as a fix (updated today), though it notes that deeper architecture changes may be needed beyond the surface fix.

5. **#4879** (4 comments, CLOSED, 2 👍) — `[Bug]: Gemini CLI OAuth is simply not working` — Closed today. Previously a high-impact S1 bug that blocked Gemini users entirely.

6. **#8303** (2 comments, 1 👍) — `RFC: Goal mode for bounded autonomous session work` — New RFC proposing a first-class durable session mode. Received one of the few positive reactions today, suggesting user interest in this capability.

### Most Active PRs
Several PRs have undefined comment counts but show sustained activity:
- **#8389**, **#8368**, **#8355**, **#8277**, **#8384** all received updates today from maintainers.

### Underlying Needs
The high-comment issues reveal three community priorities:
- **Security governance**: Supply-chain signing (#8177) and work-organization RFCs (#6808) show the community wants professional-grade operational security
- **Memory/context management**: Two of the top bugs (#5844, #5808) relate to how the agent manages context and memory, indicating this is a core UX pain point
- **Channel reliability**: OAuth issues (#4879), prompt caching with Telegram (#6360), and Discord threads (#7849) show users are actively deploying ZeroClaw across multiple platforms and hitting integration friction

---

## Bugs & Stability

### Critical / S1 Severity (Workflow Blocked)
- **#8434** (reported today? actually #5808) — `Default 32k context budget exceeded by system prompt` — Active, fix PR [#7440](https://github.com/zeroclaw-labs/zeroclaw/pull/7440) exists. Perpetual preemptive trim renders the agent non-functional with default settings.

### High Severity (S2 - Degraded Behavior / Security No-Op)
- **#7733** — `mcp_bundles parsed but never enforced at runtime` — Security isolation field is a silent no-op. Per-agent MCP scoping doesn't work despite clean parsing.
- **#8366** — `Heartbeat engine reads HEARTBEAT.md from data_dir instead of agent workspace` — Path inconsistency causes heartbeat tasks to be missed.
- **#7800** — `Code help/keybindings misleading or unreachable on macOS` — UX bug affecting ZeroCode TUI users.
- **#6360** — `Prompt caching does not work with telegram` — Performance degradation on Telegram channel.
- **#8047** (CLOSED) — `ReadSkillTool looks in data_dir but skills live in agent workspace` — Fixed; similar data_dir vs workspace path confusion as #8366.

### Today's New Bug Reports
- **#8379** — `Opt-in passive group context for WhatsApp Web group chats` — Feature request but highlights current behavior gap where unaddressed group messages are dropped.

### Notable Fixes In Progress
- PR [#7440](https://github.com/zeroclaw-labs/zeroclaw/pull/7440) fixes context budget overflow (#5808)
- PR [#6619](https://github.com/zeroclaw-labs/zeroclaw/pull/6619) fixes shell tool refusal at autonomy level "full" (#6434)
- PR [#8350](https://github.com/zeroclaw-labs/zeroclaw/pull/8350) fixes unbounded Regex allocation in web-search tool

---

## Feature Requests & Roadmap Signals

### Likely for v0.8.3 or Next Release
- **Goal mode for autonomous sessions** (#8303, accepted RFC) — First-class durable session pursuing a single objective until completion or budget exhaustion. High user interest (1 👍 on a 2-comment issue). Likely tracking for v0.8.3 or v0.9.0.
- **Wasm-first plugin runtime** (#8135, accepted RFC) — Removing Node.js dependency, making Wasm the default plugin runtime with signed distribution. PR [#8368](https://github.com/zeroclaw-labs/zeroclaw/pull/8368) exists (DO NOT MERGE status, but active).
- **OpenRouter model fallbacks** (#8138, in-progress) — Support for OpenRouter's `models` array for automatic failover. Small scope, likely to land.
- **Discord mention-triggered thread mode** (#7849, accepted) — Creates threads when bot is mentioned to avoid channel clutter.
- **Passive WhatsApp group context** (#8379, open today) — Companion PR [#8389](https://github.com/zeroclaw-labs/zeroclaw/pull/8389) already submitted. Fast track to implementation.
- **Inkbox native channel** (PR #8384, submitted today) — New email/SMS/voice/iMessage channel. Complete with Quickstart onboarding.

### Long-Term Signals (v0.9.0)
- **Supply-chain signing** (#8177, #8058) — Hardware-backed PGP, SLSA provenance, SBOM publication. High complexity, tracked under [#7432](https://github.com/zeroclaw-labs/zeroclaw/issues/7432) (v0.9.0 auth/security tracker).
- **In-app upgrade from web dashboard** (PR #8173, size:L) — Sidebar version tag becomes upgrade affordance. High risk, large scope.
- **ACP multiple-choice elicitation** (PR #8338, size:XL) — Multi-choice forms for ACP channel and ZeroCode. Draft spec, no shipping editor support yet.

---

## User Feedback Summary

### Pain Points
1. **Memory over-prioritization** (#5844, CLOSED) — System prompts weighting memories above current context, especially in cron jobs. User `databillm` reported "gives too much value/trust to the memories rather than what is being said." Fix was applied and issue closed today.
2. **Context budget unusability** (#5808) — Default 32k context is immediately exhausted by system prompt + tool definitions. User `JordanTheJet` reported the agent "endlessly re-ran the same tool calls" due to perpetual trim. Wait-and-see if PR #7440 fully resolves or if config defaults need changing.
3. **Gemini OAuth failure** (#4879, CLOSED) — "Simply not working" (user `nrpx`). Rate-limited error right after successful auth. Closed today after fix.
4. **Shell tool refusal at full autonomy** (#6434, CLOSED) — With maximally permissive config, agent returned simulated refusals without emitting tool calls. User `sam74S` reported "no `tool_dispatch` ever reaches the runtime." PR #6619 addresses this.
5. **Silent security no-op** (#7733) — `mcp_bundles` config parses correctly but is never enforced. User `metalmon` reported this as a "silent no-op of a security-relevant isolation field." No fix PR yet.

### Satisfaction Indicators
- Active contributor engagement: 50 PRs and 50 issues updated in 24 hours with diverse author list (rifuki, Super-Cabbage, ConYel, Audacity88, Nillth, dimavrem22, tidux, etc.)
- Multiple contributors submitting safety/quality improvements (unwrap-to-expect conversions, Regex caching, error message improvements) — signals a maturing codebase culture
- Fast turnaround on some issues: WhatsApp group context requested (#8379) had companion PR submitted same day (#8389)
- CLOSED rate of 13/50 issues today suggests active triage and resolution

---

## Backlog Watch

### Issues Needing Maintainer Attention

1. **#7733** — `mcp_bundles silently not enforced at runtime` — Security-relevant bug (risk:high) with no fix PR. Last updated 2026-06-26 (11 days since filing). Severity S2 but security impact makes it urgent. No maintainer assignment visible.

2. **#6619** — `fix(runtime/agent): authorize shell explicitly at autonomy.level=full` — PR is stale candidate, labeled `needs-author-action`. Submitted 2026-05-13, still open after 6 weeks with no author response. Fixes a critical S1 bug (#6434). May need maintainer to adopt or reach out to contributor `yijunyu`.

3. **#8350** — `perf(web-search): cache strip_tags regex in a LazyLock static` — Labeled `needs-author-action`. Small low-risk fix that optimizes a per-call Regex compilation. Contributor `Super-Cabbage` may need guidance to complete.

### Long-Open Issues with High Impact
- **#5808** (context budget overflow) — 72 days open. S1 severity. Has fix PR but discussion indicates deeper issue than surface fix.
- **#6360** (Telegram prompt caching) — 54 days open. Moderate severity but affects user experience on a popular channel.
- **#6642** (capture full prompt/completion on llm.call spans) — 45 days open. Relies on contributor `alexandme` to upstream downstream implementation. If not completed soon, observability features remain incomplete.

</details>

---
*This digest is auto-generated by [agents-radar](https://github.com/Lux0206/agents-radar).*