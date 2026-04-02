# OAS-RS-VEZB-UVOD-OPENPROJECT

## Rešenje vežbe (Docker Compose + MailHog)

U repozitorijumu je dodat `docker-compose.yaml` koji sadrži:
- `openproject` servis,
- `db` (PostgreSQL) servis,
- `mailhog` servis,
- volumene `pgdata` i `opdata` za perzistenciju.

SMTP podešavanja za OpenProject su već nameštena da koriste MailHog:
- host: `mailhog`
- port: `1025`

## Pokretanje

```bash
docker compose up -d
```

Provera statusa:

```bash
docker compose ps
```

## Pristup servisima

- OpenProject: http://localhost:8080
- MailHog UI: http://localhost:8025

## Predlog za deo zadatka o testiranju

1. Ulogovati se u OpenProject i završiti inicijalni setup (admin nalog).
2. Kreirati projekat.
3. Dodati nekoliko zadataka (work packages).
4. Otvoriti Board (Kanban/Scrum) i rasporediti zadatke po kolonama.
5. Uraditi akciju koja šalje email (npr. poziv korisnika / notifikacija) i proveriti poruku u MailHog UI.
