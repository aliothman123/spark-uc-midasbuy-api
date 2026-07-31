# Midasbuy API — PUBG Mobile UC | Spark UC Bot HTTP API

> **Independent developer API** for Midasbuy-style UC redeem, code check, player lookup, stock automation.  
> Midasbuy, Krafton, या Tencent से **संबद्ध नहीं**।

[![Telegram](https://img.shields.io/badge/Telegram-@SparkUCBot-26A5E4?style=flat&logo=telegram)](https://telegram.me/SparkUCBot)
[![Docs](https://img.shields.io/badge/Docs-api.pubgredeemerbot.com-2dd4bf?style=flat)](https://api.pubgredeemerbot.com/docs)

**Languages:** [EN](./README.md) · [AR](./README.ar.md) · [RU](./README.ru.md) · [UR](./README.ur.md) · [FA](./README.fa.md) · [TR](./README.tr.md) · [HI](./README.hi.md) · [中文](./README.zh-CN.md)

---

## परिचय

**Spark UC Bot** — `https://api.pubgredeemerbot.com` पर **PUBG Mobile UC / Midasbuy** codes के लिए HTTP REST API। Telegram bot [@SparkUCBot](https://telegram.me/SparkUCBot) जैसा pipeline।

- UC redeem — `POST /v1/jobs/manual-redeem`
- Code check (1–10) — `POST /v1/jobs/check-code`
- Player lookup — `GET /v1/player/lookup`
- Stock batch redeem — `POST /v1/jobs/stock-redeem`

**Resellers**, panels, automation के लिए।

---

## Links

| | URL |
|---|-----|
| API | https://api.pubgredeemerbot.com |
| Docs | https://api.pubgredeemerbot.com/docs |
| Swagger | https://api.pubgredeemerbot.com/swagger |
| Landing | https://www.pubgredeemerbot.com/hi/midasbuy-api.html |
| Bot | https://telegram.me/SparkUCBot |
| Support | https://telegram.me/sparkuc_support |

---

## Authentication

```http
X-API-Key: YOUR_API_KEY
```

**@SparkUCBot** → active plan → **HTTP API add-on** (15 USDT / 30 days)

---

## Quick example

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/manual-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"player_id":"5123456789","codes":["XXXX-XXXX-XXXX-XXXX"]}'
```

[docs/QUICKSTART.md](./docs/QUICKSTART.md) · [docs/FAQ.md](./docs/FAQ.md)

---

## Keywords

Midasbuy API · PUBG Mobile UC API · UC redeem API · code check API · pubgredeemerbot API · SparkUCBot · PUBG UC reseller
