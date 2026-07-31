# FAQ — Midasbuy-style PUBG Mobile UC API

## Is this the official Midasbuy API?

**No.** Spark UC Bot provides an **independent** HTTP API that processes PUBG Mobile UC / Midasbuy-style voucher codes through the same redemption pipeline as the Telegram bot [@SparkUCBot](https://telegram.me/SparkUCBot).

We are not affiliated with Midasbuy, Krafton, or Tencent.

---

## What is the API base URL?

| | URL |
|---|-----|
| Production | https://api.pubgredeemerbot.com |
| HTML docs | https://api.pubgredeemerbot.com/docs |
| Swagger | https://api.pubgredeemerbot.com/swagger |
| Health | https://api.pubgredeemerbot.com/health |
| Landing page | https://www.pubgredeemerbot.com/midasbuy-api.html |

---

## How do I get an API key?

1. Open [@SparkUCBot](https://telegram.me/SparkUCBot)
2. Subscribe to a daily plan (USDT wallet in bot)
3. Purchase **HTTP API add-on** (15 USDT / 30 days)
4. Copy key from the API menu in Telegram

Free API trial may be granted by admin — contact [@sparkuc_support](https://telegram.me/sparkuc_support).

---

## Can I check codes before redeeming?

**Yes.** Use `POST /v1/jobs/check-code` with a `codes` array (1–10 vouchers). Poll `GET /v1/jobs/{job_id}` for validation results without charging a player ID.

---

## Is redeem synchronous?

**No** for redeem and check-code — they are **async jobs**.  
`POST` returns `job_id` immediately; poll `GET /v1/jobs/{id}` until complete.

**Yes** for `GET /v1/player/lookup` — synchronous GET.

---

## How much does API access cost?

- Active subscription plan from **5 USDT / 30 days** (Starter tier)
- Plus **HTTP API add-on: 15 USDT / 30 days**
- Requires an active base plan

Plans combine when you hold multiple subscriptions. Limits reset every 24 hours.

---

## What can I automate?

- UC redeem to Player ID (manual codes)
- Batch code validation (reseller QC)
- Player nickname lookup before redeem
- Stock / inventory batch redeem
- History export, quota monitoring, order screenshot images

---

## Bot vs API — which should I use?

| Use bot if… | Use API if… |
|-------------|-------------|
| You redeem manually | You run a panel or shop |
| You want free trial in chat | You need REST + polling |
| Individual volume | High volume automation |

Same USDT wallet and subscription system.

---

## Support

Telegram: [@sparkuc_support](https://telegram.me/sparkuc_support)  
Website: [www.pubgredeemerbot.com](https://www.pubgredeemerbot.com)

Integration help, billing disputes, API trials.
