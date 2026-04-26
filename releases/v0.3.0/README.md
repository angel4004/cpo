# v0.3.0

Это заметка о релизе `v0.3.0`.
Это не стартовая точка для запуска.

Если хочешь понять, что это за copilot и как его запустить, начни с корневого [README.md](../../README.md).

## Что изменилось

- Onboarding теперь ведёт пользователя через Customer Value Chain Intake перед Draft Project Passport.
- После draft copilot должен сам запускать Passport Challenge Review и, при необходимости, Passport Hardening Interview.
- Passport Hardening стал пошаговым controlled interview: один вопрос за шаг, 2-3 варианта ответа, рекомендация, `Поле паспорта:` и `Что изменится в паспорте:`.
- Final Passport Snapshot нельзя выдавать сразу после draft: сначала нужно закрыть hardening-вопросы.
- Stage-маркеры и post-draft output получили более строгий machine-readable contract.
- Для старых паспортов без Customer Value Chain добавлена явная классификация gaps.
- Корневой README теперь объясняет ценность copilot более живым языком: зачем он нужен и в какое рабочее состояние приводит команду.
- В AGENTS.md закреплён релизный чек: при релизных изменениях нужно обновлять `CHANGELOG.md` и `releases/vX.Y.Z/README.md`.

## Проверено

- Документарная согласованность релиза: `README.md`, `CHANGELOG.md`, `AGENTS.md` и `releases/v0.3.0/README.md`.
