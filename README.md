# Haminjast Backend

Go services for a lost-and-found platform, with search, chat, and background processing.

## Overview

Backend services for Haminjast, a lost-and-found platform. The repository contains a main API service and a worker service, with code for posters, users, search, conversations, and background processing.

**Stack:** Go · Docker Compose · PostgreSQL · Elasticsearch · Redis · RabbitMQ

## Repository structure

| Path | Responsibility |
| --- | --- |
| `src/MainService/` | API, data models, repositories, and WebSocket code |
| `src/WorkerService/` | Background processing and notification code |
| `src/StackBuilderService/` | Additional service-stack configuration |
| `src/MainService/docs/` | Generated Swagger documentation |

## Local development

Install Docker with Compose and GNU Make. Review the service configuration and environment variables for your local setup before starting containers.

```bash
git clone https://github.com/imhmdrz/haminjast-backend.git
cd haminjast-backend/src/MainService
make start DOCKER_COMP="docker compose"
```

The Makefile lives under `src/MainService/`, not the repository root. Its default executable is the legacy `docker-compose`; the override above selects the modern Compose command.

```bash
make logs DOCKER_COMP="docker compose"
make down DOCKER_COMP="docker compose"
```

Review the separate Compose files under `src/WorkerService/` and `src/StackBuilderService/` for the rest of the stack. Starting the main service alone does not establish that all integrations are configured.

## Upstream

This repository is a fork of [MohammadaliFakhari/Haminjast-BackEnd](https://github.com/MohammadaliFakhari/Haminjast-BackEnd). Credit for the upstream project belongs to its contributors.
