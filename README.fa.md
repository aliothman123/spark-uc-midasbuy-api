# Midasbuy API — UC PUBG Mobile | Spark UC Bot HTTP API

> **API مستقل توسعه‌دهندگان** برای redeem کدهای UC به سبک Midasbuy، بررسی voucher، lookup بازیکن و اتوماسیون انبار.  
> وابسته به Midasbuy، Krafton یا Tencent **نیست**.

[![Telegram](https://img.shields.io/badge/Telegram-@SparkUCBot-26A5E4?style=flat&logo=telegram)](https://telegram.me/SparkUCBot)
[![Docs](https://img.shields.io/badge/Docs-api.pubgredeemerbot.com-2dd4bf?style=flat)](https://api.pubgredeemerbot.com/docs)

**زبان‌ها:** [EN](./README.md) · [AR](./README.ar.md) · [RU](./README.ru.md) · [UR](./README.ur.md) · [FA](./README.fa.md) · [TR](./README.tr.md) · [HI](./README.hi.md) · [中文](./README.zh-CN.md)

---

## معرفی

**Spark UC Bot** — REST API روی `https://api.pubgredeemerbot.com` برای کدهای **UC PUBG Mobile / Midasbuy** — همان pipeline ربات [@SparkUCBot](https://telegram.me/SparkUCBot).

- فعال‌سازی UC — `POST /v1/jobs/manual-redeem`
- بررسی کد (۱–۱۰) — `POST /v1/jobs/check-code`
- lookup بازیکن — `GET /v1/player/lookup`
- redeem انبوه از stock — `POST /v1/jobs/stock-redeem`

برای **نمایندگان**، **پنل‌ها** و **اتوماسیون**.

---

## لینک‌ها

| منبع | URL |
|------|-----|
| API | https://api.pubgredeemerbot.com |
| مستندات | https://api.pubgredeemerbot.com/docs |
| Swagger | https://api.pubgredeemerbot.com/swagger |
| Landing | https://www.pubgredeemerbot.com/fa/midasbuy-api.html |
| ربات | https://telegram.me/SparkUCBot |
| پشتیبانی | https://telegram.me/sparkuc_support |

---

## احراز هویت

```http
X-API-Key: YOUR_API_KEY
```

کلید در **@SparkUCBot** → پلن فعال → **HTTP API add-on** (۱۵ USDT / ۳۰ روز).

---

## مثال سریع

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/manual-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"player_id":"5123456789","codes":["XXXX-XXXX-XXXX-XXXX"]}'
```

جزئیات: [docs/QUICKSTART.md](./docs/QUICKSTART.md) · [docs/FAQ.md](./docs/FAQ.md)

---

## کلمات کلیدی

Midasbuy API · PUBG Mobile UC API · Midasbuy redeem API · بررسی کد Midasbuy · pubgredeemerbot API · SparkUCBot API · فعال‌سازی UC
