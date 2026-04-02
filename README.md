# OAS-RS-VEZB-UVOD-OPENPROJECT

## Rešenje vežbe (Docker Compose + MailHog)

Dodat je parametarski `docker-compose.yaml` sa servisima:
- `openproject`
- `db` (PostgreSQL)
- `mailhog`

Perzistencija:
- `pgdata` za bazu
- `opdata` za OpenProject podatke

## 1) Podešavanje parametara (`.env`)

Kopiraj primer i prilagodi vrednosti:

```bash
cp .env.example .env
```

Najvažniji SMTP parametri (sada potpuno parametrizovani):
- `SMTP_HOST`
- `SMTP_PORT`
- `SMTP_AUTHENTICATION`
- `SMTP_USERNAME`
- `SMTP_PASSWORD`
- `SMTP_ENABLE_STARTTLS_AUTO`

Podrazumevano (`.env.example`) je lokalni MailHog (`mailhog:1025`) bez autentikacije i bez STARTTLS.

> Napomena: obavezno postavi bezbedan `OPENPROJECT_SECRET_KEY_BASE` pre realne upotrebe.

## 2) Pokretanje

```bash
docker compose up -d
```

Provera statusa:

```bash
docker compose ps
```

Logovi:

```bash
docker compose logs -f openproject
```

## 3) Pristup servisima

- OpenProject: `http://localhost:8080` (ili port iz `OPENPROJECT_HTTP_PORT`)
- MailHog UI: `http://localhost:8025` (ili port iz `MAILHOG_UI_PORT`)

## 4) Koraci iz zadatka

1. Otvori OpenProject i završi inicijalnu konfiguraciju (admin nalog).
2. Kreiraj novi projekat.
3. Dodaj nekoliko zadataka (work packages).
4. Organizuj zadatke kroz Kanban/Scrum board.
5. Izazovi slanje email-a (notifikacija/invite).
6. Proveri poruke u MailHog UI.
