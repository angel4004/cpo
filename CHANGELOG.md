# CHANGELOG

## Unreleased
- Добавлен UX Contract для onboarding: один assistant-turn должен вести к одному целевому действию пользователя, а intake, Draft Project Passport, Passport Challenge Review, Passport Hardening, Final Snapshot, Project Instructions и publication instructions разделены по шагам.
- Onboarding metrics intake теперь начинается с ближайшего измеримого результата клиента и доказательства, а не с полного блока методических labels.
- Routine decision rights intake удалён из no-passport onboarding: CPO / владелец продукта считается decision maker по умолчанию, а copilot уточняет только human checkpoints для legal, security, privacy, compliance, pricing, public claims, client commitments и руководства.
- Draft Project Passport, Passport Challenge Review и Project Instructions разделены на отдельные assistant-turn: после draft copilot спрашивает готовность к review, а Project Instructions больше не дублируют полный паспорт проекта.
- Onboarding no passport flow теперь явно собирает цели и рамку решения до draft passport, а вопрос про карту ответственности не должен повторять уже собранные роли клиента.
- Критичные поля со статусом `частично собрано` больше не считаются готовыми к Draft Project Passport / проверке паспорта; текущая альтернатива, baseline, target и источники данных должны быть собраны или явно помечены пользователем как `unknown`.
- User-facing onboarding теперь закреплён как plain-language contract: вопросы не должны выводить методические англицизмы вроде Customer Value Chain Intake, publish-critical metrics, decision rights или Next decision area.
- В корневом README блок `Для чего он нужен` перенесён выше блока `Что это`, чтобы сначала показать ценность, а затем формат подключения.
- Перестроено описание ценности CPO Copilot: блок объясняет связь идей, фич и решений с целями продукта и бизнеса, контекст перед решением и риск фич без понятного основания.

## v0.4.0
- PAF-режим усилен как routing / next-step engine, а не только как слой осторожности.
- Для вопросов о следующем артефакте добавлен обязательный compact routing block: `decision type → PAF context / activity → required artifacts → missing inputs / artifacts → forbidden claim labels → next best artifact / next check`.
- Усилена работа с contradiction / gap context: CPO должен явно поднимать конфликт, evidence gap, forbidden claim labels и next check, не сглаживая unsupported PMF/Growth claims.
- PMF evidence block стал более человеко- и машино-читаемым: русские labels сохраняют canonical terms в скобках, включая `Segment`, `Need`, `Alternative`, `PMF metric`, `baseline / benchmark / norm`.
- Onboarding Sources Check получил явные empty-state формулировки без двойных отрицаний и различает clean setup от setup with project artifacts.
- Onboarding flow теперь сначала разводит ветки `passport exists` / `no passport`: без паспорта CPO собирает context intake вопросами, а с паспортом запускает review / hardening существующего паспорта.
- Project Context Intake усилен правилом одной question-line за шаг; старый паспорт без новых полей явно маркируется как `это не ошибка автора`.
- Неоднозначные onboarding-поля заменены на явные, но компактные контексты: human checkpoints, текущая альтернатива, основные роли клиента, статус запуска по слоям, глобальная и ближайшая цель, классы метрик и источники правды по типам.
- PAF-routing поведение до последней wording-правки проверено full API baseline matrix: GPT-5.5 + Sonnet 4.6, 2 прогона на модель, 5 PAF-сценариев, итог `20/20 pass`.

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
