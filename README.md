<<<<<<< HEAD
# airflow-docker
=======
# Docker Compose – Check Container Status

## Command

```bash
docker compose ps -a
```

## Purpose

Displays the status of all containers defined in the Docker Compose project, including stopped and failed containers.

## Usage

```bash
cd ~/airflow-docker
docker compose ps -a
```

## Container Status Explained

| Status | Meaning |
|---|---|
| Up | Container is running |
| Up (healthy) | Container is running and health check passed |
| Up (unhealthy) | Container is running but health check failed |
| Exited | Container stopped or crashed |
| Restarting | Container is repeatedly restarting |
| Created | Container created but not started |

## Useful Airflow Commands

### Check all containers

```bash
docker compose ps -a
```

### Check running containers only

```bash
docker compose ps
```

### View all service logs

```bash
docker compose logs -f
```

### Check Airflow API server

```bash
docker compose logs -f airflow-apiserver
```

### Check scheduler

```bash
docker compose logs -f airflow-scheduler
```

### Check worker

```bash
docker compose logs -f airflow-worker
```

### Check initialization

```bash
docker compose logs airflow-init
```

### Restart all services

```bash
docker compose restart
```

### Start all services

```bash
docker compose up -d
```

### Stop all services

```bash
docker compose down
```

## Airflow UI

```text
http://localhost:8080
```

## Troubleshooting

If any container shows `Exited` or `Restarting`, inspect its logs:

```bash
docker compose logs --tail=100 SERVICE_NAME
```

Example:

```bash
docker compose logs --tail=100 airflow-scheduler
```

**Important:** Avoid `docker compose down -v` unless you intentionally want to delete persistent Docker volumes, including the PostgreSQL metadata database.

>>>>>>> e2505a2 (added dockerfiles and readme files here)
