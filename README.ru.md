# Midasbuy API для UC PUBG Mobile — Spark UC Bot HTTP API

> **Независимый API** для активации кодов UC в стиле Midasbuy, проверки ваучеров, lookup игрока и автоматизации склада.  
> Не связан с Midasbuy, Krafton или Tencent.

[![Telegram](https://img.shields.io/badge/Telegram-@SparkUCBot-26A5E4?style=flat&logo=telegram)](https://telegram.me/SparkUCBot)
[![Docs](https://img.shields.io/badge/Docs-api.pubgredeemerbot.com-2dd4bf?style=flat)](https://api.pubgredeemerbot.com/docs)

**Языки:** [EN](./README.md) · [AR](./README.ar.md) · [RU](./README.ru.md) · [UR](./README.ur.md) · [FA](./README.fa.md) · [TR](./README.tr.md) · [HI](./README.hi.md) · [中文](./README.zh-CN.md)

![Spark UC Bot — Midasbuy API для UC ПУБГ Мобайл](./docs/images/spark-uc-midasbuy-api-cover.png)

---

## Описание

**Spark UC Bot** — HTTP REST API на `https://api.pubgredeemerbot.com` для **кодов UC PUBG Mobile / Midasbuy** — тот же pipeline, что и Telegram-бот [@SparkUCBot](https://telegram.me/SparkUCBot).

**Возможности:**

- Активация UC на Player ID — `POST /v1/jobs/manual-redeem`
- Проверка ваучеров (до 10 кодов) — `POST /v1/jobs/check-code`
- Lookup ника — `GET /v1/player/lookup`
- Пакетная активация со склада — `POST /v1/jobs/stock-redeem`
- Аккаунт, quota, история, склад

Для **реселлеров**, **панелей** и **автоматизации**.

### Скриншоты

![HTTP API активации UC PUBG — POST manual-redeem](./docs/images/pubg-uc-redeem-api.webp)

![Midasbuy API проверки кодов — valid / used / expired](./docs/images/midasbuy-code-check-api.webp)

![Проверка ID игрока PUBG Mobile перед активацией UC](./docs/images/pubg-player-id-lookup.webp)

---

## Ссылки

| Ресурс | URL |
|--------|-----|
| API | https://api.pubgredeemerbot.com |
| Документация | https://api.pubgredeemerbot.com/docs |
| Swagger | https://api.pubgredeemerbot.com/swagger |
| Landing | https://www.pubgredeemerbot.com/ru/midasbuy-api.html |
| Бот | https://telegram.me/SparkUCBot |
| Поддержка | https://telegram.me/sparkuc_support |

---

## Аутентификация

```http
X-API-Key: YOUR_API_KEY
```

Ключ в **@SparkUCBot** → активный тариф → **HTTP API add-on** (15 USDT / 30 дней).

---

## Быстрый старт

```bash
# Создать job активации
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/manual-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"player_id":"5123456789","codes":["XXXX-XXXX-XXXX-XXXX"]}'

# Poll статуса
curl -s "https://api.pubgredeemerbot.com/v1/jobs/JOB_ID" \
  -H "X-API-Key: YOUR_API_KEY"
```

Подробнее: [docs/QUICKSTART.md](./docs/QUICKSTART.md) · [docs/FAQ.md](./docs/FAQ.md)

---

## Тарифы (30 дней, USDT)

| План | Лимит/день | Цена |
|------|------------|------|
| Starter | 25 | 5 USDT |
| Standard | 200 | 10 USDT |
| Pro | 1 000 | 25 USDT |
| Enterprise | 2 500 | 50 USDT |
| Ultra | 5 000 | 85 USDT |
| Titan | 10 000 | 135 USDT |
| **API add-on** | 30 дней | **15 USDT** |

---

## Ключевые слова

Midasbuy API · PUBG Mobile UC API · Midasbuy redeem API · проверка кода Midasbuy · pubgredeemerbot API · SparkUCBot API · активация UC · API реселлера PUBG
