# v0.4.0

Краткая заметка о PAF-ветке.
Это не стартовая точка для запуска.

Если хочешь понять, что это за copilot и как его запустить, начни с корневого [README.md](../../README.md).

## Что было

- PAF уже помогал не делать unsupported PMF / PCF / Growth claims.
- Evidence discipline была сильной, но выбор следующего артефакта иногда превращался в обычный совет.
- Sonnet 4.6 мог отвечать содержательно, но не стабильно выдавал проверяемую routing-форму.

## Что стало

- Для вопросов о следующем артефакте CPO обязан начинать с compact routing block:
  `decision type → PAF context / activity → required artifacts → missing inputs / artifacts → forbidden claim labels → next best artifact / next check`.
- Contradiction / gap context стал first-class behavior: сначала конфликт и gaps, потом безопасный следующий шаг.
- PMF evidence block стал понятнее для русскоязычного пользователя: русский смысл сохраняется рядом с canonical terms.
- Passport flow остаётся сильным operational layer, но не подменяет весь PAF.

## Проверено

- Full API baseline matrix: GPT-5.5 + Sonnet 4.6.
- 5 PAF-сценариев, 2 прогона на модель.
- Итог после правки CPO: `20/20 pass`.
