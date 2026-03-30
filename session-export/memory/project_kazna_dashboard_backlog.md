---
name: Kazna Dashboard Backlog
description: Список отложенных фич для дашборда казначейства — push-уведомления, daily cron, PDF, forecast, Sankey
type: project
---

## Выполнено

- Telegram-бот (Vercel serverless /api/telegram, webhook настроен)
- Sparklines в KPI-карточках (canvas-based)
- Hero-метрика "Тобі причитається" с формулой борга
- QC Panel (BLOCKER/WARNING из 21_qc_engine.js)
- Effective Fee Rate (4 категории утримань)
- Activity feed "Що нового"
- Multi-owner через URL ?owner=OWN-001
- Auto-sync: Web App API https://script.google.com/macros/s/AKfycbyMW-.../exec
- Apps Script deployment v6 (clasp + UI)

## Отложенные задачи

### P0: Push-уведомлення при поступлении
- Потрібен тригер в Google Sheets (onEdit або за розкладом)
- Apps Script викликає Vercel endpoint або Telegram API напряму
- Зберігати chat_id у Script Properties

### P0: Щоденна зведка (cron)
- Vercel Cron Jobs або Google Apps Script time-driven trigger
- dailySummary() вже написана в 93_telegram_bot.gs
- Потрібен setupDailyTrigger() — запустити один раз в Apps Script

### P1: Mobile-first режим
- 3 KPI + activity feed + баланс на мобільному
- 80% переглядів з телефону через Telegram

### P1: PDF-експорт
- Кнопка "Звіт за лютий" з графіками та таблицями
- html2pdf.js або puppeteer server-side

### P1: Cash Flow Forecast
- Прогноз залишку на 7/14/30 днів
- На основі середніх темпів та графіка виплат

### P2: Sankey-діаграма
- Реальні потоки з товщиною ліній пропорційно сумам
- D3.js sankey plugin

### P2: Drill-down по кліку
- Клік на KPI → деталізація, клік на стовпець → транзакції дня

## Ключові URL
- Dashboard: https://kazna-dashboard.vercel.app
- GitHub: https://github.com/yasikvlad/kazna-dashboard
- Bot: @IIkoznachey_bot (token: env TG_BOT_TOKEN)
- Web App API: https://script.google.com/macros/s/AKfycbyMW-PW06ahc-V5p0OF1RS4ugm9IBHg5IeniDuGrrwIz0_1FXdJsUunUo544e-2OXD9yQ/exec
- Apps Script project: 1ukVZDOEmhvo1qLEamvovV2sJu068JOJQI2UcYPqLqfXhVr5_NjzqQQow
