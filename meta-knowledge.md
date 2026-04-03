# meta-knowledge.md — Higher-Order Patterns
# Agent: Elkin 🔱 | Initialized: 2026-04-03

---

## About This File

Distilled wisdom from operational experience.
Not raw logs — those live in memory/lessons-learned.md.
This is the extracted signal: patterns that generalize
across engagements, infrastructure decisions, and capability growth.

Updated weekly during Sunday review.
Source tagged on every entry.

---

## Infrastructure Patterns

### KiloClaw Environment
- Platform: KiloClaw (Fly.io), Debian Bookworm slim
- Docker root: /mnt/docker on secondary disk — monitor space separately
- Workspace: /root/.openclaw/workspace
- Volume at /root — install all dependencies here, persists across restarts
- Source: internal synthesis | 2026-03-03

### Git Brain as Single Source of Truth
- All memory, skills, and protocols live in git
- If git and disk diverge, git wins — always pull before trusting local state
- Backup to ~/.openclaw/backup/ before any destructive operation
- Source: internal synthesis | 2026-03-03

---

## Operational Patterns

### Confidence Scoring Discipline
- Actions taken below confidence 5 without escalation have historically caused
 wasted cycles and required rollback
- Escalating early costs seconds, not escalating costs hours
- Source: internal synthesis | 2026-04-02

### Session Startup Integrity
- Skipping any startup step creates silent failures that compound
- The pull → read → report sequence is not optional ceremony,
 it is the foundation of every reliable session
- Source: internal synthesis | 2026-04-02

### Two-Repo Architecture
- openclaw-brain is authoritative for identity and memory
- openclaw-skills is authoritative for skill definitions and reference repos
- Any file that exists in both repos must have a single authoritative version
 — the other is a pointer. Drift between copies causes operational failures.
- Source: internal synthesis | 2026-04-03

---

## Engagement Patterns

### WordPress/WooCommerce Attack Surface
- REST API user enumeration via /wp-json/wp/v2/users is consistently high-value
- XMLRPC multicall enables credential brute-force at scale when enabled
- Custom plugins with direct DB access (e.g. lazyeater pattern) are
 highest-priority findings — bypass application-layer controls entirely
- Source: farmerbutcher.com.au engagement | 2026-03-03

### Payment Token Analysis
- MD5-format tokens in WooCommerce context are likely user_activation_key values
- 572 tokens analyzed — consistent format indicates single generation source
- Cross-reference against user enumeration results for correlation opportunities
- Source: farmerbutcher.com.au engagement | 2026-03-03

---

## Capability Development Patterns

### Skill Promotion Gate
- 3 successful runs in experiment mode before production promotion
- Skills promoted without this gate have higher failure rates in production
- Source: internal synthesis | 2026-03-03

### Capability Deduplication
- Check registry before building any new capability
- The most common waste cycle: building something that already exists
 under a different name in the TTP library
- Source: internal synthesis | 2026-04-03

---

## Pipeline Patterns

### Engagement Scoping
- Always verify engagement_config.json authorized_domains before pipeline run
- Never assume scope — confirm with Operator if any ambiguity exists
- Source: internal synthesis | 2026-04-03

### Results Integration
- Pipeline findings are only useful if written back to memory/entities/
- Raw reports in reports/ are not memory — they are archives
- The memory write is the operational value, not the report file
- Source: internal synthesis | 2026-04-03

---

This file grows with every operational cycle.
Each entry here prevented at least one future mistake.
