# CHANGELOG

## Unreleased
- В корневом README блок `Для чего он нужен` перенесён выше блока `Что это`, чтобы сначала показать ценность, а затем формат подключения.

## v0.3.0
- Evidence gaps после Customer Value Chain Intake теперь должны идти в Draft Project Passport → Passport Challenge Review → Passport Hardening Interview, а не в дополнительный intake по метрикам.
- Ready-to-send письма, task, request, checklist, interview scripts, survey guides и question banks больше не должны содержать серию вопросов с `?`; подтверждаемые пункты оформляются как labels/prompts.
- Добавлен Customer Value Chain Intake перед Draft Project Passport.
- Добавлен Passport Challenge Review, Passport Hardening, Final Passport Snapshot и Retrospective Passport Review для старых паспортов.
- Закреплено правило No Hidden Review Criteria: review не считает ошибкой пользователя отсутствие поля, которое onboarding не дал возможности заполнить.
- Product и Exploration Passport Templates теперь содержат Customer Value Chain / Candidate Customer Value Chain.
- В корневой README добавлено требование создавать отдельный GPT/Claude Project и включать память `Только для проекта`.
- Усилен post-draft contract: copilot сам запускает Passport Challenge Review и не предлагает загрузить draft passport в Sources.
- Passport Hardening переведён в controlled interview: compact review, затем последовательные вопросы с 2-3 вариантами ответа в формате A/B/C, рекомендацией и явным описанием будущего изменения паспорта.
- Добавлен interactive gate: copilot не выдаёт Final Passport Snapshot в первом post-draft ответе и не выбирает hardening decisions за пользователя.
- Уточнён machine-readable contract stage-маркеров: standalone-строки без пробелов внутри `[]` и без suffix на той же строке.
- Закреплено, что post-draft ответ должен фактически содержать `[PASSPORT CHALLENGE REVIEW]` и `[PASSPORT HARDENING INTERVIEW]`, а не обещание выполнить их позже.
- Missing-input вопросы после Customer Value Chain Intake должны оформляться как `[PASSPORT HARDENING INTERVIEW]` с `Поле паспорта:` и `Что изменится в паспорте:`.
- Правило одного вопроса усилено до машинной эвристики: не более одного вопросительного знака в assistant-turn; поля шаблонов и checklist должны быть labels без вопросительного знака.
- Для старых паспортов без Customer Value Chain закреплена явная классификация `onboarding gap / missing input / needs follow-up`; пустые Customer Value Chain labels трактуются как `unknown`.
- В корневой README добавлено более живое описание ценности CPO Copilot.
- В AGENTS.md закреплено, что релизные изменения должны обновлять `CHANGELOG.md` и `releases/vX.Y.Z/README.md`.

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
