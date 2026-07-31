# API endpoints reference

Production base: **`https://api.pubgredeemerbot.com`**

Authentication: header **`X-API-Key`** on all `/v1/*` and `/api/v1/*` routes (except public health).

| Method | Path | Auth | Sync/async | Description |
|--------|------|------|------------|-------------|
| GET | `/health` | No | Sync | Service health |
| GET | `/v1/me` | Yes | Sync | Balance, subscription snapshot |
| GET | `/v1/quota` | Yes | Sync | Daily limits, usage, trial |
| GET | `/v1/player/lookup?player_id=` | Yes | Sync | Nickname & region; 0.25 quota on success |
| POST | `/v1/jobs/manual-redeem` | Yes | **Async** | Redeem 1–10 UC codes to Player ID |
| POST | `/v1/jobs/check-code` | Yes | **Async** | Validate 1–10 vouchers without redeem |
| POST | `/v1/jobs/stock-redeem` | Yes | **Async** | Redeem from uploaded stock |
| GET | `/v1/jobs/{job_id}` | Yes | Sync | Poll job status & result |
| GET | `/v1/jobs?limit=&offset=` | Yes | Sync | List jobs (newest first, max limit 100) |
| GET | `/v1/history?limit=&offset=` | Yes | Sync | Redemption history (paginated) |
| GET | `/v1/stock/summary` | Yes | Sync | Available stock by UC denomination |
| POST | `/v1/subscription/purchase` | Yes | Sync | Buy plan from API balance (see live docs) |
| POST | `/api/v1/order/screenshot` | Yes | Sync | WebP ORDER DETAILS image from `job_id` |

---

## Job workflow

1. `POST` to a job endpoint → receive `{ "job_id": "..." }`
2. `GET /v1/jobs/{job_id}` until `status` is `done` or `failed`
3. Read `result` payload (structure documented per job type)

Player lookup is the main **synchronous** redeem-related call.

---

## Request bodies (summary)

### `POST /v1/jobs/manual-redeem`

```json
{
  "player_id": "5123456789",
  "codes": ["18-char-voucher-code"]
}
```

- `codes`: array, **1–10** elements, 18-character alphanumeric vouchers

### `POST /v1/jobs/check-code`

```json
{
  "codes": ["code1", "code2"]
}
```

- `codes`: array, **1–10** elements (use one element for single check)

---

## Documentation URLs

| Page | URL |
|------|-----|
| HTML reference | https://api.pubgredeemerbot.com/docs |
| Swagger UI | https://api.pubgredeemerbot.com/swagger |
| OpenAPI JSON | https://api.pubgredeemerbot.com/openapi.json |
| Landing (8 langs) | https://www.pubgredeemerbot.com/midasbuy-api.html |

This file is a summary. **Always refer to live `/docs` for the latest version and error codes.**
