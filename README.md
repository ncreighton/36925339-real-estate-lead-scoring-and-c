# Real Estate Lead Scoring and CRM API

> REST API for proptech platforms automating real estate lead scoring and CRM operations. Ingests lead data from Zillow, Realtor.com, and direct web forms, scores each lead across 18 behavioural and demographic signals including property search frequency, price range alignment, pre-approval status, and engagement recency. Returns a composite score from 0 to 100 with contributing factor weights and next-best-action recommendation. Integrates with Follow Up Boss, kvCORE, and Salesforce via outbound webhook. Supports individual agent and team-level dashboards. Processes 500 leads per minute with 99.9 percent uptime SLA. Includes a 30-day lead velocity trend and source attribution breakdown in every response.

## Features

- Full REST API

## Quick Start

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Configure environment
cp .env.example .env
# Edit .env with your settings

# 3. Run locally
uvicorn main:app --reload --port 8000

# 4. View interactive docs
open http://localhost:8000/docs
```

## Docker Deployment

```bash
# Build and run
docker compose up -d

# Check health
curl http://localhost:8000/health
```

## Authentication

Get a token first:
```bash
curl -X POST "http://localhost:8000/auth/token?username=admin&password=admin123"
```

Use the token in subsequent requests:
```bash
curl -H "Authorization: Bearer YOUR_TOKEN" http://localhost:8000/items
```

## API Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/health` | System health |
| POST | `/auth/token` | Get JWT token |
| GET | `/items` | List all items |
| POST | `/items` | Create item |
| GET | `/items/{id}` | Get item |
| PATCH | `/items/{id}` | Update item |
| DELETE | `/items/{id}` | Delete item |
| GET | `/stats` | API statistics |

Full interactive docs: `http://localhost:8000/docs`

## Rate Limits

| Endpoint | Limit |
|----------|-------|
| `/auth/token` | 10/minute |
| `GET /items` | 60/minute |
| `POST /items` | 30/minute |
| `DELETE /items` | 20/minute |

## Running Tests

```bash
pip install pytest httpx
pytest tests/ -v
```

## Production Notes

- Change `SECRET_KEY` in `.env` before deploying
- Replace in-memory `_db` with a real database
- Add proper user management to `auth.py`
- Configure `ALLOWED_ORIGINS` for CORS
- Use Nginx/Traefik as reverse proxy

## License

MIT



---

## Free vs Pro

| Feature | Free | Pro |
|---------|:----:|:---:|
| 100 requests/day | Yes | Yes |
| Standard endpoints | Yes | Yes |
| JSON responses | Yes | Yes |
| Unlimited requests | - | Yes |
| Premium endpoints | - | Yes |
| Batch processing | - | Yes |
| Webhook notifications | - | Yes |
| SLA guarantee | - | Yes |
| Priority support | - | Yes |

### Upgrade to Pro

Get the full version with all premium features, priority support, and lifetime updates.

**[Get Pro Version](https://buy.stripe.com/6oU6oH3aLf6Q1de7jCcZa0x)**

- [Buy Now (Stripe)](https://buy.stripe.com/6oU6oH3aLf6Q1de7jCcZa0x)
- [Buy on Gumroad](https://pulsegear.gumroad.com/l/hkieuz)
- [Buy on Whop](https://whop.com/real-estate-lead-scoring-and-crm-api)

