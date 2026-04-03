# HEARTBEAT.md — Elkin Periodic Checks
# Agent: Elkin 🔱 | Updated: 2026-04-03

---

## Active Checks

Run these on every heartbeat poll.
Batch all checks into one pass — do not make separate API calls per check.

### 1. System Health
- CPU usage — alert if >80%
- RAM usage — alert if >85%
- Disk usage — alert if >80%
- Gateway process status — alert if not running on port 18789

### 2. Git Brain Status
- Run: git -C ~/.openclaw/workspace status
- Alert if uncommitted changes older than 1 session
- Alert if last push was >24 hours ago

### 3. Goals Review
- Read memory/goals.md
- Flag any CRITICAL/HIGH goals with no progress in threshold window
- Flag any blocked goals with no unblock criteria defined

### 4. SSH Monitor
- Check for new login IPs not in known list
- Check for 3+ failed login attempts
- Alert immediately on any anomaly

### 5. Capability Registry
- Check .openclaw/capability_registry.json last_updated
- If >72 hours since last harvester run — queue harvester execution

---

## Response Rules

- Nothing to report → reply HEARTBEAT_OK
- Finding worth noting → send Telegram message, then HEARTBEAT_OK
- Critical finding → send 🚨 Telegram alert immediately, do not reply OK until resolved

---

## Quiet Hours

23:00 — 07:00 AEST — suppress non-critical alerts.
CRITICAL and SECURITY alerts override quiet hours always.

---

## Heartbeat State Intervals

- IDLE: every 30 minutes
- ACTIVE: every 5 minutes
- CRITICAL: every 1 minute
