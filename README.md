# CPO copilot

## Что это
CPO Copilot — это набор markdown-инструкций для GPT Project или Claude Project. Он помогает превратить обычный AI-чат в продуктового помощника, который работает с контекстом конкретного продукта или идеи.

Это не приложение, которое нужно запускать локально. Файлы добавляются в `Sources` / project knowledge, а дальше copilot сам проводит пользователя через настройку.

В конце настройки появляются 2 рабочих артефакта:
- `[PROJECT INSTRUCTIONS]` — правила поведения copilot внутри проекта;
- `[PROJECT PASSPORT]` — паспорт продукта с контекстом, пользователями, value chain, ограничениями и слабыми местами.

## Для чего он нужен
CPO Copilot нужен, чтобы быстро привести продуктовый контекст в порядок: понять, что мы делаем, для кого, какую ценность хотим дать и где сейчас есть слабые места.

Он помогает не держать всё в голове и не собирать заново из разных обсуждений, документов и догадок. Вместо этого у команды появляется единая опора для дальнейшей работы.

После активации copilot понимает продуктовый контекст и помогает спокойнее проходить discovery, выбирать приоритеты, обсуждать стратегию и объяснять решения.

Copilot умеет работать в двух режимах:
- `product mode` — когда продукт или проект уже есть;
- `exploration mode` — когда продукта ещё нет и нужно выбрать направление.

## Как запустить
1. Создай новый GPT Project или Claude Project.
2. В настройках памяти выбери режим `Только для проекта`. Не используй глобальную память для контекста CPO Copilot.
3. Скачай все `.md`-файлы из `runtime/core`.
4. Скачай все `.md`-файлы из `runtime/project_setup`.
5. Добавь эти файлы в `Sources` / project knowledge своего проекта.
6. Открой файл [PROMPT] Launch CPO Copilot: [runtime/project_setup/prompt_launch_cpo_copilot.md](runtime/project_setup/prompt_launch_cpo_copilot.md).
7. Скопируй весь текст из этого файла в первый чат проекта.
8. Пройди онбординг.
9. Дойди до Customer Value Chain Intake, Draft Project Passport, Passport Challenge Review, Passport Hardening Interview и Final Passport Snapshot.
   После черновика copilot должен в том же assistant-turn сам вывести `[PASSPORT CHALLENGE REVIEW]` и, если есть critical / major weak points, `[PASSPORT HARDENING INTERVIEW]`.
   Stage-маркеры должны быть standalone-строками без пробелов внутри квадратных скобок и без suffix на той же строке.
   Hardening идёт пошагово: один вопрос за шаг, не более одного вопросительного знака в assistant-turn, 2-3 варианта ответа в формате A/B/C, один рекомендованный вариант, `Поле паспорта:` и `Что изменится в паспорте:`.
   Copilot не должен сразу выдавать Final Passport Snapshot: сначала нужно ответить на hardening-вопросы.
10. Вставь полученный `[PROJECT INSTRUCTIONS]` в поле `Project instructions`.
11. Сохрани финальный `[PROJECT PASSPORT]` отдельным `.md`-файлом и добавь его в `Sources`.

## Что должно остаться после активации
Если выполнены все условия ниже, setup-файлы из `runtime/project_setup` можно убрать из `Sources`:
- текст `[PROJECT INSTRUCTIONS]` уже вставлен в `Project instructions`;
- `[PROJECT PASSPORT]` уже сохранён и добавлен в `Sources`;
- повторная активация проекта сейчас не нужна.

В `Sources` должны остаться:
- markdown-файлы из `runtime/core`;
- `[PROJECT PASSPORT]`;
- актуальные документы текущего проекта.

Если позже понадобится повторная активация, setup-файлы можно временно вернуть в `Sources`.

## Что где лежит
- `runtime/core` — канон и методическая база copilot.
- `runtime/project_setup/start_here_activate_cpo_copilot.md` — протокол активации, по которому copilot должен работать внутри проекта.
- `runtime/project_setup/method_project_passport_review_and_hardening_for_cpo_copilot.md` — процесс Customer Value Chain Intake, Passport Challenge Review, Passport Hardening и финальной публикации паспорта.
- `runtime/project_setup/prompt_launch_cpo_copilot.md` — только текст первого сообщения.
- `releases/` — релизные заметки. Это не стартовая точка.

## Что не делать
- Не начинай с `releases/*/README.md`, если хочешь запустить copilot.
- Не подключай Google Drive как основной способ запуска рабочего пакета.
- Не добавляй папки вместо конкретных markdown-файлов.
- Не подключай весь репозиторий, если тебе нужен только рабочий пакет.
- Не добавляй Draft Project Passport в `Sources`: сначала дождись Final Passport Snapshot.
