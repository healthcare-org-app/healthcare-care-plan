# care-plan-service

care-plan-service — domain: ehr

- **Port:** 8309
- **Language:** Python 3.11 + Flask
- **Database:** `ehr` (Postgres, table `care_plan`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/care_plan/`          |
| POST      | `/api/care_plan/`          |
| GET       | `/api/care_plan/<id>`      |
| PUT/PATCH | `/api/care_plan/<id>`      |
| DELETE    | `/api/care_plan/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `ehr-service`
- `care-teams-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
