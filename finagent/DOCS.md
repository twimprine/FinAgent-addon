# FinAgent

Personal/family financial planning — a daily brief to your phone plus dashboard sensors.
Plan-only; all money math is local and the LLM only sees computed aggregates.

This is the **public add-on manifest only**. The source (code + your private config) lives in
the private repo `twimprine/FinAgent`; its CI builds the image this add-on pulls.

## Options
| Option | Meaning |
|--------|---------|
| `anthropic_api_key` | Anthropic key for the Opus/Haiku drafting models. |
| `recipients` | Notify service suffixes, e.g. `mobile_app_chaosmonkey_nomap`. |
| `config_dir` | Directory of the hand-editable YAML (default `/config/finagent`). |
| `year` | Plan year; `0` = current year. |

## Setup
1. Put your YAML data at `/config/finagent/*.yaml` (from the source repo's `config/example/`).
2. Install, set `anthropic_api_key` + `recipients`, and Start.

Each start runs once (brief + sensors). Trigger daily with a `hassio.addon_start` automation.
