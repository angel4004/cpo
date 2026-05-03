# How to Set Up a CPO Copilot Project

Этот файл — вспомогательная памятка setup-слоя.

Если ты читаешь репозиторий руками, главная точка входа — [README.md](../../README.md).

## Роль setup-файлов
- [START HERE] Activate CPO Copilot — главный протокол активации внутри GPT Project или Claude Project.
- [PROMPT] Launch CPO Copilot — только текст первого сообщения в чат.
- Этот файл — короткая памятка о том, что должно получиться после активации.
- Создание GPT/Claude Project и настройка памяти описаны в корневом [README.md](../../README.md).

## Что должно получиться после активации
После онбординга copilot должен провести draft/review/hardening пошагово и выдать 2 результата отдельными шагами:
- `[PROJECT INSTRUCTIONS]` — текст для поля `Project instructions`;
- `[PROJECT PASSPORT]` — финальный стабильный markdown-файл, который нужно сохранить и добавить в `Sources`.

Первый паспорт после onboarding — это Draft Project Passport, а не финальный source document.
До публикации в Sources должны пройти:

```text
Customer Value Chain Intake
→ Draft Project Passport
→ Passport Challenge Review
→ Passport Hardening Interview
→ Final Passport Snapshot
→ Project Instructions
```

Финальный [PROJECT PASSPORT] пользователь сохраняет отдельным markdown-файлом и добавляет в Sources вручную.
Copilot не обновляет Sources автоматически.
После draft copilot останавливается и спрашивает готовность к Passport Challenge Review.
Passport Challenge Review и Passport Hardening Interview идут отдельным assistant-turn после согласия пользователя.
Project Instructions готовятся отдельным шагом и не дублируют полный паспорт проекта.
Stage-маркеры должны быть standalone-строками ровно в таком виде: `[DRAFT PROJECT PASSPORT]`, `[PASSPORT CHALLENGE REVIEW]`, `[PASSPORT HARDENING INTERVIEW]`.
Пробелы внутри квадратных скобок, suffix вроде `compact` / `Question 1/3` и объединённые заголовки недопустимы.
После compact review copilot должен вести Passport Hardening как controlled interview: один вопрос за шаг, не более одного вопросительного знака в assistant-turn, 2-3 варианта ответа в формате A/B/C, один рекомендованный вариант, `Поле паспорта:` и `Что изменится в паспорте:`.
Copilot не должен сразу выдавать Final Passport Snapshot: сначала пользователь отвечает на hardening-вопросы.

## Что можно убрать из Sources после активации
Если выполнены все условия ниже, setup-файлы из `runtime/project_setup` можно убрать из `Sources`:
- текст `[PROJECT INSTRUCTIONS]` уже вставлен в поле `Project instructions`;
- финальный `[PROJECT PASSPORT]` после Passport Challenge Review и Passport Hardening уже сохранён отдельным markdown-файлом и добавлен в `Sources`;
- повторная активация проекта сейчас не нужна.

Что должно остаться в `Sources`:
- markdown-файлы из `runtime/core`;
- `[PROJECT PASSPORT]`;
- актуальные документы текущего проекта.

Если позже понадобится повторная активация или перепроверка setup-логики, setup-файлы можно временно вернуть в `Sources`.
