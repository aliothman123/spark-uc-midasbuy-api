# Midasbuy API لشدات PUBG Mobile — Spark UC Bot HTTP API

> **API مستقل للمطورين** لتفعيل أكواد UC بنمط Midasbuy، **فحص القسائم**، **lookup اللاعب**، و**أتمتة المخزون**.  
> غير تابع لـ Midasbuy أو Krafton أو Tencent.

[![بوت تلجرام](https://img.shields.io/badge/Telegram-@SparkUCBot-26A5E4?style=flat&logo=telegram&logoColor=white)](https://telegram.me/SparkUCBot)
[![توثيق API](https://img.shields.io/badge/Docs-api.pubgredeemerbot.com-2dd4bf?style=flat)](https://api.pubgredeemerbot.com/docs)
[![Swagger](https://img.shields.io/badge/Swagger-OpenAPI-85EA2D?style=flat)](https://api.pubgredeemerbot.com/swagger)
[![الموقع](https://img.shields.io/badge/صفحة%20Midasbuy-pubgredeemerbot.com-blue?style=flat)](https://www.pubgredeemerbot.com/ar/midasbuy-api.html)

**اللغات:** [English](./README.md) · [العربية](./README.ar.md) · [Русский](./README.ru.md) · [اردو](./README.ur.md) · [فارسی](./README.fa.md) · [Türkçe](./README.tr.md) · [हिन्दी](./README.hi.md) · [中文](./README.zh-CN.md)

![بوت Spark UC — Midasbuy API لشحن شدات ببجي](./docs/images/spark-uc-midasbuy-api-cover.png)

---

## ما هذا؟

**Spark UC Bot** يوفّر **HTTP REST API** على `https://api.pubgredeemerbot.com` لمعالجة **أكواد شدات PUBG Mobile بنمط Midasbuy** — نفس مسار التفعيل في بوت تلجرام [@SparkUCBot](https://telegram.me/SparkUCBot).

يمكنك:

- **تفعيل أكواد UC** على Player ID (`POST /v1/jobs/manual-redeem`)
- **فحص / التحقق من القسائم** قبل البيع أو التفعيل (`POST /v1/jobs/check-code` — حتى 10 أكواد)
- **lookup اسم اللاعب والمنطقة** (`GET /v1/player/lookup`)
- **تفعيل دفعي من المخزون** (`POST /v1/jobs/stock-redeem`)
- قراءة **الحساب، quota، السجل، ملخص المخزون**

مناسب لـ **لوحات الوسطاء**، **المتاجر**، **السكربتات**، و**أنظمة SaaS**.

### لقطات الشاشة

![واجهة HTTP API لتفعيل شدات ببجي — طلب manual-redeem](./docs/images/pubg-uc-redeem-api.png)

![فحص أكواد Midasbuy عبر API — صالح / مستخدم / منتهي](./docs/images/midasbuy-code-check-api.png)

![فحص معرف لاعب ببجي موبايل قبل شحن الشدات](./docs/images/pubg-player-id-lookup.png)

---

## روابط سريعة

| المورد | الرابط |
|--------|--------|
| **قاعدة API** | https://api.pubgredeemerbot.com |
| **توثيق HTML** | https://api.pubgredeemerbot.com/docs |
| **Swagger** | https://api.pubgredeemerbot.com/swagger |
| **OpenAPI JSON** | https://api.pubgredeemerbot.com/openapi.json |
| **Health** | https://api.pubgredeemerbot.com/health |
| **صفحة Midasbuy** (8 لغات) | https://www.pubgredeemerbot.com/ar/midasbuy-api.html |
| **البوت** | https://telegram.me/SparkUCBot |
| **الدعم** | https://telegram.me/sparkuc_support |

---

## إخلاء مسؤولية

**Spark UC Bot** (pubgredeemerbot.com) — خدمة **مستقلة**. لسنا Midasbuy أو Krafton أو Tencent أو PUBG Mobile.

---

## المصادقة

كل مسارات `/v1/*` و `/api/v1/*` تحتاج:

```http
X-API-Key: YOUR_API_KEY
```

احصل على المفتاح من **@SparkUCBot** → اشتراك نشط → **HTTP API add-on** → انسخ المفتاح.

**المتطلبات:** باقة نشطة + **إضافة API** (15 USDT / 30 يوم). تجربة مجانية ممكنة بطلب من الإدارة.

---

## Endpoints الأساسية

| Method | Path | الوصف |
|--------|------|--------|
| `GET` | `/health` | فحص عام |
| `GET` | `/v1/me` | ملخص الحساب |
| `GET` | `/v1/quota` | الحدود والاستخدام |
| `GET` | `/v1/player/lookup` | lookup اللاعب (متزامن) |
| `POST` | `/v1/jobs/manual-redeem` | تفعيل UC (job غير متزامن) |
| `POST` | `/v1/jobs/check-code` | فحص الكود (job) |
| `POST` | `/v1/jobs/stock-redeem` | تفعيل من المخزون |
| `GET` | `/v1/jobs/{job_id}` | حالة الـ job |
| `GET` | `/v1/history` | سجل التفعيل |
| `GET` | `/v1/stock/summary` | ملخص المخزون |

التفاصيل: [docs/ENDPOINTS.md](./docs/ENDPOINTS.md)

---

## الدمج في 3 خطوات

### 1) اشتراك + API add-on

@SparkUCBot → شحن USDT → باقة → HTTP API add-on → نسخ المفتاح.

### 2) إنشاء job

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/manual-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"player_id":"5123456789","codes":["XXXX-XXXX-XXXX-XXXX"]}'
```

### 3) Poll حتى الانتهاء

```bash
curl -s "https://api.pubgredeemerbot.com/v1/jobs/JOB_ID" \
  -H "X-API-Key: YOUR_API_KEY"
```

---

## الباقات (30 يوم، USDT)

| الباقة | الحد اليومي | السعر |
|--------|-------------|-------|
| Starter | 25 | 5 USDT |
| Standard | 200 | 10 USDT |
| Pro | 1,000 | 25 USDT |
| Enterprise | 2,500 | 50 USDT |
| Ultra | 5,000 | 85 USDT |
| Titan | 10,000 | 135 USDT |
| **HTTP API add-on** | 30 يوم | **15 USDT** |

---

## كلمات مفتاحية

Midasbuy API · Midasbuy redeem API · PUBG Mobile UC API · فحص كود Midasbuy · تفعيل شدات ببجي · بوت شحن UC · pubgredeemerbot API · SparkUCBot API · Midasbuy integration · UC reseller API · auto redeem Midasbuy · API شدات · تفعيل كود شدات · ببجي موبايل API

---

## الدعم

[@sparkuc_support](https://telegram.me/sparkuc_support) · [www.pubgredeemerbot.com](https://www.pubgredeemerbot.com)
