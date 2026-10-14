# FinAgent

Personal/family financial planning — a daily brief to your phone plus dashboard sensors.
Plan-only; all money math is local and the LLM only sees computed aggregates.

This is the **public add-on manifest only**. The source (code + your private config) lives in
the private repo `twimprine/FinAgent`; its CI builds the image this add-on pulls.

## Options
| Option | Meaning |
|--------|---------|
| `anthropic_api_key` | Anthropic key for the Opus/Haiku drafting models. |
| `recipients` | Notify service suffixes, e.g. `mobile_app_your_phone`. |
| `config_files` | Optional, masked: a YAML/JSON mapping of filename → file content, validated and written to `config_dir` each run (allowed: people, bills, budget, debts, accounts, notifications, categories, goal, alerts `.yaml`). Clear it to stop pushing. |
| `config_dir` | Directory of the hand-editable YAML (default `/config/finagent`). |
| `year` | Plan year; `0` = current year. |

## Setup
1. Put your YAML data at `/config/finagent/*.yaml` (from the source repo's `config/example/`).
2. Install, set `anthropic_api_key` + `recipients`, and Start.

Each start runs once (brief + sensors). Trigger daily with a `hassio.addon_start` automation.
