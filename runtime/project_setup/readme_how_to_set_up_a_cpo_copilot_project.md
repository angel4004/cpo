# How to Set Up a CPO Copilot Project

Этот файл — вспомогательная памятка setup-слоя.

Если ты читаешь репозиторий руками, главная точка входа — [README.md](../../README.md).

## Роль setup-файлов
- [START HERE] Activate CPO Copilot — главный протокол активации внутри GPT Project.
- [PROMPT] Launch CPO Copilot — только текст первого сообщения в чат.
- Этот файл — короткая памятка о том, что должно получиться после активации.

## Что должно получиться после активации
После онбординга copilot должен провести draft/review/hardening и выдать 2 результата:
- `[PROJECT INSTRUCTIONS]` — текст для поля `Project instructions`;
- `[PROJECT PASSPORT]` — финальный стабильный markdown-файл, который нужно сохранить и добавить в `Sources`.

Первый паспорт после onboarding — это Draft Project Passport, а не финальный source document.
До публикации в Sources должны пройти:

```text
Customer Value Chain Intake
→ Draft Project Passport
→ Passport Challenge Review
→ Passport Hardening
→ Final Passport Snapshot
```

Финальный [PROJECT PASSPORT] пользователь сохраняет отдельным markdown-файлом и добавляет в Sources вручную.
Copilot не обновляет Sources автоматически.

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
