# AGENTS.md

## CPO Quality Ecosystem

Этот репозиторий является частью `cpo-quality-ecosystem`: набора связанных,
но независимых проектов вокруг качества CPO Copilot.

Соседние проекты:

- `cpo` — текущий репозиторий, source under test и рабочий markdown-пакет CPO Copilot.
- `../Salamander` — methodology audit / observability layer: сравнивает PAF reference layer и CPO Copilot working package.
- `../cpo-protocol-lab` — protocol harness: проверяет observable behavior через scenarios, fixtures, transcript, replay, deterministic evaluator и reports.

Границы ответственности:

- В этом repo меняй только рабочий пакет CPO Copilot: `runtime/core`, `runtime/project_setup`, `releases/`, `README.md`, `CHANGELOG.md` и repo-level инструкции.
- В `../Salamander` уходят задачи про методологический аудит PAF reference layer → CPO working package.
- В `../cpo-protocol-lab` уходят задачи про pass/fail onboarding-протокола, scenarios, fixtures, transcript, replay, deterministic evaluator и reports.
- Интеграция между проектами должна идти через artifacts и будущий quality-gate слой, а не через импорт кода соседних проектов.
- Не смешивай env, reports, deploy, runtime-файлы и проверки соседних проектов без явного запроса Ильи.

Важно: этот `AGENTS.md` — repo-level инструкция для агентов и разработки. Он не входит в CPO Copilot runtime package и не должен добавляться в GPT Project / Claude Project `Sources`.

## Назначение репозитория
- Это репозиторий CPO copilot.
- Это не обычное приложение и не локальный сервис.
- Здесь хранится рабочий markdown-пакет для запуска продуктового copilot внутри GPT Project.
- Git является источником истины для этого copilot.
- Релизы собираются из этого репозитория.

## Основные слои проекта
- `runtime/core` — канон и методическая база copilot.
- `runtime/project_setup` — setup-слой: активация, onboarding, шаблоны и вспомогательные материалы.
- `releases/` — релизный слой и релизные заметки.

## Канонический рабочий пакет
- Официальный рабочий пакет состоит из всех `.md`-файлов из `runtime/core` и `runtime/project_setup`.
- Для активации внутри GPT Project пользователь добавляет этот пакет в `Sources`.

## Режимы работы copilot
- `product mode` — когда продукт или проект уже есть.
- `exploration mode` — когда продукта ещё нет и нужно выбрать направление.

## Канонический сценарий активации
- Стартовый протокол активации задаётся файлом `runtime/project_setup/start_here_activate_cpo_copilot.md`.
- Файл `runtime/project_setup/prompt_launch_cpo_copilot.md` должен содержать только текст первого сообщения в чат GPT Project.
- В конце активации copilot должен выдать 2 артефакта:
  - `[PROJECT INSTRUCTIONS]` для поля `Project instructions`;
  - `[PROJECT PASSPORT]` как отдельный markdown-файл для `Sources`.

## Что считается успешной активацией
- `[PROJECT INSTRUCTIONS]` уже вставлены в `Project instructions`.
- `[PROJECT PASSPORT]` уже сохранён отдельным markdown-файлом и добавлен в `Sources`.
- После этого проект считается активированным и готовым к обычной работе.

## Post-setup инварианты
- Setup-файлы из `runtime/project_setup` можно убирать из `Sources`, только если:
  - `[PROJECT INSTRUCTIONS]` уже вставлены;
  - `[PROJECT PASSPORT]` уже сохранён и добавлен в `Sources`;
  - повторная активация сейчас не нужна.
- После этого в `Sources` должны оставаться:
  - markdown-файлы из `runtime/core`;
  - `[PROJECT PASSPORT]`;
  - актуальные документы текущего проекта.

## Релизный процесс
- Если изменение готовится как релиз или должно уйти в `main` как релизное изменение, обязательно проверь релизный слой.
- Для нового релиза нужно:
  - перенести накопленные записи из `CHANGELOG.md` → `Unreleased` в секцию новой версии;
  - создать или обновить `releases/vX.Y.Z/README.md`;
  - добавить в релизный README краткое описание, список изменений и, если проверки реально запускались, блок проверок;
  - убедиться, что корневой `README.md` остаётся единственной пользовательской точкой входа, а релизный README ссылается на него.
- Нельзя считать релиз готовым, если обновлён только корневой `README.md`, но не обновлены `CHANGELOG.md` и соответствующий `releases/vX.Y.Z/README.md`.

## Инварианты репозитория
- Корневой `README.md` — единственная пользовательская точка входа в проект.
- `releases/*/README.md` не должны быть стартовой точкой для запуска.
- `prompt_launch_cpo_copilot.md` не должен содержать служебную обвязку, объяснения или дублирующую мета-информацию.
- Логика запуска и логика post-setup cleanup должны быть согласованы между `README.md`, `runtime/project_setup/start_here_activate_cpo_copilot.md` и setup-чеклистом.
