# 🎮 Brown Dust 2 Automation

[![ClawHub](https://img.shields.io/badge/ClawHub-brown--dust--2-blue)](https://clawhub.ai)
[![Python 3.9+](https://img.shields.io/badge/python-3.9%2B-brightgreen)](https://python.org)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-zero-orange)]()
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)

Brown Dust 2 全自动签到 + 兑换码一键兑换 for [OpenClaw](https://openclaw.ai).

## Features

### Gift Code Redemption (API-based, no browser needed)

- Auto-scrape latest codes from [BD2Pulse](https://thebd2pulse.com)
- One-click redeem all codes via official API
- Reports: new success / already redeemed / expired

### Daily Web Shop Sign-in (browser-based)

- Auto sign-in to the official web shop
- Google OAuth login support
- Calendar check-in for daily rewards

## Install

```bash
clawhub install brown-dust-2
```

Or clone:

```bash
git clone https://github.com/XiaoYiWeio/brown-dust-2.git ~/.openclaw/workspace/skills/brown-dust-2
```

## Setup

### Gift Code (one-time)

Save your in-game nickname:

```bash
python3 scripts/redeem.py --save-nickname "YourNickname"
```

### Daily Sign-in (one-time)

Log in to Google in the OpenClaw browser.

## Usage

### In OpenClaw

- "BD2兑换码" — auto-redeem all latest codes
- "BD2签到" — daily web shop sign-in
- "BD2全签" — both

### CLI

```bash
# Auto-fetch + redeem all codes
python3 scripts/redeem.py

# List available codes without redeeming
python3 scripts/redeem.py --list

# Manually specify codes
python3 scripts/redeem.py --code BD21000BOOST,BD2RADIOMAGICAL

# JSON output
python3 scripts/redeem.py --json
```

## Architecture

```
brown-dust-2/
├── SKILL.md          # OpenClaw skill definition
├── persona.md        # Agent interaction guide
├── README.md
└── scripts/
    └── redeem.py     # Gift code scraper + redeemer (API-based)
```

## Design

- **Zero dependencies** — pure Python 3 standard library
- **API-based redemption** — no browser needed for gift codes
- **Auto-scrape** — always gets the latest codes from BD2Pulse
- **Idempotent** — safe to run multiple times (already-redeemed codes are skipped)

## License

MIT
