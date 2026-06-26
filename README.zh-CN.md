# Midasbuy API — PUBG Mobile UC 兑换 | Spark UC Bot HTTP API

> **独立开发者 API** — Midasbuy 风格 UC 兑换、券码验证、玩家查询、库存批量自动化。  
> **非** Midasbuy、Krafton 或 Tencent 官方服务。

[![Telegram](https://img.shields.io/badge/Telegram-@SparkUCBot-26A5E4?style=flat&logo=telegram)](https://t.me/SparkUCBot)
[![Docs](https://img.shields.io/badge/Docs-api.pubgredeemerbot.com-2dd4bf?style=flat)](https://api.pubgredeemerbot.com/docs)

**语言:** [EN](./README.md) · [AR](./README.ar.md) · [RU](./README.ru.md) · [UR](./README.ur.md) · [FA](./README.fa.md) · [TR](./README.tr.md) · [HI](./README.hi.md) · [中文](./README.zh-CN.md)

---

## 简介

**Spark UC Bot** 在 `https://api.pubgredeemerbot.com` 提供 **PUBG Mobile UC / Midasbuy** 兑换码 HTTP REST API，与 Telegram 机器人 [@SparkUCBot](https://t.me/SparkUCBot) 使用相同兑换流程。

- UC 兑换 — `POST /v1/jobs/manual-redeem`
- 验码（最多 10 个）— `POST /v1/jobs/check-code`
- 玩家查询 — `GET /v1/player/lookup`
- 库存批量兑换 — `POST /v1/jobs/stock-redeem`

适用于 **代理商**、**面板** 和 **自动化集成**。

---

## 链接

| 资源 | URL |
|------|-----|
| API | https://api.pubgredeemerbot.com |
| 文档 | https://api.pubgredeemerbot.com/docs |
| Swagger | https://api.pubgredeemerbot.com/swagger |
| 落地页 | https://www.pubgredeemerbot.com/midasbuy-api.html?lang=ch |
| 机器人 | https://t.me/SparkUCBot |
| 支持 | https://t.me/sparkuc_support |

---

## 认证

```http
X-API-Key: YOUR_API_KEY
```

在 **@SparkUCBot** 获取：有效套餐 → **HTTP API 附加**（15 USDT / 30 天）。

---

## 快速示例

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/manual-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"player_id":"5123456789","codes":["XXXX-XXXX-XXXX-XXXX"]}'
```

详见 [docs/QUICKSTART.md](./docs/QUICKSTART.md) · [docs/FAQ.md](./docs/FAQ.md)

---

## 关键词

Midasbuy API · PUBG Mobile UC API · Midasbuy兑换API · Midasbuy验码 · pubgredeemerbot API · SparkUCBot API · 和平精英UC · UC自动兑换
