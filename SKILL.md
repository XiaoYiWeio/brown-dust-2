---
name: brown-dust-2
description: "Brown Dust 2 自动化工具 — 每日签到领奖 + 全自动兑换码兑换（从BD2Pulse抓取最新码，一键全部兑换）。触发词：BD2、棕色尘埃、brown dust、签到、兑换码、redeem、gift code。"
version: 1.0.0
---

# Brown Dust 2 Automation

棕色尘埃2 自动签到 + 兑换码全自动兑换。

## 触发规则

| 模式 | 示例 |
|------|------|
| 包含 `BD2` / `棕色尘埃` / `brown dust` | "BD2签到", "棕色尘埃兑换码" |
| 包含 `签到` + 游戏相关 | "帮我BD2签到" |
| 包含 `兑换码` / `redeem` / `gift code` | "BD2兑换码", "redeem BD2 codes" |

## 两大功能

### 功能 1 — 兑换码自动兑换（纯 API，无需浏览器）

自动从 BD2Pulse 抓取最新兑换码 → 调用官方 API 一键兑换。

```bash
# 首次使用，保存游戏昵称
python3 {baseDir}/scripts/redeem.py --save-nickname "你的游戏昵称"

# 自动抓取 + 全部兑换
python3 {baseDir}/scripts/redeem.py

# 只看有哪些码
python3 {baseDir}/scripts/redeem.py --list

# 手动指定码
python3 {baseDir}/scripts/redeem.py --code BD21000BOOST,BD2RADIOMAGICAL
```

### 功能 2 — Web Shop 每日签到（需浏览器）

签到页面：https://webshop.browndust2.global/CT/events/attend-event/

需要 Google 账号登录，通过 browser 工具操作。详见 `persona.md`。

## 前置要求

| 功能 | 需要什么 |
|------|---------|
| 兑换码 | 游戏内昵称（保存一次即可） |
| 每日签到 | OpenClaw 浏览器中登录 Google 账号 |
