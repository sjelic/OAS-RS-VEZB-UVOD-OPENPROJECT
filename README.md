# OAS-RS-VEZB-UVOD-OPENPROJECT

## Rešenje vežbe (Docker Compose + MailHog)

U repozitorijumu je dodat `docker-compose.yaml` koji sadrži:
- `openproject` servis,
- `db` (PostgreSQL) servis,
- `mailhog` servis,
- volumene `pgdata` i `opdata` za perzistenciju.

SMTP podešavanja za OpenProject su nameštena da koriste MailHog:
- host: `mailhog`
- port: `1025`

> Napomena: `SECRET_KEY_BASE` je obavezan za pokretanje OpenProject-a.
> Za realno okruženje obavezno promeniti vrednost `super-secret-change-me` nasumičnim i bezbednim stringom.

## Pokretanje

```bash
docker compose up -d
```

Provera statusa:

```bash
docker compose ps
```

Pregled logova (korisno kod inicijalnog podizanja):

```bash
docker compose logs -f openproject
```

## Pristup servisima

- OpenProject: http://localhost:8080
- MailHog UI: http://localhost:8025

## Koraci iz zadatka

1. Otvoriti OpenProject na `http://localhost:8080` i završiti inicijalnu konfiguraciju (admin nalog).
2. Kreirati novi projekat.
3. Dodati nekoliko zadataka (work packages).
4. Otvoriti Board (Kanban/Scrum) i rasporediti zadatke po kolonama.
5. Uraditi akciju koja šalje email (npr. poziv korisnika/notifikacija).
6. Otvoriti MailHog UI na `http://localhost:8025` i proveriti da su poruke isporučene.
