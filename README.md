# CPO copilot

## Что это
Это рабочий markdown-пакет для запуска продуктового copilot внутри GPT Project.

Это не обычное приложение.
Его не нужно запускать локально через `Run`.

После настройки пользователь должен получить 2 результата:
- `[PROJECT INSTRUCTIONS]` — текст для поля `Project instructions`;
- `[PROJECT PASSPORT]` — markdown-файл с контекстом проекта для `Sources`.

## Для чего он нужен
Copilot умеет работать в двух режимах:
- `product mode` — когда продукт или проект уже есть;
- `exploration mode` — когда продукта ещё нет и нужно выбрать направление.

## Как запустить
1. Создай новый GPT Project.
2. Скачай все `.md`-файлы из `runtime/core`.
3. Скачай все `.md`-файлы из `runtime/project_setup`.
4. Добавь эти файлы в `Sources` своего GPT Project.
5. Открой файл [PROMPT] Launch CPO Copilot: [runtime/project_setup/prompt_launch_cpo_copilot.md](runtime/project_setup/prompt_launch_cpo_copilot.md).
6. Скопируй весь текст из этого файла в первый чат проекта.
7. Пройди онбординг.
8. Вставь полученный `[PROJECT INSTRUCTIONS]` в поле `Project instructions`.
9. Сохрани `[PROJECT PASSPORT]` отдельным `.md`-файлом и добавь его в `Sources`.

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
- `runtime/project_setup/prompt_launch_cpo_copilot.md` — только текст первого сообщения.
- `releases/` — релизные заметки. Это не стартовая точка.

## Что не делать
- Не начинай с `releases/v0.1.0/README.md`, если хочешь запустить copilot.
- Не подключай Google Drive как основной способ запуска рабочего пакета.
- Не добавляй папки вместо конкретных markdown-файлов.
- Не подключай весь репозиторий, если тебе нужен только рабочий пакет.
