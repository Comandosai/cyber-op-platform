# Кибер ОП — AI Platform

Внутренняя платформа Кибер ОП для построения и эксплуатации AI-агентов и chatflow-сценариев. Используется для автоматизации входящих лидов, продуктовых консультаций, подбора тарифов и закрытия сделок через специализированных AI-специалистов (Squad).

## Статус

Закрытый внутренний проект. Доступ — по согласованию.

## Архитектура

Платформа построена как self-hosted сервис из двух основных компонент:

- `api/` — backend на Python (Flask + DDD слоистая архитектура).
- `web/` — frontend на TypeScript (Next.js / React).
- `docker/` — конфигурации развёртывания через Docker Compose.

Конфигурации chatflow-сценариев хранятся в YAML-файлах в корне репозитория (например, `cyber-op-sales-team.yml`).

## Быстрый старт

Требования: Docker, Docker Compose, доступ к Git.

```bash
git clone <repo-url> cyber-op
cd cyber-op/docker
cp .env.example .env
# Отредактировать .env: указать ключи моделей (OpenAI и т.п.) и сгенерированные секреты
docker compose up -d
```

После запуска UI будет доступен на `http://localhost`. Импорт chatflow-конфига — через UI: «Apps → Create from DSL file» → загрузить `cyber-op-sales-team.yml`.

## Разработка

```bash
pnpm install
pnpm run lint
pnpm run type-check
```

Для локальной разработки backend и frontend — см. `dev/` и инструкции в `AGENTS.md`.

## Структура репозитория

| Каталог | Назначение |
|---------|------------|
| `api/` | Backend сервис |
| `web/` | Frontend приложение |
| `packages/` | Общие пакеты (UI-кит и пр.) |
| `docker/` | Docker Compose, .env-шаблоны, инициализация |
| `dev/` | Скрипты для локальной разработки |
| `scripts/` | Утилитарные скрипты |
| `e2e/` | E2E-тесты |
| `sdks/` | Клиентские SDK |
| `docs/` | Внутренняя документация |

## Контакты

Поддержка проекта — команда Кибер ОП. Внешние вопросы: https://comandos.ai

## Лицензия

См. файл `LICENSE` в корне репозитория.
