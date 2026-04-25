# CHANGELOG

## Unreleased
- Добавлен Customer Value Chain Intake перед Draft Project Passport.
- Добавлен Passport Challenge Review, Passport Hardening, Final Passport Snapshot и Retrospective Passport Review для старых паспортов.
- Закреплено правило No Hidden Review Criteria: review не считает ошибкой пользователя отсутствие поля, которое onboarding не дал возможности заполнить.
- Product и Exploration Passport Templates теперь содержат Customer Value Chain / Candidate Customer Value Chain.
- В корневой README добавлено требование создавать отдельный GPT/Claude Project и включать память `Только для проекта`.
- Усилен post-draft contract: copilot сам запускает Passport Challenge Review и не предлагает загрузить draft passport в Sources.
- Passport Hardening переведён в controlled interview: compact review, затем последовательные вопросы с 2-3 вариантами ответа в формате A/B/C, рекомендацией и явным описанием будущего изменения паспорта.
- Добавлен interactive gate: copilot не выдаёт Final Passport Snapshot в первом post-draft ответе и не выбирает hardening decisions за пользователя.

## v0.2.0
- Закреплены обязательные PAF-проверки перед сильными продуктовыми решениями.
- Добавлен hypothesis routing по customer, value proposition, solution и business model hypotheses.
- Добавлен PMF evidence block с нормой, baseline / benchmark, assumptions about norm, qualitative evidence, forbidden claims и next check.
- PMF evidence и Hypothesis map доведены до product context schema, setup checklist и итогового [PROJECT PASSPORT].
- Смягчён PMF-trigger: полный PMF evidence block нужен для сильных PMF-выводов и решений, а не для любого раннего обсуждения PMF.
- Dialogue-first UX сохранён: ранние неясные запросы не превращаются в тяжёлый decision memo.

## v0.1.0
- Первый перенос реального CPO copilot в Git.
- Создан первый релизный слой.
- Раскатка в рабочую оболочку ещё не подтверждена.
