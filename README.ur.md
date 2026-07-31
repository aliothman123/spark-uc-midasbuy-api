# Midasbuy API — PUBG Mobile UC | Spark UC Bot

> **آزاد developer API** — Midasbuy-style UC redeem، code check، player lookup، stock automation۔  
> Midasbuy، Krafton، Tencent سے وابستہ نہیں۔

[![Telegram](https://img.shields.io/badge/Telegram-@SparkUCBot-26A5E4?style=flat&logo=telegram)](https://telegram.me/SparkUCBot)
[![Docs](https://img.shields.io/badge/Docs-api.pubgredeemerbot.com-2dd4bf?style=flat)](https://api.pubgredeemerbot.com/docs)

**زبانیں:** [EN](./README.md) · [AR](./README.ar.md) · [RU](./README.ru.md) · [UR](./README.ur.md) · [FA](./README.fa.md) · [TR](./README.tr.md) · [HI](./README.hi.md) · [中文](./README.zh-CN.md)

---

## تعارف

**Spark UC Bot** کا HTTP API: `https://api.pubgredeemerbot.com` — **PUBG Mobile UC / Midasbuy** codes [@SparkUCBot](https://telegram.me/SparkUCBot) جیسا ہی flow۔

- UC redeem — `POST /v1/jobs/manual-redeem`
- Code check (10 تک) — `POST /v1/jobs/check-code`
- Player lookup — `GET /v1/player/lookup`
- Stock batch — `POST /v1/jobs/stock-redeem`

**Resellers**، panels، automation کے لیے۔

---

## لنکس

| | URL |
|---|-----|
| API | https://api.pubgredeemerbot.com |
| Docs | https://api.pubgredeemerbot.com/docs |
| Swagger | https://api.pubgredeemerbot.com/swagger |
| Landing | https://www.pubgredeemerbot.com/ur/midasbuy-api.html |
| Bot | https://telegram.me/SparkUCBot |
| Support | https://telegram.me/sparkuc_support |

---

## Authentication

```http
X-API-Key: YOUR_API_KEY
```

**@SparkUCBot** → plan → HTTP API add-on (15 USDT / 30 days)

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

Midasbuy API · PUBG Mobile UC API · Midasbuy redeem API · UC code check · pubgredeemerbot API · SparkUCBot · PUBG UC reseller API
