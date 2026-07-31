# Midasbuy API — PUBG Mobile UC | Spark UC Bot HTTP API

> **Bağımsız geliştirici API** — Midasbuy tarzı UC redeem, kod kontrolü, oyuncu lookup, stok otomasyonu.  
> Midasbuy, Krafton veya Tencent ile **ilişkili değildir**.

[![Telegram](https://img.shields.io/badge/Telegram-@SparkUCBot-26A5E4?style=flat&logo=telegram)](https://telegram.me/SparkUCBot)
[![Docs](https://img.shields.io/badge/Docs-api.pubgredeemerbot.com-2dd4bf?style=flat)](https://api.pubgredeemerbot.com/docs)

**Diller:** [EN](./README.md) · [AR](./README.ar.md) · [RU](./README.ru.md) · [UR](./README.ur.md) · [FA](./README.fa.md) · [TR](./README.tr.md) · [HI](./README.hi.md) · [中文](./README.zh-CN.md)

---

## Nedir?

**Spark UC Bot** — `https://api.pubgredeemerbot.com` üzerinde **PUBG Mobile UC / Midasbuy** kodları için HTTP REST API. Telegram botu [@SparkUCBot](https://telegram.me/SparkUCBot) ile aynı pipeline.

- UC redeem — `POST /v1/jobs/manual-redeem`
- Kod kontrolü (10'a kadar) — `POST /v1/jobs/check-code`
- Oyuncu lookup — `GET /v1/player/lookup`
- Stok toplu redeem — `POST /v1/jobs/stock-redeem`

**Bayiler**, paneller ve otomasyon için.

---

## Bağlantılar

| | URL |
|---|-----|
| API | https://api.pubgredeemerbot.com |
| Dokümantasyon | https://api.pubgredeemerbot.com/docs |
| Swagger | https://api.pubgredeemerbot.com/swagger |
| Landing | https://www.pubgredeemerbot.com/tr/midasbuy-api.html |
| Bot | https://telegram.me/SparkUCBot |
| Destek | https://telegram.me/sparkuc_support |

---

## Kimlik doğrulama

```http
X-API-Key: YOUR_API_KEY
```

**@SparkUCBot** → aktif plan → **HTTP API add-on** (15 USDT / 30 gün).

---

## Hızlı örnek

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/manual-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"player_id":"5123456789","codes":["XXXX-XXXX-XXXX-XXXX"]}'
```

[docs/QUICKSTART.md](./docs/QUICKSTART.md) · [docs/FAQ.md](./docs/FAQ.md)

---

## Anahtar kelimeler

Midasbuy API · PUBG Mobile UC API · Midasbuy redeem API · kod kontrolü · pubgredeemerbot API · SparkUCBot API · UC otomasyon
