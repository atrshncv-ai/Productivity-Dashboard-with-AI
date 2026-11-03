# Productivity Dashboard with AI

A personal productivity dashboard built with **Next.js + TypeScript**: tasks, analytics and reminders in one place, with Google Sheets as the data backend and AI-generated recommendations.

> **Status: prototype** — a working dashboard for personal use; features are functional, deployment details may require adjustment for your own hosting.

## Features

- Dashboard with productivity analytics and charts (Recharts)
- User accounts: registration, login, password hashing (bcryptjs)
- **Google Sheets integration** as the data layer (service-account credentials via `googleapis`)
- **AI recommendations** — OpenAI-based suggestions shown on the dashboard
- Reminders in two channels: in-browser notifications (PWA) and a Telegram fallback via webhook
- Server-side reminder cron (`/api/cron/notifications`), with a GitHub Actions schedule included
- PWA-ready (icons, manifest)

## Tech stack

Next.js (App Router), TypeScript, React, Recharts, next-auth + bcryptjs, googleapis (Google Sheets), openai, Tailwind CSS.

## Project layout

The application lives in the [`productivity-dashboard/`](productivity-dashboard) subdirectory:

- `src/app/dashboard/page.tsx` — main dashboard
- `src/app/api/*` — API routes (auth, AI, telegram webhook, cron notifications)
- `src/lib/googleSheets.ts` — Google Sheets client
- `src/lib/openai.ts` — AI recommendations client
- `src/lib/telegram.ts` — Telegram notification channel

Detailed technical notes (notifications setup, webhook binding, Google Sheets migration, env variables) are in [`productivity-dashboard/README.md`](productivity-dashboard/README.md).

## Local run

```bash
cd productivity-dashboard
npm install
npm run dev
```

Open `http://localhost:3000`. Build: `npm run build && npm run start`.

## Configuration

Environment variables are documented in the nested README; key names include `GOOGLE_SHEETS_CREDENTIALS`, `TELEGRAM_BOT_TOKEN`, `TELEGRAM_WEBHOOK_SECRET`, `CRON_SECRET`, `APP_BASE_URL`. No secrets are committed to the repository.

---

# Productivity Dashboard with AI

Персональный дашборд продуктивности на **Next.js + TypeScript**: задачи, аналитика и напоминания в одном месте, с Google Sheets в роли хранилища данных и AI-рекомендациями.

> **Статус: prototype** — рабочий дашборд для личного использования; функциональность реализована, детали деплоя могут требовать настройки под ваш хостинг.

## Возможности

- Дашборд с аналитикой продуктивности и графиками (Recharts)
- Учётные записи: регистрация, вход, хеширование паролей (bcryptjs)
- **Интеграция Google Sheets** как слой данных (service-account креды через `googleapis`)
- **AI-рекомендации** — подсказки на базе OpenAI на дашборде
- Напоминания в двух каналах: браузерные уведомления (PWA) и Telegram-fallback через webhook
- Серверный cron напоминаний (`/api/cron/notifications`), включая расписание в GitHub Actions
- Готовность к PWA (иконки, манифест)

## Технологический стек

Next.js (App Router), TypeScript, React, Recharts, next-auth + bcryptjs, googleapis (Google Sheets), openai, Tailwind CSS.

## Структура проекта

Приложение находится в поддиректории [`productivity-dashboard/`](productivity-dashboard):

- `src/app/dashboard/page.tsx` — основной дашборд
- `src/app/api/*` — API-роуты (auth, AI, telegram webhook, cron-уведомления)
- `src/lib/googleSheets.ts` — клиент Google Sheets
- `src/lib/openai.ts` — клиент AI-рекомендаций
- `src/lib/telegram.ts` — Telegram-канал уведомлений

Подробные технические заметки (настройка уведомлений, привязка webhook, миграция Google Sheets, переменные окружения) — в [`productivity-dashboard/README.md`](productivity-dashboard/README.md).

## Локальный запуск

```bash
cd productivity-dashboard
npm install
npm run dev
```

Откройте `http://localhost:3000`. Сборка: `npm run build && npm run start`.

## Конфигурация

Переменные окружения описаны во вложенном README; ключевые имена: `GOOGLE_SHEETS_CREDENTIALS`, `TELEGRAM_BOT_TOKEN`, `TELEGRAM_WEBHOOK_SECRET`, `CRON_SECRET`, `APP_BASE_URL`. Секреты в репозиторий не коммитятся.

## License / Лицензия

Released under the MIT License. See [LICENSE](LICENSE).
Проект распространяется по лицензии MIT. См. [LICENSE](LICENSE).
