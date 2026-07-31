# Quickstart — Spark UC Midasbuy-style API

Base URL: `https://api.pubgredeemerbot.com`  
Auth header: `X-API-Key: YOUR_API_KEY`

Get a key: [@SparkUCBot](https://telegram.me/SparkUCBot) → active plan → HTTP API add-on.

---

## 1. Health check (no auth)

```bash
curl -s https://api.pubgredeemerbot.com/health
```

---

## 2. Account & quota

```bash
curl -s https://api.pubgredeemerbot.com/v1/me \
  -H "X-API-Key: YOUR_API_KEY"

curl -s https://api.pubgredeemerbot.com/v1/quota \
  -H "X-API-Key: YOUR_API_KEY"
```

---

## 3. Player lookup (synchronous)

Charges **0.25** quota on success.

```bash
curl -s "https://api.pubgredeemerbot.com/v1/player/lookup?player_id=5123456789" \
  -H "X-API-Key: YOUR_API_KEY"
```

---

## 4. Manual redeem (async job)

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/manual-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "player_id": "5123456789",
    "codes": ["AbCdEfGhIjKlMnOp12"]
  }'
```

Save `job_id` from the response, then poll:

```bash
curl -s "https://api.pubgredeemerbot.com/v1/jobs/JOB_ID" \
  -H "X-API-Key: YOUR_API_KEY"
```

Wait until `"status": "done"` or `"failed"`.

**Batch:** up to **10** codes in the `codes` array per job.

---

## 5. Check code (async job)

Validate without redeeming:

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/check-code" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"codes": ["AbCdEfGhIjKlMnOp12", "XyZaBcDeFgHiJkLm34"]}'
```

Poll `GET /v1/jobs/{job_id}` for per-code status (valid / used / expired).

---

## 6. Stock redeem (async job)

Redeem from codes uploaded to your bot inventory:

```bash
curl -X POST "https://api.pubgredeemerbot.com/v1/jobs/stock-redeem" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"player_id": "5123456789", "uc_amount": 660}'
```

See live docs for exact body fields: [api.pubgredeemerbot.com/docs](https://api.pubgredeemerbot.com/docs)

---

## 7. Python example (poll loop)

```python
import time
import requests

API = "https://api.pubgredeemerbot.com"
KEY = "YOUR_API_KEY"
HEADERS = {"X-API-Key": KEY, "Content-Type": "application/json"}

r = requests.post(
    f"{API}/v1/jobs/manual-redeem",
    headers=HEADERS,
    json={"player_id": "5123456789", "codes": ["AbCdEfGhIjKlMnOp12"]},
)
r.raise_for_status()
job_id = r.json()["job_id"]

while True:
    j = requests.get(f"{API}/v1/jobs/{job_id}", headers=HEADERS).json()
    if j["status"] in ("done", "failed"):
        print(j)
        break
    time.sleep(2)
```

---

## 8. Order screenshot (WebP)

After a successful redeem job:

```bash
curl -X POST "https://api.pubgredeemerbot.com/api/v1/order/screenshot" \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"job_id": "JOB_ID"}' \
  --output order.webp
```

---

## Rate limits

Per-minute limits may apply per API key. On **429**, read `Retry-After` header and retry.

Full error codes: [api.pubgredeemerbot.com/docs](https://api.pubgredeemerbot.com/docs)
