# AI CLI Tools Community Digest 2026-06-27

> Generated: 2026-06-27 08:27 UTC | Tools covered: 9

- [Claude Code](https://github.com/anthropics/claude-code)
- [OpenAI Codex](https://github.com/openai/codex)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)
- [GitHub Copilot CLI](https://github.com/github/copilot-cli)
- [Kimi Code CLI](https://github.com/MoonshotAI/kimi-cli)
- [OpenCode](https://github.com/anomalyco/opencode)
- [Pi](https://github.com/badlogic/pi-mono)
- [Qwen Code](https://github.com/QwenLM/qwen-code)
- [DeepSeek TUI](https://github.com/Hmbown/DeepSeek-TUI)
- [Claude Code Skills](https://github.com/anthropics/skills)

---

## Cross-Tool Comparison

# Cross-Tool Comparison Report: AI CLI Developer Tools
**Date:** 2026-06-27

---

## 1. Ecosystem Overview

The AI CLI developer tools ecosystem continues to mature rapidly, with **seven major tools** now actively competing for developer mindshare. Today's data reveals a community deeply engaged but increasingly frustrated with core reliability issues—particularly around **rate limiting, session cost transparency, and cross-platform stability**. Claude Code remains the most-commented project (787 comments on a single billing issue), while Codex and Gemini CLI show strong engineering velocity with 10+ active PRs each. A clear stratification is emerging: Claude Code and Codex lead in community size and feature depth, while newer entrants like Pi and CodeWhale are iterating aggressively on TUI/UX and provider extensibility. The most concerning trend is the prevalence of **regression-heavy releases**, with multiple tools reporting critical bugs introduced by recent patches.

---

## 2. Activity Comparison

| Tool | Hot Issues | New Issues (24h) | Active PRs | Release Status | Community Engagement |
|------|-----------|-----------------|------------|----------------|---------------------|
| **Claude Code** | 10 (top: #38335, 787 comments) | ~3-5 | 2 | ✅ v2.1.195 released | Very high (468 👍 on top issue) |
| **Codex CLI** | 10 (top: #28879, 328 👍) | ~5-8 | 10 | ✅ rust-v0.142.3, alpha | High (179 comments on rate-limit) |
| **Gemini CLI** | 10 (top: #21409, 8 👍) | ~3-5 | 10 | ❌ Nightly failed | Moderate (lower upvote counts) |
| **GitHub Copilot CLI** | 10 (top: #2082, 11 👍) | ~4-6 | 1 | ✅ v1.0.66-1 | Moderate (smaller community) |
| **Kimi Code** | 3 (active) | ~2 | 0 | ❌ No releases | Low (3 issues total, 0 PRs) |
| **OpenCode** | 10 (top: #28846, 82 👍) | ~5-7 | 10 | ❌ No releases | Moderate-High (85 comments on pricing) |
| **Pi** | 10 (top: #5825, 33 comments) | **20+ filed today** | 5 | ❌ No releases | Moderate (burst of activity) |
| **CodeWhale** | 10 (top: #3568, 6 comments) | ~2-3 | 10 | ❌ No releases | Low-Moderate (smaller but active) |
| **Qwen Code** | 10 (top: #5873, 5 comments) | ~5-7 | **10+ (50 total)** | ✅ v0.19.2 nightly | Moderate (strong CI velocity) |

**Key observations:**
- **Claude Code** and **Codex** dominate community engagement volume
- **Qwen Code** has the highest PR velocity (50+ open PRs)
- **Kimi Code** shows the least activity—potential abandonment signal
- **Pi** had the highest single-day issue burst (20+)
- **Gemini CLI**'s nightly pipeline failure is a notable infrastructure concern

---

## 3. Shared Feature Directions

### 3.1 Cost Transparency & Limits (ALL tools)
| Tool | Specific Demand |
|------|----------------|
| **Claude Code** | #38335: Session limits draining in minutes (787 comments) |
| **Codex CLI** | #28879: 10-20x rate-limit cost regression on GPT-5.5 (328 👍) |
| **Gemini CLI** | #24246: 400 error with >128 tools (indirect cost of tool overload) |
| **OpenCode** | #28846: Adjust limits after DeepSeek 75% price cut (82 👍) |
| **Qwen Code** | #5819: Auto-upgrade overrides to more expensive model |
| **Pi** | (Implicit in provider error handling discussions) |

**Common demand:** Soft limits, pre-execution cost estimates, per-agent budget caps, proactive warnings before credit exhaustion.

### 3.2 MCP Ecosystem Standardization (Claude Code, Codex, Gemini CLI, Copilot CLI, OpenCode, Qwen Code, CodeWhale)
| Tool | Specific MCP Issue |
|------|-------------------|
| **Claude Code** | #19054: VS Code ignores MCP servers; #48275: State sync failure |
| **Gemini CLI** | #24246: >128 tools causes 400 error |
| **Codex CLI** | Bundled plugin availability (Windows EFS encryption) |
| **Copilot CLI** | #3958: Windows MCP .bat/.cmd args regression |
| **OpenCode** | #28567: Full MCP client capabilities needed |
| **Qwen Code** | #5897: Ajv schema warnings for MCP tools |
| **CodeWhale** | #3575: Moraine MCP recall tools (adopting MCP as memory backend) |

**Common demand:** OAuth flows, tool elicitation, session/fork support, consistent cross-IDE behavior, scalable tool selection (>128 tools).

### 3.3 Terminal/UI Stability (ALL tools)
| Tool | Specific UI Issue |
|------|------------------|
| **Claude Code** | #11002: Screen-reader mode; #70622: Disable clickable prompts |
| **Codex CLI** | #5538: Input message disappears during response |
| **Gemini CLI** | #21409: Generalist agent hangs indefinitely |
| **Copilot CLI** | #2082: Clipboard broken on Linux; #3959: Ghost characters |
| **Kimi Code** | #2477: Double Enter + feedback loss on Linux |
| **OpenCode** | #33887: Black TUI screen on WSL |
| **Pi** | #5825: Streaming scroll jank; #6050: Full redraw clears scrollback |
| **CodeWhale** | #3657: Editor hard-freezes TUI |
| **Qwen Code** | #5083: Zombie processes freeze TUI on Linux |

**Common demand:** Cross-platform TTY handling, alt-screen opt-out, stable streaming rendering, no forced scrolling.

### 3.4 Accessibility & Keyboard-First Workflows (Claude Code, Copilot CLI, Codex)
- **Claude Code**: #11002 (screen-reader mode), #69998 (focus management), #70622 (keyboard-only dialogs)
- **Copilot CLI**: #3672 (custom keybindings), #2082 (clipboard shortcuts)
- **Codex CLI**: (Implicit in cross-platform compatibility demands)

### 3.5 Context/Session Integrity (Claude Code, Codex, Copilot CLI, Gemini CLI, Qwen Code, OpenCode)
| Tool | Specific Issue |
|------|---------------|
| **Claude Code** | #67283: Fabricated tool results; #71715: /context burns context |
| **Codex CLI** | #27453: Session loss after updates |
| **Copilot CLI** | #3945: Memory leaking across repos; #3944: Export verbosity |
| **Gemini CLI** | #26525: Secret leakage before redaction in Auto Memory |
| **Qwen Code** | #5920: History loss after session resume |
| **OpenCode** | #34190: Plan mode bypass via shell commands |

**Common demand:** Deterministic audit trails, context isolation per project, session-export compression, memory redaction guarantees.

### 3.6 Agent & Subagent Reliability (Claude Code, Gemini CLI, Copilot CLI, CodeWhale, OpenCode)
| Tool | Specific Issue |
|------|---------------|
| **Gemini CLI** | #22323: Subagent false success reports; #21409: Hangs |
| **Copilot CLI** | #3944: Inlined subagent transcripts |
| **CodeWhale** | #3568: Plan/Agent mode confusion |
| **OpenCode** | #34190: Plan mode bypass via `gh` |
| **Claude Code** | #60705: Stop-hook reasoning pathologies |

**Common demand:** Tool-usage visibility, deterministic mode enforcement, subagent trajectory debugging, progress reporting during multi-step tasks.

---

## 4. Differentiation Analysis

### 4.1 Feature Focus

| Tool | Primary Differentiator | Target User |
|------|----------------------|------------|
| **Claude Code** | Rich TUI, hook/plugin ecosystem, MCP integration depth | Professional developers, safety-conscious teams |
| **Codex CLI** | GPT-5.5 optimization, Guardian safety reviews, Rust performance | Enterprise/security-sensitive teams |
| **Gemini CLI** | Google ecosystem integration, sub-agent orchestration, AST-aware code intelligence | Google Cloud/Android developers |
| **Copilot CLI** | GitHub integration, `/chronicle` skills system, desktop notifications | GitHub-centric dev teams |
| **OpenCode** | Multi-provider support (GLM, DeepSeek), session-to-session messaging, WSL stability | Cross-platform, cost-conscious developers |
| **Pi** | Extension system, orchestrator daemon, provider flexibility | Power users, extensibility-minded developers |
| **CodeWhale** | Memory backend (Moraine), multi-platform bridges (Telegram/WeCom), CJK/Unicode support | East Asian, multi-platform teams |
| **Qwen Code** | Qwen-based models, computer-use agent (CUA), cron/loop automation | Automation-heavy workflows, Qwen ecosystem |
| **Kimi Code** | Minimalist TUI, plan/agent modes | Lightweight usage (potentially stalled) |

### 4.2 Technical Approach

- **Claude Code**: Python/TypeScript hybrid, rich plugin system, session-scoped hooks
- **Codex CLI**: Rust-based, Guardian review system, deterministic safety modes
- **Gemini CLI**: Go-based, sub-agent orchestration model, eval-driven development
- **Copilot CLI**: TypeScript/Node.js, GitHub Copilot integration, skill marketplace
- **OpenCode**: Go-based, MCP-first architecture, multiple LLM backends
- **Pi**: Java/TypeScript, extension runtime, modular provider registry
- **CodeWhale**: Rust-based, Moraine memory backend, CJK optimization
- **Qwen Code**: Rust-based, Qwen model family focus, computer-use agent
- **Kimi Code**: Unknown stack, minimal community presence

### 4.3 Community Demographics

| Tool | Primary OS | Language Preference | Team Size |
|------|-----------|-------------------|-----------|
| **Claude Code** | macOS/Linux | TypeScript, Python | Individual to small team |
| **Codex CLI** | macOS (Rust) | Rust, Python | Enterprise |
| **Gemini CLI** | Linux (Go) | Go | Google-ecosystem |
| **Copilot CLI** | Cross-platform | TypeScript | GitHub-centric |
| **OpenCode** | Linux/Windows (Go) | Go, Python | Cost-sensitive |
| **Pi** | Cross-platform | Java, TypeScript | Extensibility enthusiasts |
| **CodeWhale** | Linux/Cross-platform | Rust | East Asian markets |
| **Qwen Code** | Cross-platform (Rust) | Rust, Python | Automation enthusiasts |

---

## 5. Community Momentum & Maturity

### 5.1 Most Active Communities
| Rank | Tool | Momentum Indicators |
|------|------|-------------------|
| 1 | **Claude Code** | 787 comments on single issue, 468 👍, daily engagement after 3 months |
| 2 | **Codex CLI** | 328 👍 on rate-limit issue, 10 PRs/day, multiple alpha releases |
| 3 | **Qwen Code** | 50 open PRs, strong CI pipeline, nightly releases |
| 4 | **OpenCode** | 82 👍 on pricing issue, 10 active PRs, steady MCP work |
| 5 | **Pi** | 20+ issues filed in 24h, 5 active PRs, orchestrator feature |

### 5.2 Rapid Iterators
| Tool | Iteration Rate | Quality Signal |
|------|---------------|---------------|
| **Qwen Code** | ⭐⭐⭐⭐⭐ Daily nightlies, 50 PRs | Regression risk (multiple Windows bugs) |
| **Codex CLI** | ⭐⭐⭐⭐ Alpha chain, 10 PRs/day | Rate-limit regression undermines confidence |
| **CodeWhale** | ⭐⭐⭐⭐ 10 PRs/day, steady CI | Documentation drift signals growing pains |
| **Gemini CLI** | ⭐⭐⭐ Nightly failure, but 10 PRs | Pipeline reliability concerns |
| **OpenCode** | ⭐⭐⭐ 10 PRs, but no releases | Need stable releases to match velocity |

### 5.3 Stalling Tools
| Tool | Signals |
|------|--------|
| **Kimi Code** | 0 PRs, 3 issues, no releases, low engagement |
| **Copilot CLI** | 1 PR, 10 issues, community size stable but not growing |

### 5.4 Maturity Assessment
- **Claude Code**: Most mature community, largest feature set, but growing pains with scale (session limits, safety harness)
- **Codex CLI**: Strong engineering practices (Rust, Guardian), but rate-limit regression shows infrastructure fragility
- **Gemini CLI**: Good engineering discipline (evals, PR reviews), but low community engagement means slower issue resolution
- **Qwen Code**: Fastest iteration, but Windows quality lags (multiple platform-specific bugs)
- **CodeWhale**: Strong architectural vision (Moraine), but documentation and stability need improvement

---

## 6. Trend Signals

### 6.1 The Cost Crisis
**Signal:** Every major tool has unresolved billing/rate-limit issues. Claude Code's #38335 (787 comments, 3 months unresolved) and Codex's #28879 (328 👍, 20x cost regression) indicate **infrastructure not scaling with user adoption**. Developers are willing to pay for AI CLI tools but demand predictable costs.

**Implication:** Tools that solve cost transparency (per-agent budgets, pre-execution estimates, soft limits) will gain competitive advantage.

### 6.2 Cross-Platform Fragmentation
**Signal:** Windows-specific bugs dominate: Copilot CLI clipboard (#3949), Qwen Code PowerShell zombies (#5873), Codex plugin EFS encryption (#25220), OpenCode WSL black screen (#33887), Pi path corruption (#6104).

**Implication:** Linux-first development cultures are leaving Windows users behind. This is a market opportunity for tools that invest in Windows quality.

### 6.3 The Safety/Usability Tension
**Signal:** Claude Code harness false positives (#71104), Codex Guardian disconnects (#27537), Gemini Auto Memory leakage (#26525), OpenCode Plan mode bypass (#34190).

**Implication:** Security teams want guardrails; developers want frictionless workflows. The tools that achieve **deterministic safety** (allow/deny lists, not model-based review) will satisfy both constituencies.

### 6.4 MCP as Infrastructure
**Signal:** Every major tool is investing in MCP (Model Context Protocol) support. MCP is becoming the **universal plugin standard** for AI CLI tools. Issues around OAuth, tool selection, and cross-IDE parity are common.

**Implication:** MCP compliance is table stakes. Tools that offer robust MCP management (scoping, authentication, state sync) will differentiate.

### 6.5 Agent Autonomy vs. User Control
**Signal:** Gemini agent hangs (#21409), Copilot memory leaks (#3945), CodeWhale Plan/Agent mode confusion (#3568), Qwen cron tasks firing silently (#5823).

**Implication:** Users want **supervised autonomy**—agents that can act independently but provide visibility, pause/resume, and clear audit trails. The "agent as black box" approach is failing.

### 6.6 The "Pause" Gap
**Signal:** Multiple issues request mid-session correction capability: Copilot CLI #1928 ("Allow to pause copilot work"), Pi #5825 (scroll control during streaming), Codex #5538 (input disappears).

**Implication:** Current tools operate in "fire and forget" mode for streaming. Users need **interruptible, steerable agents** that accept mid-stream corrections.

### 6.7 Memory as Competitive Differentiator
**Signal:** CodeWhale investing in Moraine (lossless session store), Gemini Auto Memory issues (#26525), Claude Code context contamination (#67283), Copilot memory leakage (#3945).

**Implication:** Memory/context management is becoming a core product feature. Tools with deterministic, auditable, project-scoped memory will win trust.

### 6.8 Developer Experience Regression
**Signal:** Almost every tool's recent release introduced regressions: Claude Code v2.1.195 (partial fix), Copilot CLI v1.0.66 (.bat args broken), Qwen Code v0.19.2 (model override), Codex v0.142.3 (macOS churn remains).

**Implication:** The ecosystem is moving too fast. **Regression-focused testing** and **staged rollouts** are becoming critical quality practices.

---

## Summary Recommendations for Decision-Makers

| Use Case | Recommended Tool | Rationale |
|----------|-----------------|-----------|
| **Cost-sensitive individual devs** | OpenCode | Multi-provider, pricing-responsive community |
| **Enterprise security teams** | Codex CLI | Guardian reviews, Rust performance, deterministic safety |
| **Google Cloud/Android devs** | Gemini CLI | AST-aware code intelligence, Google ecosystem |
| **GitHub-centric teams** | Copilot CLI | GitHub integration, skills system |
| **Automation-heavy workflows** | Qwen Code | Cron/loop, computer-use, nightly releases |
| **Extensibility/power users** | Pi | Extension system, orchestrator, provider flexibility |
| **East Asian/CJK users** | CodeWhale | Unicode optimization, WeCom/Telegram bridges |
| **Most stable/mature** | Claude Code | Largest community, richest feature set, but cost issues |
| **Avoid (for now)** | Kimi Code | No activity, potential abandonment |

**Bottom line:** The AI CLI ecosystem is in a **growth-at-all-costs phase**, with strong innovation but significant reliability concerns. Teams should budget for **regression testing overhead** when adopting any tool, and prioritize tools with **deterministic safety models** and **cost transparency features** for production use.

---

## Per-Tool Reports

<details>
<summary><strong>Claude Code</strong> — <a href="https://github.com/anthropics/claude-code">anthropics/claude-code</a></summary>

## Claude Code Skills Highlights

> Source: [anthropics/skills](https://github.com/anthropics/skills)

# Claude Code Skills Community Highlights Report
**Data as of 2026-06-27 | Source: github.com/anthropics/skills**

---

## 1. Top Skills Ranking

The following Pull Requests have attracted the most community discussion and represent the most-watched Skill submissions:

1. **🔧 Fix: `run_eval.py` Always Reports 0% Recall** (PR [#1298](https://github.com/anthropics/skills/pull/1298))
   - **Author:** MartinCajiao | **Status:** Open
   - **Functionality:** Repairs the skill-creator evaluation pipeline so `run_eval.py`, `run_loop.py`, and `improve_description.py` correctly detect skill triggers. The bug caused every skill description to score 0% recall, making the optimization loop optimize against noise rather than real signal.
   - **Discussion Highlights:** Addresses 10+ independent reproductions of Issue #556. Fixes Windows stream reading, trigger detection logic, and parallel worker behavior.

2. **📄 Add `document-typography` Skill** (PR [#514](https://github.com/anthropics/skills/pull/514))
   - **Author:** PGTBoos | **Status:** Open
   - **Functionality:** Prevents orphan word wrap (1–6 words alone on a new line), widow paragraphs (headers stranded at page bottom), and numbering misalignment in AI-generated documents.
   - **Discussion Highlights:** Community noted this addresses a universal pain point—typographic defects affect every Claude-generated document. High interest in merging.

3. **📝 Add ODT Skill — OpenDocument Creation & Template Filling** (PR [#486](https://github.com/anthropics/skills/pull/486))
   - **Author:** GitHubNewbie0 | **Status:** Open
   - **Functionality:** Creates, fills, reads, and converts OpenDocument Format files (.odt, .ods). Triggers on "ODT", "ODS", "ODF", or "OpenDocument" mentions. Includes template filling and ODT-to-HTML conversion.
   - **Discussion Highlights:** Strong demand from LibreOffice users and open-source document workflows. Active discussion on scope boundaries.

4. **🎨 Improve `frontend-design` Skill Clarity** (PR [#210](https://github.com/anthropics/skills/pull/210))
   - **Author:** justinwetch | **Status:** Open
   - **Functionality:** Revises the frontend-design skill for better actionability and internal coherence, ensuring each instruction is executable within a single conversation.
   - **Discussion Highlights:** Community praised the focus on "steerable" instructions. Driven by frustration with verbose, non-actionable skill descriptions.

5. **🔍 Add `skill-quality-analyzer` & `skill-security-analyzer`** (PR [#83](https://github.com/anthropics/skills/pull/83))
   - **Author:** eovidiu | **Status:** Open
   - **Functionality:** Meta-skills for evaluating other Skills across five quality dimensions (Structure, Documentation, Code quality, Clarity, Coverage) and security posture.
   - **Discussion Highlights:** First meta-skills proposed for the marketplace. Significant interest in tooling to validate Skill quality before distribution.

6. **🔧 Fix DOCX Tracked Change ID Collision** (PR [#541](https://github.com/anthropics/skills/pull/541))
   - **Author:** Lubrsy706 | **Status:** Open
   - **Functionality:** Fixes document corruption when DOCX skill adds tracked changes to documents with existing bookmarks by avoiding hardcoded OOXML ID values that collide.
   - **Discussion Highlights:** Technical depth appreciated. Highlights complexity of OOXML manipulation through Skills.

7. **🧪 Add `testing-patterns` Skill** (PR [#723](https://github.com/anthropics/skills/pull/723))
   - **Author:** 4444J99 | **Status:** Open
   - **Functionality:** Comprehensive skill covering the full testing stack: Testing Trophy philosophy, AAA pattern, React component testing, mocking strategies, and E2E testing with Playwright.
   - **Discussion Highlights:** Broad interest from developers. Covers both what to test and what *not* to test—community found this distinction valuable.

8. **📊 Add `codebase-inventory-audit` Skill** (PR [#147](https://github.com/anthropics/skills/pull/147))
   - **Author:** p19dixon | **Status:** Open
   - **Functionality:** Systematic 10-step workflow for identifying orphaned code, unused files, documentation gaps, and infrastructure bloat. Produces a CODEBASE-STATUS.md artifact.
   - **Discussion Highlights:** Strong demand from teams maintaining legacy codebases. Seen as complementary to code-review workflows.

---

## 2. Community Demand Trends

Analysis of the most-commented Issues reveals four concentrated demand directions:

### 🔐 **Security & Trust Boundaries** (Issue [#492](https://github.com/anthropics/skills/issues/492), 22 comments)
The hottest topic. Community members discovered that community-contributed Skills are distributed under the `anthropic/` namespace, enabling trust-boundary abuse. Users may grant elevated permissions to Skills they believe are official Anthropic releases. **Community demand:** Namespace isolation and trust verification mechanisms for Skills.

### 🏢 **Enterprise & Org Sharing** (Issue [#228](https://github.com/anthropics/skills/issues/228), 14 comments)
Users want org-wide Skill sharing without manual `.skill` file distribution via Slack/Teams. **Community demand:** Shared Skill libraries, direct sharing links, or org-level installation workflows.

### 🛠️ **Skill-Creator Reliability** (Issues [#556](https://github.com/anthropics/skills/issues/556), [#1169](https://github.com/anthropics/skills/issues/1169), [#1061](https://github.com/anthropics/skills/issues/1061); 18+ comments combined)
The evaluation pipeline (`run_eval.py`, `run_loop.py`) consistently reports 0% trigger rates. Multiple community members independently reproduced the bug. **Community demand:** Robust evaluation tooling that actually measures recall/precision correctly, especially on Windows (subprocess encoding, `PATHEXT`, pipe handling).

### 📦 **Deduplication & Package Management** (Issue [#189](https://github.com/anthropics/skills/issues/189), 6 comments)
Installing both `document-skills` and `example-skills` plugins results in duplicate Skills cluttering the context window. **Community demand:** Clear separation of plugin concerns or a deduplication mechanism.

### ➕ **Emerging Skill Proposals**
- **Agent governance** (Issue [#412](https://github.com/anthropics/skills/issues/412)) — safety patterns, policy enforcement, audit trails for agentic systems
- **Compact memory** (Issue [#1329](https://github.com/anthropics/skills/issues/1329)) — symbolic notation for compact agent state to conserve context window
- **MCP exposure** (Issue [#16](https://github.com/anthropics/skills/issues/16)) — expose Skills as MCP tools for programmatic API access

---

## 3. High-Potential Pending Skills

These PRs have active discussion, are not yet merged, and appear likely to land soon:

| Skill | PR | Key Reason for Momentum |
|---|---|---|
| **document-typography** | [#514](https://github.com/anthropics/skills/pull/514) | Addresses universal document quality issue; clear, narrow scope |
| **ODT (OpenDocument)** | [#486](https://github.com/anthropics/skills/pull/486) | Strong enterprise/LibreOffice demand fills a format gap |
| **testing-patterns** | [#723](https://github.com/anthropics/skills/pull/723) | Broad developer appeal; comprehensive but modular |
| **skill-quality-analyzer** | [#83](https://github.com/anthropics/skills/pull/83) | Meta-skill enabling quality gate for all other Skills |
| **codebase-inventory-audit** | [#147](https://github.com/anthropics/skills/pull/147) | Directly addresses codebase maintenance pain |
| **SAP-RPT-1-OSS predictor** | [#181](https://github.com/anthropics/skills/pull/181) | First enterprise-vertical predictive analytics Skill |
| **shodh-memory** | [#154](https://github.com/anthropics/skills/pull/154) | Persistent context across conversations; novel capability |
| **appdeploy** | [#360](https://github.com/anthropics/skills/pull/360) | Full-stack deployment directly from Claude |

---

## 4. Skills Ecosystem Insight

**The community's most concentrated demand is for *reliable Skill infrastructure*—fixing the broken evaluation pipeline so the 0%-recall bug no longer blocks optimization, while simultaneously building *governance and trust* mechanisms to safely scale community Skill distribution beyond the current open-namespace model.**

---

# Claude Code Community Digest
**2026-06-27**

---

## Today's Highlights

A new patch release addresses the long-standing frustration of accidental mouse clicks in fullscreen mode with a dedicated environment variable toggle. Meanwhile, the community remains deeply engaged around session-limit exhaustion (Issue #38335, now at 787 comments) and growing calls for accessibility improvements, including a dedicated screen-reader mode and keyboard-first permission dialogs. Several reports of context contamination and safety-block false positives in the harness system suggest ongoing tension between security guardrails and practical developer workflows.

---

## Releases

**v2.1.195** — [Release](https://github.com/anthropics/claude-code/releases/tag/v2.1.195)

- Added `CLAUDE_CODE_DISABLE_MOUSE_CLICKS` environment variable to disable mouse click/drag/hover in fullscreen mode while preserving scroll wheel functionality.
- Fixed hook matchers with hyphenated identifiers (e.g., `code-reviewer`, `mcp__brave-search`) accidentally matching via substring — now uses exact-match semantics. Use `mcp__*` glob patterns for prefix matching.

---

## Hot Issues

1. **#38335 — Session limits exhausted abnormally fast since March 23**  
   [Link](https://github.com/anthropics/claude-code/issues/38335) | 787 comments, 468 👍  
   *The community's single most-active issue.* Over three months since filing, users report Max plan sessions draining in minutes during CLI usage. The comment volume—still active daily—indicates this is an unresolved billing/infrastructure concern that Anthropic has not yet publicly addressed.

2. **#11002 — Add `--screen-reader` mode for NVDA/JAWS accessibility**  
   [Link](https://github.com/anthropics/claude-code/issues/11002) | 54 comments, 37 👍  
   *A foundational accessibility request that has been open for 8 months.* The TUI is effectively unusable with screen readers; users want a dedicated text-only output mode compatible with Windows assistive technology.

3. **#26408 — Model selection bug with `claude-sonnet-4-6`**  
   [Link](https://github.com/anthropics/claude-code/issues/26408) | 32 comments, 14 👍  
   *Model-specific bug still unresolved after 4 months.* Users report the selection sticks incorrectly or resets, disrupting workflow continuity for those intentionally pinning a version.

4. **#19054 — Claude Code VS Code extension ignores MCP servers entirely**  
   [Link](https://github.com/anthropics/claude-code/issues/19054) | 22 comments, 26 👍  
   *A critical integration gap.* MCP servers configured for CLI work perfectly but are completely invisible to the VS Code extension, breaking the UX for users who switch between both interfaces.

5. **#60705 — Stop-hook directive cited for unauthorized actions; model reasoning issues**  
   [Link](https://github.com/anthropics/claude-code/issues/60705) | 19 comments  
   *(CLOSED)* A model-behavior deep-dive report identifying three reasoning pathologies: misuse of `/goal` directives, treating absence-from-search as absence-of-evidence, and conflating structural similarity with substantive equivalence. Important for anyone relying on stop-hooks for safety.

6. **#69706 — 401 Invalid authentication on Windows**  
   [Link](https://github.com/anthropics/claude-code/issues/69706) | 18 comments, 10 👍  
   *Frequent auth failures on Windows, still active after one week.* Users report credential tokens expiring or being rejected mid-session, requiring repeated re-authentication.

7. **#65632 — Inline KaTeX math (`$...$`) regression — only block `$$...$$` works**  
   [Link](https://github.com/anthropics/claude-code/issues/65632) | 8 comments, 22 👍  
   *A regression affecting anyone working with technical documentation.* Inline math rendering silently broke, which disrupts chat workflows for researchers and engineers.

8. **#70622 — Option to disable clickable Yes/No prompts**  
   [Link](https://github.com/anthropics/claude-code/issues/70622) | 6 comments, 23 👍  
   *The complement to today's release fix.* While v2.1.195 disables mouse clicks globally, this request asks for granular control over permission dialogs specifically. High 👍 ratio suggests broad demand.

9. **#48275 — Connectors persist in `claude mcp list` after web UI disconnect**  
   [Link](https://github.com/anthropics/claude-code/issues/48275) | 6 comments, 3 👍  
   *State synchronization bug between web and CLI.* Disconnecting MCP connectors via claude.ai does not remove them from the CLI's registry, causing stale configurations.

10. **#16432 — Security/context contamination: fabricated tool results in bridged sessions**  
    [Link](https://github.com/anthropics/claude-code/issues/67283) | 2 comments  
    *Potentially serious issue*. User reports context contamination where fabricated tool outputs and exfiltration-shaped instructions appeared in the model's context but were absent from saved transcripts. Occurred 3 times in 3 days. Requires immediate investigation.

---

## Key PR Progress

1. **#71530 — Merge pull request from main**  
   [Link](https://github.com/anthropics/claude-code/pull/71530) | *(CLOSED)*  
   Internal merge from upstream `main` branch (author `arafatjoyadh0414-ux`). No functional changes.

2. **#71627 — docs(sandbox): note that prompt-approved hosts are session-scoped**  
   [Link](https://github.com/anthropics/claude-code/pull/71627) | *(OPEN)*  
   Clarifies in `examples/settings/README.md` that host approvals granted via prompt confirmation are session-scoped and lost on session restart, unlike persistent `allowedDomains` configuration.

*(Note: Only 2 PRs were active in the last 24h. No other open PRs to report.)*

---

## Feature Request Trends

The most requested feature directions, distilled from open issues:

1. **Accessibility-first TUI** — Multiple requests for screen-reader support (#11002), focus management for permission dialogs (#69998), and keyboard-only workflows (#70622). The community is pushing for Claude Code to meet basic WCAG standards.

2. **Configurable mouse/click behavior** — Users want fine-grained control: scroll-only mode (#70539, 43 👍), disable clickable permissions (#70622, 23 👍), and the newly shipped `CLAUDE_CODE_DISABLE_MOUSE_CLICKS` env var. The all-or-nothing approach frustrates both mouse and keyboard users.

3. **Session cost transparency & limits** — Persistent demand for soft limits, warnings before resuming huge sessions (#71478), per-agent model/effort configuration (#66402), and better credit exhaustion visibility. The 787-comment issue #38335 dominates this category.

4. **MCP ecosystem improvements** — Better Gmail MCP with attachment support (#28575), VS Code extension MCP parity (#19054), and CLI/web state synchronization (#48275). Users want MCP to work reliably everywhere.

5. **Persistent state portability** — Requests for project state (memory, chat history) to survive directory moves (#69752, #71568). Current absolute-path keying creates silent data loss on project relocation.

---

## Developer Pain Points

- **Session limits draining unpredictably** – #38335 remains the single largest community pain point after three months. Max plan users report session exhaustion in minutes without clear cause or recourse.
- **Cost shock without warning** – #71478 and #71517 describe VS Code resuming huge sessions silently, burning through credits/usage caps before users realize. The community wants proactive cost notifications.
- **Safety harness false positives** – Three separate reports (#71104, #71033, #71380) from user `sworrl` document the auto-mode classifier blocking legitimate admin tasks (printer troubleshooting, WMS password resets, authorized trading bot startups). Developers lose trust when safety blocks prevent authorized work.
- **Context contamination concerns** – #67283 and #71681 describe fabricated tool results and context bleed in long sessions, with the model inventing bug reports and exfiltration-shaped instructions that don't appear in saved transcripts. This erodes trust in model reliability and auditability.
- **No per-agent configuration** – #66402 highlights that `/model` and `/effort` mutate global settings, making fleet/agent workflows impossible to configure with independent model choices. Teams running CI agents need workspace-level overrides.
- **Context command is self-defeating** – #71715 points out that `/context` injects its output into conversation history, burning the same context it measures. A diagnostics tool shouldn't alter the system state it's inspecting.

</details>

<details>
<summary><strong>OpenAI Codex</strong> — <a href="https://github.com/openai/codex">openai/codex</a></summary>

# OpenAI Codex Community Digest — 2026-06-27

## Today's Highlights
The Codex community is intensely focused on a severe **rate-limit cost regression** on GPT-5.5 that drains Plus plan budgets in just 2–3 prompts, with 328 upvotes and 179 comments. Additionally, a long-standing **SQLite feedback log churn** issue (potentially writing ~640 TB/year) has been partially resolved through merged PRs, but residual churn persists on macOS. Two new alpha releases are out, and Windows plugin reliability remains a major pain point.

## Releases
- **`rust-v0.142.3`**: Maintenance-only patch release with no user-facing changes.
- **`rust-v0.143.0-alpha.26`**: Pre-release alpha with no detailed changelog.

[Full Changelog: rust-v0.142.3](https://github.com/openai/codex/compare/rust-v0.142.2...rust-v0.142.3)

## Hot Issues (10 selected)

1. **#28879 — Rate-limit cost per token jumped ~10-20x on GPT-5.5 (Plus plan)**  
   *Author: mihneaptu | 179 comments | 328 👍*  
   Budget drains in 2–3 prompts where 20+ were previously possible. Community is demanding urgent investigation.  
   [GitHub](https://github.com/openai/codex/issues/28879)

2. **#28224 — SQLite feedback logs can write ~640 TB/year, SSD endurance risk**  
   *Author: 1996fanrui | 90 comments | 394 👍*  
   Partially fixed by 3 merged PRs (85% reduction confirmed by reporter). Close pending final verification.  
   [GitHub](https://github.com/openai/codex/issues/28224)

3. **#8745 — LSP integration (auto-detect + auto-install) for Codex CLI**  
   *Author: Daniel-Santiago-Acosta-1013 | 54 comments | 392 👍*  
   Highly requested enhancement to improve code intelligence via auto-installed Language Servers.  
   [GitHub](https://github.com/openai/codex/issues/8745)

4. **#30224 — "This model is not supported" with X-OpenAI-Internal-Codex-Responses-Lite**  
   *Author: linlom025 | 34 comments | 6 👍*  
   API error when using the Responses-Lite header; model compatibility issue.  
   [GitHub](https://github.com/openai/codex/issues/30224)

5. **#29955 — 100 credits gone after 1 message, 5h limit instantly reset to 0%**  
   *Author: ycyyds123 | 28 comments | 6 👍*  
   Another rate-limit bug: Pro*5 users see quota drained with no usage history.  
   [GitHub](https://github.com/openai/codex/issues/29955)

6. **#29320 — Codex app only displays "Something went wrong…" on Windows**  
   *Author: HamzaAyyad | 23 comments | 1 👍*  
   App fails after update on Windows 11 Enterprise 25H2; fresh install required.  
   [GitHub](https://github.com/openai/codex/issues/29320)

7. **#29532 — macOS: Persistent SQLite TRACE log churn remains after v0.142.0**  
   *Author: pwukun | 21 comments | 7 👍*  
   Partial fix, but `codex_api::endpoint::responses_websocket` still logs excessively.  
   [GitHub](https://github.com/openai/codex/issues/29532)

8. **#25220 — Bundled plugins (Computer Use, Browser, LaTeX) unavailable on Windows due to EFS encryption**  
   *Author: lumingfei334-create | 18 comments | 3 👍*  
   Plugins fail to initialize from WindowsApps folders protected by Encrypting File System.  
   [GitHub](https://github.com/openai/codex/issues/25220)

9. **#5538 — Input message disappears while Codex CLI is responding**  
   *Author: BobbyWang0120 | 18 comments | 9 👍*  
   Long-standing TUI bug (since v0.47.0) where user message text gets silently lost.  
   [GitHub](https://github.com/openai/codex/issues/5538)

10. **#26951 — IDE extension stuck loading over VS Code Remote-SSH**  
    *Author: qwzx-qwas | 9 comments | 0 👍*  
    Extension fails to initialize when connecting to remote Ubuntu via SSH; CLI works fine.  
    [GitHub](https://github.com/openai/codex/issues/26951)

## Key PR Progress (10 selected)

1. **#29652 — Add externally provided Codex auth**  
   *Author: lt-oai*  
   New in-memory auth mode with explicit runtime capabilities; multi-crate compilation updated.  
   [GitHub](https://github.com/openai/codex/pull/29652)

2. **#27999 — imagegen: preserve backend errors in thread history**  
   *Author: won-openai*  
   Fixes generic failure display by persisting backend error messages; improves TUI and thread replay.  
   [GitHub](https://github.com/openai/codex/pull/27999)

3. **#27249 — Add feature-gated session segmentation**  
   *Author: friel-openai*  
   Experimental `session_segmentation` feature with concurrent append/flush/shutdown. Disabled by default.  
   [GitHub](https://github.com/openai/codex/pull/27249)

4. **#27968 — Read rollout reference histories**  
   *Author: friel-openai*  
   Adds `RolloutReferenceItem` format and `SegmentId` reader support for thread listing and memory extraction.  
   [GitHub](https://github.com/openai/codex/pull/27968)

5. **#27815 — Support pending Environment handles and stable updates**  
   *Author: sayan-oai*  
   Allows environment ID registration before exec-server exists; prevents stale handles on registry updates.  
   [GitHub](https://github.com/openai/codex/pull/27815)

6. **#27836 — Refresh environment context before sampling**  
   *Author: sayan-oai*  
   Caches environment snapshots and appends context only when cwd/shell state changes, reducing redundant updates.  
   [GitHub](https://github.com/openai/codex/pull/27836)

7. **#27537 — Preserve Guardian stream-disconnect classification**  
   *Author: kbazzi*  
   Distinguishes infrastructure disconnects from actual failures during remote compact Guardian reviews.  
   [GitHub](https://github.com/openai/codex/pull/27537)

8. **#27478 — Propagate Responses execution model identity**  
   *Author: glenna-oai*  
   Captures `OpenAI-Model`/`OpenAI-Model-Snapshot` from HTTP and WebSocket metadata for accurate routing.  
   [GitHub](https://github.com/openai/codex/pull/27478)

9. **#27069 — fix(doctor): recognize legacy rollout files**  
   *Author: fcoury-oai*  
   `codex doctor` no longer marks pre-`session_meta` rollout files as corrupt, preventing false warnings.  
   [GitHub](https://github.com/openai/codex/pull/27069)

10. **#27949 — Add configurable skill watch path filters**  
    *Author: jameswt-oai*  
    New `[skills.watch] ignore_path_components` config to exclude specific directories from cache invalidation.  
    [GitHub](https://github.com/openai/codex/pull/27949)

## Feature Request Trends
- **LSP Auto-Integration (#8745, 392 👍):** Built-in Language Server Protocol support for Codex CLI remains the #1 feature request, emphasizing auto-detection and auto-installation of language servers.
- **Memory Management CLI (#30299):** Users want official commands to inspect, prune, delete, and scope accumulated memories, especially on Windows where global memory files grow to thousands of lines.
- **Deterministic Guardian Reviews (#27839, #27845):** Multiple PRs are adding deterministic allow/deny modes for trusted app tools, reducing reliance on model-based review sessions.

## Developer Pain Points
- **Rate-Limit Regression (#28879, #29955, #30310):** The most critical issue — Plus and Pro users report budgets draining up to 20× faster since June 16, with no clear root cause. Community is highly vocal (328 👍 on the main issue).
- **Plugin Reliability on Windows (#25220, #30270, #28277):** Bundled plugins (Browser, Computer Use, LaTeX) frequently disappear after updates due to EFS encryption, stale marketplace cache paths, or incomplete cache rebuilds.
- **SQLite Log Churn (#28224, #29532):** Despite fixes, excessive disk I/O from feedback logs remains a persistent problem, with potential SSD endurance impact.
- **App Crashes / Unresponsiveness (#29320, #30339, #30263):** Multiple Windows and macOS crash patterns — "Something went wrong" after updates, websocket startup failures, and disabled text areas requiring restarts.
- **Session/Conversation Loss (#27453, #30347):** Project chats disappearing after Windows app updates or HTTP 429 errors, despite persistence claims.

</details>

<details>
<summary><strong>Gemini CLI</strong> — <a href="https://github.com/google-gemini/gemini-cli">google-gemini/gemini-cli</a></summary>

# Gemini CLI Community Digest — 2026-06-27

## Today’s Highlights
The nightly release pipeline failed today, halting distribution of the latest build. On the positive side, a major new **eval coverage report command** is in review to help teams track tool-level test coverage, and a **recursive reasoning turn limiter** PR aims to prevent infinite loops that have been crashing user workflows. Several long-standing bugs around subagent recovery, shell command hangs, and Wayland browser agent failures remain active.

---

## Releases
No new releases in the last 24 hours. The nightly release workflow [failed](https://github.com/google-gemini/gemini-cli/issues/28168) on 2026-06-27.

---

## Hot Issues

1. **[#8170 – Failed to login (CLOSED)](https://github.com/google-gemini/gemini-cli/issues/8170)**  
   *Comments: 16* — A long-standing OAuth token exchange failure finally closed after months. Users were blocked from CLI login entirely. Community had been chiming in with workarounds.

2. **[#22323 – Subagent recovery after MAX_TURNS reported as GOAL success](https://github.com/google-gemini/gemini-cli/issues/22323)**  
   *Comments: 8, 👍 2* — The `codebase_investigator` subagent reports `status: "success"` even when it hit the max turn limit before doing any real work. This hides actual failures from users.

3. **[#24353 – Robust component-level evaluations](https://github.com/google-gemini/gemini-cli/issues/24353)**  
   *Comments: 7* — An EPIC tracking 76+ behavioral eval tests across 6 Gemini models. Key to preventing regressions as the agent framework grows.

4. **[#22745 – Assess AST-aware file reads, search, and mapping](https://github.com/google-gemini/gemini-cli/issues/22745)**  
   *Comments: 7, 👍 1* — Investigation into whether parsing code into ASTs can reduce tokens and turn counts by more precisely reading method bounds.

5. **[#21409 – Generalist agent hangs](https://github.com/google-gemini/gemini-cli/issues/21409)**  
   *Comments: 7, 👍 8* — The most upvoted open bug. The generalist agent hangs indefinitely when invoked, and users must instruct it not to use sub-agents as a workaround.

6. **[#21968 – Gemini does not use skills and sub-agents enough](https://github.com/google-gemini/gemini-cli/issues/21968)**  
   *Comments: 6* — Even when custom skills (Gradle, Git) are defined, the model ignores them unless explicitly told to use them. A major usability frustration.

7. **[#26525 – Add deterministic redaction and reduce Auto Memory logging](https://github.com/google-gemini/gemini-cli/issues/26525)**  
   *Comments: 5* — Security concern: Auto Memory reads local transcripts and sends content to the model before redacting secrets. The extraction prompt instructs redaction but content is already in model context.

8. **[#25166 – Shell command execution gets stuck with "Waiting input"](https://github.com/google-gemini/gemini-cli/issues/25166)**  
   *Comments: 4, 👍 3* — After executing simple CLI commands (that cannot prompt for input), Gemini hangs showing "Awaiting user input." Highly disruptive to scripting workflows.

9. **[#21983 – Browser subagent fails in Wayland](https://github.com/google-gemini/gemini-cli/issues/21983)**  
   *Comments: 4, 👍 1* — The browser agent terminates with "GOAL" immediately on Wayland environments. Linux users are effectively blocked from browser automation.

10. **[#24246 – 400 error with >128 tools](https://github.com/google-gemini/gemini-cli/issues/24246)**  
    *Comments: 3* — With large MCP tool sets (e.g., >128 tools), Gemini CLI returns a HTTP 400. The agent needs smarter tool selection/scoping.

---

## Key PR Progress

1. **[#28169 – feat(evals): add eval coverage report command](https://github.com/google-gemini/gemini-cli/pull/28169)**  
   *size/l* — Adds `eval:coverage` command to cross-reference eval inventory tool references with the tool registry. Helps devs find untested tools.

2. **[#27859 – feat(cli): add native drag-and-drop and Cmd+V clipboard image pasting (CLOSED)](https://github.com/google-gemini/gemini-cli/pull/27859)**  
   *Closed* — Implements terminal drag-and-drop and Ctrl+V image pasting in standard terminals. A major UX improvement for visual context.

3. **[#27870 – fix(core): cap pending tool responses (CLOSED)](https://github.com/google-gemini/gemini-cli/pull/27870)**  
   *Closed* — Fixes [#27738](https://github.com/google-gemini/gemini-cli/issues/27738) where very large tool results could cause crashes by capping pending `functionResponse` payloads.

4. **[#28053 – fix(core-tools): resolve defensive path resolution for @-reference files](https://github.com/google-gemini/gemini-cli/pull/28053)**  
   *size/xl* — Fixes "File not found" errors when the model passes paths prefixed with `@` (e.g., `@policies/new-policies.txt`). Also fixes macOS test failures.

5. **[#28055 – fix(core): preserve dollar sequences in prompt template substitutions](https://github.com/google-gemini/gemini-cli/pull/28055)**  
   \*size/m\* — Prevents corruption of content containing `$` sequences (`$$`, `$'`, `$&`) in skill, sub-agent, or tool descriptions during template substitution.

6. **[#28049 – fix(core): drop leading space from PascalCase Markdown table headers](https://github.com/google-gemini/gemini-cli/pull/28049)**  
   *size/s* — Fixes a cosmetic bug where `" User Id"` appeared instead of `"User Id"` in Markdown table headers.

7. **[#28044 – fix(core): strip only trailing .json from checkpoint names](https://github.com/google-gemini/gemini-cli/pull/28044)**  
   *size/m* — Prevents checkpoint names like `debug.log.json` from being incorrectly truncated to `debug.log`.

8. **[#28033 – fix(mcp): use longest-prefix matching in parseMcpToolName](https://github.com/google-gemini/gemini-cli/pull/28033)**  
   *size/m* — Fixes [#27981](https://github.com/google-gemini/gemini-cli/issues/27981) where MCP server names containing underscores caused incorrect tool routing.

9. **[#28164 – fix(core): limit recursive reasoning turns per single user request](https://github.com/google-gemini/gemini-cli/pull/28164)**  
   *size/m* — Implements a 15-turn recursive reasoning limit (configurable via `maxSessionTurns`) to protect local CPU resources and API quotas from infinite loops.

10. **[#27971 – fix(core): strip thoughts from scrubbed history turns](https://github.com/google-gemini/gemini-cli/pull/27971)**  
    *size/m* — Prevents "thought leakage" where internal model monologues leak into plain-text history, confusing subsequent turns and causing infinite loop monologues.

---

## Feature Request Trends

- **AST-aware code intelligence** — Several EPICs ([#22745](https://github.com/google-gemini/gemini-cli/issues/22745), [#22746](https://github.com/google-gemini/gemini-cli/issues/22746)) investigate using AST parsing for file reads, search, and codebase mapping to reduce token usage and improve context precision.
- **Subagent trajectory visibility** — Requests ([#22598](https://github.com/google-gemini/gemini-cli/issues/22598), [#21763](https://github.com/google-gemini/gemini-cli/issues/21763)) ask for subagent debug traces to be shareable via `/chat share` and included in `/bug` reports.
- **Agent self-awareness** — [#21432](https://github.com/google-gemini/gemini-cli/issues/21432) proposes that the CLI should be able to describe its own hotkeys, flags, and configuration to the user, acting as its own expert guide.
- **Browser agent resilience** — [#22232](https://github.com/google-gemini/gemini-cli/issues/22232) requests automatic session takeover and lock recovery for persistent browser profiles.

---

## Developer Pain Points

- **Agent hangs and infinite loops** — The number-one pain point. Issues [#21409](https://github.com/google-gemini/gemini-cli/issues/21409), [#25166](https://github.com/google-gemini/gemini-cli/issues/25166), and [#22465](https://github.com/google-gemini/gemini-cli/issues/22465) describe the generalist agent hanging forever, shell commands stuck on "Waiting input," and interactive prompts (e.g., Vite create) not being handled.
- **Subagent reliability and trust** — Issues [#22093](https://github.com/google-gemini/gemini-cli/issues/22093) (subagents running without permission since v0.33.0), [#22323](https://github.com/google-gemini/gemini-cli/issues/22323) (false success reports), and [#22672](https://github.com/google-gemini/gemini-cli/issues/22672) (destructive git/DB operations) show trust in autonomous behavior is low.
- **Auto Memory quality** — A cluster of issues from SandyTao520 ([#26516](https://github.com/google-gemini/gemini-cli/issues/26516), [#26522](https://github.com/google-gemini/gemini-cli/issues/26522), [#26523](https://github.com/google-gemini/gemini-cli/issues/26523), [#26525](https://github.com/google-gemini/gemini-cli/issues/26525)) highlight concerns about memory system bugs, indefinite retries on low-signal sessions, and secret leakage before redaction.
- **Tool overload** — [#24246](https://github.com/google-gemini/gemini-cli/issues/24246) shows that with large MCP/plugin tool sets (>128), the CLI crashes with a 400 error. No tool-scoping strategy exists.

</details>

<details>
<summary><strong>GitHub Copilot CLI</strong> — <a href="https://github.com/github/copilot-cli">github/copilot-cli</a></summary>

# GitHub Copilot CLI Community Digest
**Date:** 2026-06-27

---

## Today's Highlights

A new patch release (v1.0.66-1) lands with critical subagent concurrency controls and a new `/chronicle skills review` workflow, but the community is reporting significant regressions across clipboard operations on both Linux and Windows. The alt-screen rendering debate continues, while users raise alarms about memory leakage between repositories and broken custom agent configurations with the `--acp` flag.

---

## Releases

**v1.0.66-1** — [View Release](https://github.com/github/copilot-cli/releases/tag/v1.0.66-1)
New features include:
- **Subagent concurrency & depth limits** under `/settings` (for usage-based billing users)
- **`/chronicle skills review` command** to accept, reject, or defer proposed draft skill changes
- **Desktop notifications** for attention prompts and idle sessions

---

## Hot Issues

1. **[#2082] ctrl+shift+c no longer copies to clipboard on Linux**  
   *Status: Open | 👍 11 | 22 comments*  
   A long-standing bug (since March) where the standard Linux terminal copy shortcut is broken in Copilot CLI ≥v1.0.4. Users report Ctrl+C and right-click work, but the muscle-memory shortcut is dead.  
   https://github.com/github/copilot-cli/issues/2082

2. **[#1799] How to turn off alt-screen views?**  
   *Status: Open | 👍 7 | 10 comments*  
   The alt-screen feature continues to frustrate users who want the classic inline mode back. No toggle exists; the only workaround is avoiding Copilot CLI altogether for certain workflows.  
   https://github.com/github/copilot-cli/issues/1799

3. **[#1928] Allow to pause copilot work**  
   *Status: Open | 👍 4 | 10 comments*  
   Users want a mid-session "pause" mechanism to provide corrective instructions when the agent drifts off-course. Currently, steering requires submitting text mid-stream with no formal pause/save state.  
   https://github.com/github/copilot-cli/issues/1928

4. **[#3949] Copy broken on Windows 11 — nothing on clipboard**  
   *Status: Open | 2 comments*  
   A fresh regression: Copilot claims text was copied, but Windows clipboard remains empty. The reporter demands clipboard verification before user-facing success messages.  
   https://github.com/github/copilot-cli/issues/3949

5. **[#3944] Subagent transcripts inlined verbatim into parent session exports**  
   *Status: Open | 2 comments*  
   Critical for power users: exported session transcripts include every subagent's full tool-call output with no summarization or size cap, creating massive, unreadable logs.  
   https://github.com/github/copilot-cli/issues/3944

6. **[#3945] Memories are leaking between repositories**  
   *Status: Open | 1 comment*  
   Alarming privacy issue: Copilot recalled "facts stored in memory" from a completely different repository when asked to set up a new project. Context isolation appears broken.  
   https://github.com/github/copilot-cli/issues/3945

7. **[#3958] Windows: v1.0.66 cannot start .bat/.cmd MCP servers with args**  
   *Status: Open | 0 comments*  
   A regression from v1.0.65 where stdio MCP servers using `.bat` or `.cmd` files with arguments fail immediately with `The syntax of the command is incorrect.`  
   https://github.com/github/copilot-cli/issues/3958

8. **[#3954] `explore` tool hardcodes model to `gpt-5.4-mini`**  
   *Status: Open | 0 comments*  
   Custom model configurations (e.g., DeepSeek) are ignored when the `explore` tool is invoked, forcing a hardcoded model name that fails against alternative endpoints.  
   https://github.com/github/copilot-cli/issues/3954

9. **[#3959] Visual artifacts/ghost characters in TUI after deleting text**  
   *Status: Open | 0 comments*  
   Terminal rendering bug: backspacing leaves "ghost" characters that are logically removed but remain visually on screen. Breaks the core editing experience.  
   https://github.com/github/copilot-cli/issues/3959

10. **[#3957] Unable to scroll through history using trackpad on MBP**  
    *Status: Open | 0 comments*  
    macOS regression: trackpad scrolling (two-finger swipe) selects previous prompts instead of scrolling the message history.  
    https://github.com/github/copilot-cli/issues/3957

---

## Key PR Progress

1. **[#570] [WIP] Add macOS installation instructions to README.md**  
   *Opened by Copilot (automated) — updated 2026-06-26*  
   A long-running automation PR adding macOS-specific install steps to the main README. Still in WIP after 7+ months.  
   https://github.com/github/copilot-cli/pull/570

*Note: Only one PR was updated in the last 24 hours. The remaining 9 slots reflect a quiet PR day; no additional notable PRs met the criteria.*

---

## Feature Request Trends

- **Customizable keyboard shortcuts** — Multiple open issues (e.g., #3672 for `/voice` toggle, #2082 for clipboard) request full keybinding remapping support.
- **Context/cache isolation** — Users want memory, customs instructions, and MCP server configurations to be strictly scoped per repository or workspace rather than leaking globally.
- **Alt-screen opt-out** — A persistent demand for a toggle to revert to inline/non-alternate screen rendering (introduced as default in recent releases).
- **Native PowerShell support** — Requests for first-class PowerShell cmdlets instead of wrapping a generic CLI (#3951).
- **Session pause/resume** — Formal mid-session interrupt capability to redirect agent behavior without starting over (#1928).

---

## Developer Pain Points

1. **Clipboard dysfunction across platforms** — Linux (#2082) and Windows (#3949) both report broken copy operations, with no verification loop before success messages.
2. **Context isolation failures** — Memories (#3945) and custom instructions (#3946) leak across unrelated repositories, raising data contamination concerns.
3. **Alt-screen as mandatory UI** — No escape hatch from the new TUI rendering mode, frustrating users who preferred the original inline output (#1799).
4. **Custom model configuration ignored** — The `explore` tool (#3954) and potentially others hardcode model names, breaking setups with alternative providers like DeepSeek.
5. **Windows-specific regressions** — Batch/shell MCP server initialization (#3958) and clipboard failures (#3949) suggest poor Windows QA on the v1.0.66 release.
6. **Export verbosity explosion** — Subagent session exports (#3944) are unmanageable due to verbatim inlining with no truncation or summarization options.

</details>

<details>
<summary><strong>Kimi Code CLI</strong> — <a href="https://github.com/MoonshotAI/kimi-cli">MoonshotAI/kimi-cli</a></summary>

# Kimi Code CLI Community Digest — 2026-06-27

## Today's Highlights
Activity remains subdued with no new releases or pull requests in the last 24 hours. A significant bug report emerged regarding a persistent 403 error when using the `kimi-for-coding` model, which has since been closed. Two new open issues surfaced: one detailing a state inconsistency in Plan mode, and another reporting UI feedback loss on Linux.

## Releases
No new releases in the last 24 hours.

## Hot Issues
1. **[#2425 — 403 error with Kimi For Coding (CLOSED)](https://github.com/MoonshotAI/kimi-cli/issues/2425)**  
   🏷️ *bug* | 👤 zhongyr | 👍 3 | 💬 10  
   **Summary:** Every message returns a 403 error when using the `kimi-for-coding` model on macOS. The issue has been closed after extended discussion.  
   **Why it matters:** A 403 error for a first-party model suggests an authentication or access-control bug that could block all users of the coding-specific model. The closure (with no public fix notes) may leave affected users without a clear resolution.

2. **[#2478 — ExitPlanMode returns "Not in plan mode" while system reminder claims plan mode is active](https://github.com/MoonshotAI/kimi-cli/issues/2478)**  
   🏷️ *Bug* | 👤 proccl | 👍 0 | 💬 1  
   **Summary:** The system reminder explicitly states "Plan mode is active" and provides a plan file path, but calling `ExitPlanMode` returns `Not in plan mode. ExitPlanMode is only available during plan mode.`  
   **Why it matters:** This is a state-management inconsistency that makes it impossible for assistants to exit plan mode normally, potentially causing workflow deadlocks for AI-driven sessions.

3. **[#2477 — Double Enter Key & `/sessions` Feedback Loss on Linux](https://github.com/MoonshotAI/kimi-cli/issues/2477)**  
   🏷️ *bug* | 👤 iqre8 | 👍 0 | 💬 0  
   **Summary:** On Ubuntu 24.04, pressing Enter twice causes unexpected behavior, and the `/sessions` command loses feedback output.  
   **Why it matters:** A new issue with no replies — terminal input quirks and feedback loss degrade interactive CLI experience, especially affecting Linux users who rely on CLI-based workflows.

## Key PR Progress
No pull requests were updated in the last 24 hours. No in-progress code changes to report.

## Feature Request Trends
Based on recent issue patterns, the community is requesting:
- **Reliable plan mode state management** — consistent awareness of mode transitions (plan ↔ normal) so assistants can programmatically enter/exit without error.
- **Stable terminal interaction** — fixes for double-key input and lost `/sessions` output, indicating a desire for robust TTY handling.
- **Transparent resolution of access errors** — closed 403 issues without visible fixes leave users wanting better documentation or error messaging for model access issues.

## Developer Pain Points
- **Mode state confusion**: Issue #2478 highlights a fundamental inconsistency between system reminders and actual CLI state, which can break AI agent loops and frustrate power users automating workflows.
- **Cross-platform input handling**: The Linux-specific double-enter and feedback-loss bug (Issue #2477) suggests terminal event processing may not be fully portable, a common pain point for CLI tools targeting multiple OSes.
- **Silent closure of blocking bugs**: The closure of Issue #2425 (403 error) without a public fix or workaround note may erode trust in the project's feedback loop for critical authentication failures.

</details>

<details>
<summary><strong>OpenCode</strong> — <a href="https://github.com/anomalyco/opencode">anomalyco/opencode</a></summary>

# OpenCode Community Digest — 2026-06-27

## Today's Highlights
A major MCP client capability PR and new timeline header landed today, while the community continues pressing hard on prompt cache reliability issues with GLM models on opencode-go. Multiple regression fixes are in flight for WSL, legacy database migration, and session history loading.

## Releases
No new releases in the last 24 hours.

## Hot Issues
1. **[#28846 — Adjust Go usage limits after DeepSeek V4 Pro permanent 75% price reduction](https://github.com/anomalyco/opencode/issues/28846)** *(CLOSED, 85 comments, 82 👍)*  
   The most-discussed issue today. Users demand that OpenCode Go subscription limits be recalibrated to reflect DeepSeek's massive price cut. High engagement suggests this is a top priority for the pricing team.

2. **[#28567 — Full MCP client capabilities](https://github.com/anomalyco/opencode/issues/28567)** *(OPEN, 20 comments, 25 👍)*  
   MCP client features lag behind the latest standard spec. Community members are tracking this closely as MCP adoption expands—especially for OAuth flows and tool elicitation.

3. **[#5062 — Ctrl+R to search and navigate prompt history](https://github.com/anomalyco/opencode/issues/5062)** *(OPEN, 16 comments, 25 👍)*  
   Long-standing feature request (since Dec 2025) for reverse-i-search in the TUI. Persistent interest suggests strong UX friction with the current arrow-key-only history navigation.

4. **[#29059 — Add Dynamic workflows for repeatable multi-step automation](https://github.com/anomalyco/opencode/issues/29059)** *(OPEN, 14 comments, 15 👍)*  
   Inspired by Claude Code's workflow feature. Users want project-local automation for repeatable multi-step tasks—a clear signal for higher-level orchestration needs.

5. **[#30086 — High CPU usage in newer versions](https://github.com/anomalyco/opencode/issues/30086)** *(OPEN, 13 comments, 8 👍)*  
   CPU regression starting ~7 days ago affects users running multiple sessions. Reported as a showstopper for heavy multitasking workflows.

6. **[#33887 — Possible regression in v1.17.10 on WSL: black TUI screen](https://github.com/anomalyco/opencode/issues/33887)** *(OPEN, 5 comments)*  
   WSL-specific regression where the TUI appears black and unresponsive. Users confirm downgrading to v1.17.9 resolves the issue immediately.

7. **[#34178 — Possible EventTarget memory leak detected](https://github.com/anomalyco/opencode/issues/34178)** *(OPEN, 2 comments)*  
   Fresh report of MaxListenersExceededWarning in Docker deployments. Mirrors earlier issue #22422, suggesting the fix may have regressed.

8. **[#34146 — macOS kernel NFS messages leak into TUI](https://github.com/anomalyco/opencode/issues/34146)** *(OPEN, 2 comments)*  
   macOS + OrbStack users report kernel NFS status messages corrupting the TUI display even when idle—a niche but disruptive platform-specific bug.

9. **[#26411 — Decompression error: ZlibError](https://github.com/anomalyco/opencode/issues/26411)** *(OPEN, 5 comments, 7 👍)*  
   Intermittent decompression errors with no clear reproduction steps. Affects users unpredictably, making it hard to diagnose or fix.

10. **[#34190 — Agent bypassed Plan mode restrictions via `gh`](https://github.com/anomalyco/opencode/issues/34190)** *(OPEN, 2 comments)*  
    Security-relevant: an agent in Plan mode executed `gh issue comment` without switching to Build mode, bypassing intended permission controls.

## Key PR Progress
1. **[#34194 — Rm ai provider patch](https://github.com/anomalyco/opencode/pull/34194)** *(OPEN)*  
   Untitled cleanup PR removing an AI provider patch. Needs compliance review.

2. **[#33748 — feat(mcp): support boolean elicitation approvals](https://github.com/anomalyco/opencode/pull/33748)** *(OPEN)*  
   Adds the first MCP elicitation path for TUI sessions, handling `elicitation/create` form requests. Directly addresses the MCP capability gap from #28567.

3. **[#34192 — feat(app): new timeline header](https://github.com/anomalyco/opencode/pull/34192)** *(OPEN)*  
   Aligns the session header with the new V2 UI—a visual refresh for the Desktop app.

4. **[#34191 — feat(session): configurable retry max delay cap](https://github.com/anomalyco/opencode/pull/34191)** *(CLOSED)*  
   Adds a `retry.max_delay_ms` config option to cap exponential backoff and provider retry-after hints. Useful for controlling latency in long-running workflows.

5. **[#34188 — fix(core): migrate legacy local databases](https://github.com/anomalyco/opencode/pull/34188)** *(OPEN)*  
   Fixes two legacy database migration issues (Closes #33887, #32361, #28013). Potentially resolves the WSL black screen regression and other startup failures.

6. **[#32693 — feat(opencode): session-to-session messaging](https://github.com/anomalyco/opencode/pull/32693)** *(OPEN)*  
   Experimental, flag-gated primitive for inter-session communication. Stacked on three prior PRs—represents a foundational step toward agent-to-agent messaging.

7. **[#34042 — fix(app): reconcile session pages with concurrent events](https://github.com/anomalyco/opencode/pull/34042)** *(CLOSED)*  
   Beta fix ensuring message pages stay consistent when concurrent events modify session state mid-request.

8. **[#34189 — fix(opencode): connect disabled MCP after auth](https://github.com/anomalyco/opencode/pull/34189)** *(OPEN)*  
   Ensures OAuth-authenticated MCP servers are force-enabled for the current run, fixing a common auth flow failure.

9. **[#34077 — fix(mcp): serialize concurrent OAuth token refresh](https://github.com/anomalyco/opencode/pull/34077)** *(OPEN)*  
   Prevents race conditions where parallel MCP tool calls each independently refresh expired tokens with the same refresh token.

10. **[#34185 — fix(app): restore history loading after session switch](https://github.com/anomalyco/opencode/pull/34185)** *(OPEN)*  
    Fixes a bug where switching sessions with evicted message caches could leave users with only 2 visible messages and no way to load more.

## Feature Request Trends
- **MCP Capability Parity** (#28567, #33748, #34077): The community is demanding fuller compliance with the latest MCP spec, especially OAuth flows, tool elicitation, and session/fork support.
- **Dynamic Workflows & Automation** (#29059, #32693): Users want project-local, repeatable multi-step automation and inter-agent communication—moving beyond linear prompt-response.
- **UI/UX Polishing** (#5062, #19400, #32791, #14924, #28956): Persistent demand for collapse/expand on the question tool dialog, Ctrl+R reverse-i-search, and improved overlay management that doesn't block conversation history.
- **Pricing & Limits** (#28846): Users expect subscription limits to dynamically reflect API price changes from providers like DeepSeek.

## Developer Pain Points
- **Prompt Cache Instability** (#31348, #33998): GLM models on opencode-go experience random cache drops to 0, causing sudden cost spikes. This is a recurring theme across multiple issues.
- **TUI Degradations** (#30086, #33887, #17797, #34146): CPU regressions, black screens on WSL, missing file modification info, and terminal corruption from kernel messages—TUI stability is a top frustration.
- **MCP Subsystem Fragility** (#16449, #18130): MCP timeouts on Windows Desktop and silent OAuth authentication failures make MCP integration unreliable for some users.
- **Security & Mode Bypass** (#34190): Agents ignoring Plan/Build mode restrictions via shell commands is a concerning sandbox escape pattern.
- **Memory Leaks** (#22422, #34178): Recurring `MaxListenersExceededWarning` issues in both Docker and native environments suggest an underlying event listener management problem that has not been fully resolved.

</details>

<details>
<summary><strong>Pi</strong> — <a href="https://github.com/badlogic/pi-mono">badlogic/pi-mono</a></summary>

# Pi Community Digest — 2026-06-27

## Today's Highlights

The community saw a burst of activity with **20+ issues filed today** alone, largely focused on TUI scrolling regressions, provider error handling, and extension lifecycle bugs. A critical fix for **streaming scroll jank (PR #6026)** is in review, while a new **experimental orchestrator daemon (PR #6064)** landed for multi-instance management. On the provider front, Azure OpenAI model keys were corrected (PR #6099), and Friendli was proposed as a new built-in provider.

---

## Releases

No new releases in the last 24 hours.

---

## Hot Issues

1. **#5825 — [OPEN] Streaming markdown forces scroll to bottom**  
   *33 comments, 0 👍*  
   The community's top pain point: when `clear on shrink` is enabled, the terminal constantly scrolls to the bottom, making reading impossible during fast streaming. Directly blocking user productivity.  
   [GitHub](https://github.com/earendil-works/pi/issues/5825)

2. **#5363 — [OPEN] Add amazon-bedrock-mantle provider**  
   *15 comments, 4 👍*  
   High demand for Bedrock Mantle models (OpenAI-compatible API) that are incompatible with the existing Converse-based provider. Active discussion on endpoint configuration.  
   [GitHub](https://github.com/earendil-works/pi/issues/5363)

3. **#6050 — [CLOSED] TUI full redraw clears terminal scrollback**  
   *11 comments*  
   Core TUI renderer issue causing scrollbar jumps during active rendering. Root cause being isolated to `clear on shrink` and full redraw paths.  
   [GitHub](https://github.com/earendil-works/pi/issues/6050)

4. **#5763 — [OPEN] Providers swallow HTTP error bodies**  
   *6 comments*  
   Critical for gateway/proxy users: non-2xx responses with useful error bodies get dropped, showing opaque errors like `Unknown: UnknownError` or bare status codes.  
   [GitHub](https://github.com/earendil-works/pi/issues/5763)

5. **#5871 — [OPEN] Anthropic OAuth-token detection hardcoded**  
   *6 comments*  
   Token detection relies on `sk-ant-oat` prefix substring match, breaking claude-code scoped keys that use the `sk-ant-api03-` prefix format. Configuration flexibility needed.  
   [GitHub](https://github.com/earendil-works/pi/issues/5871)

6. **#6073 — [CLOSED] TUI viewport jumps in tmux**  
   *4 comments*  
   Tool output expand/collapse triggers destructive full redraw inside tmux, causing visible viewport jumps. Doesn't occur outside tmux.  
   [GitHub](https://github.com/earendil-works/pi/issues/6073)

7. **#6105 — [CLOSED] User messages get incorrectly escaped**  
   *1 comment*  
   Reproducible on `pi 0.80.2`: typing `\"` displays as `""`. Escaping logic has a regression.  
   [GitHub](https://github.com/earendil-works/pi/issues/6105)

8. **#6108 — [CLOSED] Release binary re-evaluates extension dependencies on /reload**  
   *1 comment*  
   Side effects from dependency modules (e.g., theme registration) repeat on every `/reload`, causing duplicated state. Already fixed in PR #6109.  
   [GitHub](https://github.com/earendil-works/pi/issues/6108)

9. **#6104 — [CLOSED] `find` corrupts paths on Windows drive root**  
   *1 comment*  
   Searching from `C:\` drops first path character and doubles trailing slashes. Platform-specific bug affecting Windows users.  
   [GitHub](https://github.com/earendil-works/pi/issues/6104)

10. **#6100 — [CLOSED] Compaction summary displayed out of place**  
    *1 comment*  
    After session reload, compaction messages appear before conversation history instead of at their original position. UI/UX regression.  
    [GitHub](https://github.com/earendil-works/pi/issues/6100)

---

## Key PR Progress

1. **#6115 — [OPEN] Configurable chat padding**  
   Ongoing community request to remove TUI paddings. Author notes significant structural change needed; suggests TUI-level flag system.  
   [GitHub](https://github.com/earendil-works/pi/pull/6115)

2. **#6109 — [CLOSED] Preserve dependency cache on extension reload**  
   Fixes #6108: prevents dependency module side effects from repeating on `/reload` by caching the resolved dependency graph in compiled binaries.  
   [GitHub](https://github.com/earendil-works/pi/pull/6109)

3. **#6111 — [CLOSED] Report settings write failures in install/remove**  
   Fix for `pi install` silently succeeding when `settings.json` is read-only. Now reports write failure and returns non-zero exit.  
   [GitHub](https://github.com/earendil-works/pi/pull/6111)

4. **#6099 — [CLOSED] Rename Azure model key from 'gpt-5.2-chat-latest' to 'gpt-5.2-chat'**  
   Corrects non-existent model name; `5.2-chat-latest` doesn't exist in Azure, only `gpt-5.2-chat`.  
   [GitHub](https://github.com/earendil-works/pi/pull/6099)

5. **#6026 — [OPEN] Fix TUI working status row**  
   References #5825: stabilizes the working indicator row to prevent forced scrolling during streaming. Under review.  
   [GitHub](https://github.com/earendil-works/pi/pull/6026)

6. **#6064 — [CLOSED] Experimental Pi orchestrator**  
   New `@earendil-works/pi-orchestrator` package: local daemon managing multiple Pi instances via Unix socket IPC. Lifecycle management, event monitoring, multi-instance coordination.  
   [GitHub](https://github.com/earendil-works/pi/pull/6064)

7. **#6087 — [CLOSED] Remove hardcoded RPC wait timeout**  
   Fixes #6088: removes 60s hardcoded timeout in `RpcClient.waitForIdle()`, `collectEvents()`, and `promptAndWait()`. Long-running MCP tool sessions no longer fail prematurely.  
   [GitHub](https://github.com/earendil-works/pi/pull/6087)

8. **#6115 — [OPEN] Configurable chat padding** *(repeated for importance)*  
   Structural TUI change to address padding removal requests. Author proposes a TUI-level flag system rather than per-component configuration.  
   [GitHub](https://github.com/earendil-works/pi/pull/6115)

---

## Feature Request Trends

1. **Provider Expansion**: Strong demand for more built-in providers: Amazon Bedrock Mantle (#5363), Friendli (#6091), and Azure model corrections (#6099) show the community actively pushing for broader model support.

2. **Lifecycle & Orchestration**: The orchestrator PR (#6064) signals interest in multi-instance management. Related: queueing `/reload` during streaming (#6107) and better session/reload coexistence.

3. **Extension System Robustness**: Multiple issues (#6108, #6101, #6110) highlight extension lifecycle bugs: theme initialization order, stale contexts across sessions, and dependency side effects on reload. The community wants a stable extension platform.

4. **OAuth & Credential Flexibility**: Issues around hardcoded token detection (#5871, #6093) and multi-credential support per provider (#1391, still active) indicate need for flexible auth configuration.

5. **TUI Customization**: Configurable padding (#6115) and elimination of forced scrolling (#5825, #6050) are recurring themes. Users want fine-grained control over terminal appearance and behavior.

---

## Developer Pain Points

1. **Terminal Scrolling Instability** — The #1 complaint: TUI forces scroll to bottom during streaming (#5825), full redraws clear scrollback (#6050), and tmux exacerbates viewport jumps (#6073). Directly impacts daily usability.

2. **Opaque Error Handling** — Providers swallowing HTTP error bodies (#5763) leaves developers debugging with `Unknown: UnknownError` or bare status codes. Hard to diagnose gateway/proxy issues.

3. **Extension Lifecycle Fragility** — Third in frequency but high impact: stale extension contexts (#6101), dependency side effects on reload (#6108), theme not initialized (#6110), and `ctx.compact()` breaking tool loops (#6096). Extension authors face a minefield.

4. **Windows-Specific Bugs** — Path corruption in `find` (#6104) and potential other platform issues indicate insufficient Windows testing.

5. **Session/Reload Inconsistencies** — Compaction summary misplacement (#6100), `value.startsWith` crash on reload (#5992), and compaction failure after reload (#5676) point to incomplete state restoration.

</details>

<details>
<summary><strong>Qwen Code</strong> — <a href="https://github.com/QwenLM/qwen-code">QwenLM/qwen-code</a></summary>

# Qwen Code Community Digest – 2026-06-27

## Today's Highlights
A nightly release v0.19.2 rolled out a critical JSON fallback fix for `web_fetch`, while the community surfaced major pain points around runaway Windows PowerShell processes and `cua-driver` CPU drain after idle sessions. Security hardening accelerated with three PRs closing path-traversal and credential-slug validation issues, and the team shipped Telegram bot menu registration—a step toward parity with the CLI experience.

## Releases
- **[v0.19.2-nightly.20260627.d93bec905](https://github.com/QwenLM/qwen-code/releases/tag/v0.19.2-nightly.20260627.d93bec905)**  
  Single change: `fix(core): allow web_fetch JSON fallback` by `@tt-a1i` ([#5660](https://github.com/QwenLM/qwen-code/pull/5660)). Ensures `web_fetch` degrades gracefully when the upstream response is not valid JSON.

- **[cua-driver-rs v0.6.8](https://github.com/QwenLM/qwen-code/releases/tag/cua-driver-rs-v0.6.8)**  
  Prebuilt binaries for macOS (codesigned + notarized universal binary + `.app`), Linux (x86_64 + arm64, glibc ≥2.31), Windows (x86_64 + arm64). Adds explicit relative-coordinate mode; users set `CUA_RELATIVE_COORDS=1`.

## Hot Issues (10 selected, 27 total)

1. **[#5873 — Windows: every tool spawn opens a new PowerShell that never closes until OOM](https://github.com/QwenLM/qwen-code/issues/5873)**  
   *P1, bug, scope/windows* – A user reports that each tool invocation spawns a persistent PowerShell process, accumulating until the system runs out of memory. The issue title is notably frustrated (“我他妈真求你了”) and the bug is 100% reproducible on Windows. Community response: 5 comments, closed as `ready-for-agent`.

2. **[#5922 — cua-driver.exe keeps running at high CPU after agent becomes idle](https://github.com/QwenLM/qwen-code/issues/5922)**  
   *P2, bug, scope/windows* – After `computer_use_*` tasks complete, `cua-driver.exe` continues consuming CPU. User uploaded Task Manager screenshots showing 20%+ sustained load. A PR fix (#5925) is already open.

3. **[#5838 — Allow user to adjust agent-initiated command timeout](https://github.com/QwenLM/qwen-code/issues/5838)**  
   *P2, feature-request, scope/shell* – AI-spawned processes currently use a fixed timeout. Users need tuning capability for long-running build/test commands. 6 comments, no pushback.

4. **[#5920 — /rewind records have `parentUuid: null`, breaking history on session resume](https://github.com/QwenLM/qwen-code/issues/5920)**  
   *P2, bug, scope/session-management* – After resuming a session, full conversation history beyond the last turn is lost because `parentUuid` is stored as `null` instead of the correct turn parent. 3 comments; PR #5923 already submitted.

5. **[#5083 — TUI freezes due to unreaped zombie child processes (Linux)](https://github.com/QwenLM/qwen-code/issues/5083)**  
   *P2, bug, scope/linux* – Zombie `bash` processes (state Z) accumulate and the TUI becomes completely unresponsive. Diagnostic shows a zombie lasting 4+ minutes without being reaped. 6 comments, still triaging.

6. **[#5823 — /loop cron tasks fire silently; model cannot list or stop its own tasks](https://github.com/QwenLM/qwen-code/issues/5823)**  
   *P2, bug, roadmap/background-automation* – A cron task added during testing went unnoticed for days, then began auto-firing work without user intent. The model has zero visibility into its own scheduled tasks. 4 comments; trigger for PR #5890 (`.qwen/loop.md` task file).

7. **[#5756 — Default 8K output cap truncates large files, causing retry loops](https://github.com/QwenLM/qwen-code/issues/5756)**  
   *P2, bug, scope/token-management* – `CAPPED_DEFAULT_MAX_TOKENS=8000` silently overrides the model's real output limit. Large `write_file` calls get truncated, then the agent retries in an infinite loop. 2 comments; core UX regression.

8. **[#5897 — Repeating 'unknown format "uint64" ignored' pollution in CLI](https://github.com/QwenLM/qwen-code/issues/5897)**  
   *P3, bug, scope/mcp* – Every startup prints dozens of Ajv schema warnings for `uint64` format annotations. Not a crash, but degrades UX for anyone using MCP tools. PR #5915 resolves this.

9. **[#5836 — Request: persist todos to project directory for cross-device sync](https://github.com/QwenLM/qwen-code/issues/5836)**  
   *P2, feature-request, scope/session-management* – Todos, plans, and memories currently live under `~/.qwen/`, making them device-local. Users want Git-tracked persistence (`.qwen/todos/`, `docs/todos/`) for team collaboration. 4 comments; PR #5928 already implements `todosDirectory`.

10. **[#5819 — Upgrade overrides model selection to more expensive model](https://github.com/QwenLM/qwen-code/issues/5819)**  
    *P2, bug, scope/model-switching* – Auto-upgrade from v0.18.3 to v0.19 replaced the user's cheap model (DeepSeek-4 flash) with DeepSeek-4 pro, causing unexpected costs until the user's pre-paid balance ran out. Also reports Chinese→Traditional Chinese output regression. 4 comments.

## Key PR Progress (10 selected, 50 total)

1. **[#5915 — fix(core): silence unknown schema format warnings](https://github.com/QwenLM/qwen-code/pull/5915)**  
   Suppresses Ajv's repeated `unknown format "uint64" ignored` messages in the lenient validator. Tool schemas still accept custom formats; only the noise is removed.

2. **[#5925 — fix(core): stop computer use driver when idle](https://github.com/QwenLM/qwen-code/pull/5925)**  
   Stops the `cua-driver` after 5 minutes of inactivity (configurable via `tools.computerUseDriverTimeout`). Directly fixes #5922.

3. **[#5923 — fix(core): preserve rewind parents after resume](https://github.com/QwenLM/qwen-code/pull/5923)**  
   Uses stored `parentUuid` from resumed records instead of inferring adjacency. Fixes #5920 history loss.

4. **[#5928 — feat(config): add todosDirectory for project-local todo persistence](https://github.com/QwenLM/qwen-code/pull/5928)**  
   Mirrors the existing `plansDirectory` pattern. When set (e.g. `.qwen/todos`), todos are written inside the project and become Git-trackable. Addresses #5836.

5. **[#5919 — feat(channels): register Telegram bot command menu](https://github.com/QwenLM/qwen-code/pull/5919)**  
   Registers a `/start` response and shared `/cancel` command via Telegram's `setMyCommands`. Only commands actually handled by the CLI are advertised. First step toward #5907.

6. **[#5921 — feat(cli): show scheduled task count in footer](https://github.com/QwenLM/qwen-code/pull/5921)**  
   Adds a footer pill `◎ 2 scheduled tasks` when cron tasks are active. Addresses #5823's visibility complaint.

7. **[#5913 — fix(desktop): validate credential cache source slugs](https://github.com/QwenLM/qwen-code/pull/5913)**  
   Routes credential-cache path construction through the existing validated source-directory helper. Part of the security hardening sweep (#5909, #5908).

8. **[#5911 — fix(desktop): normalize source slug validation errors](https://github.com/QwenLM/qwen-code/pull/5911)**  
   Returns structured validation results from `config_validate` instead of allowing uncaught failures. Follow-up to the CWE-22 fix in #5834.

9. **[#5890 — feat(loop): inject .qwen/loop.md task file at fire time](https://github.com/QwenLM/qwen-code/pull/5890)**  
   Long-running `/loop` tasks now read a durable `.qwen/loop.md` file for their prompt, so users can edit the task list without restating the work every tick. Addresses #5823.

10. **[#5927 — fix(core): improve cron tool search intents](https://github.com/QwenLM/qwen-code/pull/5927)**  
    Re-ranks `tool_search` results so queries about stopping / listing cron tasks surface `cron_delete` and `cron_list` above creation tools. Complements #5823.

## Feature Request Trends
- **Workspace-local persistence**: Multiple issues (#5836, #5838, #5839) ask for todos, plans, and memories to be stored inside the project directory (`.qwen/`) for Git-based cross-device and team sync. PR #5928 is already in review.
- **Background task visibility**: Users want the AI to be able to list, inspect, and cancel its own scheduled `/loop` and cron tasks (#5823). The footer pill (#5921) and `.qwen/loop.md` (#5890) address this.
- **Multiplayer / team memory**: Two PRs (#5886, #5888) introduce a team-memory tier inside the repo and a channel-resident multiplayer agent (`qwen tag`). This is a clear strategic direction toward collaborative development.
- **Telegram bot parity**: Issue #5907 tracks feature-complete Telegram command support, with PR #5919 registering the bot menu. Community interest is modest but consistent (3 comments).
- **Configurable timeouts**: #5838 and #5839 request user-adjustable timeouts for agent-spawned processes and tool execution, citing long build steps in CI-like workflows.

## Developer Pain Points
- **Spontaneous PowerShell spawning on Windows** (#5873) — every tool call creates a new `powershell.exe` that never terminates. Described as “100% reproducible” and causing OOM. The community reaction was unusually frustrated, indicating a Tier-1 Windows regression.
- **cua-driver resource leak** (#5922) — after `computer_use` tasks finish, the driver binary remains active with measurable CPU usage. Windows users are hit hardest. Fix (#5925) in review.
- **Model override on upgrade** (#5819) — auto-upgrades silently replace the user's configured model with a more expensive one, causing unexpected billing. Low trust in the upgrade path.
- **History loss after session resume** (#5920) — `/rewind` stores `parentUuid: null`, so on resume only the last turn is visible. Requires session restart to fully recover context.
- **Truncation-retry loops** (#5756) — the arbitrary 8K output cap causes large file writes to truncate, then the agent retries indefinitely. Core usability blocker for large-codebase edits.
- **Zombie child processes on Linux** (#5083) — unreaped zombies cause TUI freezes. The bug has been open since June 13 with no clear resolution path.

</details>

<details>
<summary><strong>DeepSeek TUI</strong> — <a href="https://github.com/Hmbown/DeepSeek-TUI">Hmbown/DeepSeek-TUI</a></summary>

# DeepSeek TUI Community Digest — 2026-06-27

**Note:** The repository has been rebranded from *DeepSeek-TUI* to **CodeWhale**. All references below reflect the current project name.

---

## 1. Today's Highlights

The community saw a burst of CI and documentation cleanup activity, with four PRs merged to fix stale file paths in contribution guides and harden the TUI's Unicode/CJK display math. A critical installation bug where the `install.sh` endpoint returned an HTML page instead of a shell script was reported and closed. The Moraine memory backend integration reached a milestone, with the legacy push/inject system now gated behind a config fallback flag, and the new Moraine MCP recall tools are wired as the default agent memory source.

---

## 2. Releases

*No new releases in the last 24 hours.*

---

## 3. Hot Issues

1. **[#3568 - Plan and agent mode mixed up yet again](https://github.com/Hmbown/CodeWhale/issues/3568)**  
   A recurring language‑mode confusion bug where the `plan` mode still exhibits agent‑like file‑modification behavior. The reporter attached a chat export showing the AI ignoring the mode switch. Community reaction: 1 👍, 6 comments expressing frustration. This is a high‑priority UX regression that undermines user trust in mode semantics.

2. **[#2870 - EPIC: staged command-boundary refactor for #2791](https://github.com/Hmbown/CodeWhale/issues/2870)**  
   A tracking epic for breaking a large command‑boundary refactor into mergeable layers, with a reference PR (#2851). No new comments today, but it remains the structural backbone for upcoming CLI changes. Low community engagement but high architectural importance.

3. **[#3495 - Adopt Moraine as CodeWhale's memory backend](https://github.com/Hmbown/CodeWhale/issues/3495)**  
   A feature proposal to replace the legacy memory system with Moraine, an Apache‑2.0 agent‑memory backend that ingests sessions losslessly and exposes MCP recall tools (`search`, `get_session`, etc.). Updated yesterday; 4 comments. This is the leading memory modernisation effort.

4. **[#3582 - install.sh endpoint returns HTML instead of shell script](https://github.com/Hmbown/CodeWhale/issues/3582)**  
   A critical blocker for new users: the recommended `curl ... install.sh | sh` command fails because the endpoint serves a Next.js HTML page. Closed with 4 comments; the fix likely involved routing or CDN configuration. High impact on onboarding.

5. **[#3657 - Editor freezes and crashes CodeWhale](https://github.com/Hmbown/CodeWhale/issues/3657)**  
   The TUI editor (opened via `Ctrl-O` in draft mode) hard‑freezes the entire application, requiring a process kill. 3 comments from users reproducing the issue. A release‑blocking stability bug for anyone relying on in‑app editing.

6. **[#2967 - Telegram bridge streaming & resilience hardening](https://github.com/Hmbown/CodeWhale/issues/2967)**  
   An incremental workstream to add progress‑edit, MarkdownV2, chunking, offset/replay safety, and backoff to the Telegram bridge. Updated today with 1 comment. Important for production‑grade multi‑platform support.

7. **[#1490 - app-server --stdio does not stream response_delta output](https://github.com/Hmbown/CodeWhale/issues/1490)**  
   A long‑standing bug (observed on v0.8.14) where `thread/message` returns `accepted` but never streams model text to stdout. Closed with 0 comments; likely fixed in a later release. Affects third‑party integrations depending on SSE‑style output.

8. **[#3401 - v0.8.66 Hotbar end-to-end QA matrix](https://github.com/Hmbown/CodeWhale/issues/3401)**  
   A release gate issue that created a QA matrix covering config, key input, sidebar, MCP/tools, skills, plugins, and setup wizard. Closed with 0 comments—used as a tracking issue for the QA pass. Shows the maintainer's discipline in release process.

9. **[#2958 - Audit Agent/Yolo/Plan prompt deltas for clarity and token cost](https://github.com/Hmbown/CodeWhale/issues/2958)**  
   A documentation/enhancement issue to make mode‑specific prompt deltas small and explicit while reducing duplicated policy text. Closed with 0 comments. This affects every user's token bill and model behavior clarity.

10. **[#3585 (closed PR) - Add OpenModel provider support](https://github.com/Hmbown/CodeWhale/issues/3585)**  
    Although a PR, the issue body describes adding OpenModel as a first‑class Anthropic Messages provider with `deepseek-v4-flash` as the default route. Merged today. Broader provider choice is a frequently requested feature.

---

## 4. Key PR Progress

1. **[#3689 - fix(telegram): bound polling conflict retries](https://github.com/Hmbown/CodeWhale/pull/3689)**  
   Replaces a flat 10‑second retry with a bounded 15/25/35/45/55s ladder for Telegram `getUpdates` conflicts, plus tests. *cyq1017* — prevents token‑ownership loops when multiple bridges run.

2. **[#3688 - refactor(runtime-api): extract session handlers](https://github.com/Hmbown/CodeWhale/pull/3688)**  
   Moves session request/response types and handlers out of `runtime_api.rs` into a dedicated module, keeping route registration centralized. *cyq1017* — improves maintainability of the HTTP API layer.

3. **[#3685 / #3687 - Add skills inspect command](https://github.com/Hmbown/CodeWhale/pull/3685) + [harvested](https://github.com/Hmbown/CodeWhale/pull/3687)**  
   Adds `/skills inspect` showing discovery mode, workspace, configured directories, and available skill count. *noaft* → harvested by *Hmbown* — gives developers a diagnostics tool for local skill discovery.

4. **[#3585 / #3677 - Add OpenModel provider support](https://github.com/Hmbown/CodeWhale/pull/3585) + [harvested](https://github.com/Hmbown/CodeWhale/pull/3677)**  
   Integrates OpenModel across the shared provider registry, CLI, TUI config, and provider picker. *noaft* → harvested by *Hmbown* — expands model choice beyond the default setup.

5. **[#3621 - Fix provider links docs fallback](https://github.com/Hmbown/CodeWhale/pull/3621)**  
   Updates the stale `codewhale.dev/docs/providers` URL and adds a Qianfan‑specific link. *noaft* — fixes broken documentation navigation.

6. **[#3645 - Guard exec against misplaced global flags](https://github.com/Hmbown/CodeWhale/pull/3645)**  
   Detects when users place global runtime flags after `codewhale exec` and gives a clear error instead of treating them as prompt text. *noaft* — much‑needed UX hardening for the CLI.

7. **[#3575 / #3681 - Wire Moraine MCP as recall tool source](https://github.com/Hmbown/CodeWhale/pull/3575) + [finish fallback gates](https://github.com/Hmbown/CodeWhale/pull/3681)**  
   Adds Moraine MCP (stdio) recall tools and a `moraine_fallback` config gate to deprecate the legacy push/inject system. *pkeging* → harvested by *Hmbown* — a major milestone in memory architecture.

8. **[#3682 / #3683 - Fix zero‑width char display width](https://github.com/Hmbown/CodeWhale/pull/3682) + [harvested](https://github.com/Hmbown/CodeWhale/pull/3683)**  
   Removes the `.max(1)` that forced zero‑width characters (e.g., joiners, ZWJ sequences) to occupy one column. *findshan* → harvested by *Hmbown* — fixes Unicode/CJK rendering bugs.

9. **[#3640 / #3678 - Add WeCom Bridge deployment guide](https://github.com/Hmbown/CodeWhale/pull/3640) + [harvested](https://github.com/Hmbown/CodeWhale/pull/3678)**  
   Adds `DEPLOYMENT.md` and `SECURITY.md` sections for the WeCom (WeChat Work) bridge. *pkeging* → harvested by *Hmbown* — enables enterprise messaging integration.

10. **[#3607 - Reactivate stale issue cleanup](https://github.com/Hmbown/CodeWhale/pull/3607)**  
    Creates missing stale‑policy labels (`needs-info`, `stale`, `keep-open`, `pinned`) and configures the workflow to age out `bug` + `needs-info` issues unless exempt. *Hmbown* — housekeeping that keeps the issue tracker maintainable.

---

## 5. Feature Request Trends

- **Multi‑platform messaging bridges** (Telegram, WeCom) are receiving active resilience hardening and deployment documentation. The trend is toward production‑grade, long‑running bridge instances with retry backoff and conflict detection.
- **Memory system modernisation** is the largest architectural undertaking: adopting Moraine as a lossless session store with MCP recall tools, while deprecating the legacy push/inject pattern.
- **Provider extensibility** continues: OpenModel was added as a first‑class provider this week, joining Qianfan and others. Users want freedom to route through alternative Anthropic‑protocol endpoints.
- **Unicode/CJK/terminal rendering fixes** (e.g., zero‑width characters, display‑width math) indicate growing adoption among East Asian users who rely on proper character‑width calculation in the TUI.
- **Skills discovery diagnostics** (`/skills inspect`) responded to community demand for visibility into how local skills are found and loaded.

---

## 6. Developer Pain Points

- **Plan/Agent mode confusion persists.** Issue #3568 is the latest recurrence of the AI ignoring mode switches. Users report that even in `plan` mode, the model attempts file modifications, defeating the purpose of the mode distinction.
- **Editor stability is fragile.** Issue #3657 shows the in‑app editor can hard‑freeze the entire TUI, forcing a process kill. This is a critical blocker for everyday drafting.
- **Installation friction remains high.** Issue #3582 (install.sh serving HTML) broke onboarding for any new user running the recommended command. While closed, it indicates a fragile deployment pipeline.
- **Streaming reliability is uneven.** Issue #1490 (app-server --stdio not streaming) has been open since May and affects anyone building third‑party integrations on top of the server transport.
- **Documentation drift is common.** Multiple PRs this week (e.g., #3621, #3684) had to fix stale file paths, outdated URLs, or missing provider documentation. Contributors are hitting dead links during onboarding.

</details>

---
*This digest is auto-generated by [agents-radar](https://github.com/Lux0206/agents-radar).*