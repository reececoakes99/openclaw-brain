# TOOLS.md - Environment Specifics

Skills define how tools work. This file is Elkin's infrastructure cheat sheet —
specifics unique to this deployment that don't belong in shared skill files.

## KiloClaw Environment

* **Platform:** KiloClaw (Fly.io isolated single-tenant machine)
* **OS:** Debian Bookworm (slim)
* **Volume mount:** /root — backed by snapshots, install dependencies here
* **Workspace:** /root/.openclaw/workspace
* **Kilo CLI:** kilo — interactive: kilo / autonomous: kilo run --auto "task"
* **Config:** /root/.config/kilo/opencode.json
* **Do not modify:** /root/.kilo

## Gateway

* **Port:** 18789 — loopback only, never expose to public internet
* **Process manager:** supervisor

## Networking

* **Tailscale IP:** 100.84.143.47

## Telegram

* **Bot handle:** @Elkinlochbot
* **Operator chat ID:** 8069069638
* **Pending alerts path:** ~/.openclaw/alerts/pending/ — retry every 5 min if unreachable

## Git Identity

* **Username:** reececoakes99
* **Email:** reececoakes99@users.noreply.github.com

## Reference Repositories (submodules)

* **PayloadsAllTheThings:** openclaw-skills/repos/PayloadsAllTheThings/
* **SecLists:** openclaw-skills/repos/SecLists/

## API

* **Primary model:** anthropic/claude-sonnet-4-6
* **Fallback 1:** openrouter/anthropic/claude-sonnet-4-6
* **Fallback 2:** openrouter/meta-llama/llama-3.3-70b-instruct
* **Spend cap:** $10 per 24-hour period — hard limit

## Pipeline

* **Repo:** openclaw-pipeline
* **Invoke:** python master_pipeline.py -t <target> --config engagement_config.json
* **Env vars required:** GITHUB_PAT, TELEGRAM_BOT_TOKEN

## Stale Connections Removed

* Previous OpenClaw instance disconnected — no longer active on this repo
