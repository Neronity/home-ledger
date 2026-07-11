# Local Development

This document explains how to run local services for Home Ledger.

Backend and frontend commands will be added after those apps are generated. For now, the local runtime service is PostgreSQL through Docker Compose.

## Requirements

- Docker Desktop or a compatible Docker environment
- Docker Compose v2, usually available as `docker compose`

## PostgreSQL with Docker Compose

The root `docker-compose.yml` defines one local PostgreSQL service.

Default connection values:

```text
Host: localhost
Port: 5432
Database: home_ledger
Username: home_ledger_user
Password: home_ledger_password
```

These values can be overridden with a local `.env` file. Use `.env.example` as the template.

## Start PostgreSQL

```bash
docker compose up -d
```

This starts PostgreSQL in the background.

## Check PostgreSQL Status

```bash
docker compose ps
```

The PostgreSQL service should eventually show as running and healthy.

To view logs:

```bash
docker compose logs postgres
```

## Stop PostgreSQL

```bash
docker compose down
```

This stops the container but keeps the named volume, so local database data is preserved.

## Reset PostgreSQL Data

```bash
docker compose down -v
```

This stops the container and deletes the named volume. Use it when you want a clean local database.

## Environment Variables

Supported local variables:

```text
POSTGRES_DB=home_ledger
POSTGRES_USER=home_ledger_user
POSTGRES_PASSWORD=home_ledger_password
POSTGRES_PORT=5432
```

Recommended setup:

PowerShell:

```powershell
Copy-Item .env.example .env
```

Bash:

```bash
cp .env.example .env
```

Then edit `.env` if local overrides are needed.

## Troubleshooting

### Port 5432 is already in use

Another PostgreSQL instance may already be running locally.

Options:

- Stop the other local PostgreSQL service.
- Change `POSTGRES_PORT` in `.env`, for example `POSTGRES_PORT=5433`.

### Container starts but is not healthy

Check logs:

```bash
docker compose logs postgres
```

If data is corrupted or local setup is disposable, reset the volume:

```bash
docker compose down -v
docker compose up -d
```
