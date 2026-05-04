# CPO Copilot Setup Checklist
Статус: CHECKLIST
Обновлено: 2026-04-24

Отмечай пункт только после реальной проверки.

## 1. Базовая сборка проекта
[ ] Downstream CPO copilot project уже создан по корневому README
[ ] Понятно, что это рабочий продуктовый проект, а не внутренняя мастерская PAF
[ ] CPO / владелец продукта считается ответственным за продуктовые решения по умолчанию
[ ] Понятно, есть ли уже паспорт проекта из другого Copilot
[ ] Если паспорта нет, copilot запускает последовательный Project Context Intake
[ ] Если паспорт уже есть, copilot запускает проверку паспорта на gaps, рискованные формулировки и уточнение контекста
[ ] В Project Context Intake один шаг содержит одну question-line с одним `?`, а дополнительные поля оформлены как labels без вопросительных знаков
[ ] Copilot не пытается собрать весь минимальный context set одним большим intake-блоком; исключение — цепочка ценности клиента четырьмя labels
[ ] Понятно, в какой из двух ситуаций запускаем copilot:
[ ] Product mode — продукт или объект работы уже есть
[ ] Exploration mode — продукта пока нет и нужно выбрать направление

## 2. Подключён рабочий пакет
[ ] Подключён полный рабочий markdown-пакет по каноническому списку из [START HERE] Activate CPO Copilot
[ ] [START HERE] Activate CPO Copilot находится и читается в Sources
[ ] Если файлов не хватает, copilot просит добавить недостающие файлы по списку из [START HERE], а не папку и не альтернативный источник

## 3. Подготовлен Project passport
[ ] До draft passport пройдена развилка passport exists / no passport
[ ] В no passport flow до draft passport собран минимальный context set: объект работы, сегмент и основные роли клиента, цепочка ценности клиента, статус по слоям, цели и рамка решения, критичные метрики и доказательства или unknown, отдельные human checkpoints для legal/security/privacy/pricing/public claims/client commitments или unknown
[ ] Статус `частично собрано` по publish-critical блоку не считается готовностью к Draft Project Passport и Passport Challenge Review
[ ] Текущее и целевое значение, классы метрик и источники данных заданы пользователем или явно помечены пользователем как unknown
[ ] До draft passport собрана цепочка ценности клиента
[ ] Copilot подготовил [DRAFT PROJECT PASSPORT] как рабочий черновик, а не финальный source document
[ ] Stage-маркер `[DRAFT PROJECT PASSPORT]` написан дословно отдельной строкой, без пробелов внутри `[]` и без suffix
[ ] Draft passport содержит цепочку ценности клиента или явно фиксирует unknown / missing inputs
[ ] После draft passport copilot остановился и спросил готовность к Passport Challenge Review
[ ] Stage-маркер `[PASSPORT CHALLENGE REVIEW]` написан дословно отдельной строкой, без пробелов внутри `[]`, без suffix и идёт отдельным assistant-turn после согласия пользователя
[ ] Copilot не объединяет Draft Project Passport, Passport Challenge Review и Passport Hardening Interview в один assistant-turn
[ ] Copilot не связывает Draft Project Passport с публикацией в Sources
[ ] Copilot не выгружает полный review-report по умолчанию
[ ] Copilot помог выполнить Passport Hardening как controlled interview после Passport Challenge Review, если review нашёл critical / major weak points
[ ] Stage-маркер `[PASSPORT HARDENING INTERVIEW]` написан дословно отдельной строкой, без пробелов внутри `[]`, без suffix и идёт после `[PASSPORT CHALLENGE REVIEW]`
[ ] Hardening идёт один вопрос за шаг
[ ] Hardening-шаг содержит ровно один user-facing вопрос и не более одного вопросительного знака во всём assistant-turn
[ ] Каждый hardening-вопрос содержит 2-3 варианта ответа в формате A/B/C и один рекомендованный вариант, если контекста достаточно
[ ] Каждый hardening-вопрос содержит `Поле паспорта:` и `Что изменится в паспорте:`
[ ] Copilot останавливается на первом hardening-вопросе и ждёт ответа пользователя
[ ] Copilot не выбирает hardening decisions за пользователя
[ ] Если draft уже добавлен в Sources, первый hardening-вопрос исправляет source hygiene
[ ] Copilot подготовил [FINAL PROJECT PASSPORT SNAPSHOT] только после ответов пользователя на critical / major hardening questions
[ ] Copilot прямо объяснил, что только финальный [PROJECT PASSPORT] нужно сохранить отдельным markdown-файлом
[ ] Финальный паспорт сохранён и добавлен в Sources вручную

## 3B. Подготовлены и вставлены Project instructions
[ ] Copilot после final snapshot или явной просьбы подготовил [PROJECT INSTRUCTIONS] Инструкция проекта отдельным assistant-turn
[ ] Project instructions не дублируют полный паспорт проекта и описывают поведение copilot
[ ] Copilot прямо объяснил, что этот текст нужно вставить в Project instructions
[ ] Текст вставлен в Project instructions
[ ] Понятно, что copilot может делать без отдельного подтверждения
[ ] Понятно, что copilot не должен решать без отдельного подтверждения

## 3C. Решение по setup-файлам после активации
[ ] Понятно, что setup-файлы из `runtime/project_setup` можно убирать из Sources только после успешной активации
[ ] Текст [PROJECT INSTRUCTIONS] уже вставлен в Project instructions
[ ] Финальный [PROJECT PASSPORT] после Passport Challenge Review и Passport Hardening уже сохранён отдельным markdown-файлом и добавлен в Sources
[ ] Понятно, что в Sources должны остаться markdown-файлы из `runtime/core`, [PROJECT PASSPORT] и актуальные документы проекта
[ ] Если повторная активация пока не нужна, setup-файлы из `runtime/project_setup` можно убрать из Sources

## 4. Проверка логики Sources
[ ] Copilot прямо говорит, что уже подключено в Sources
[ ] Copilot прямо говорит, что обязательно добавить в Sources сейчас
[ ] Copilot прямо говорит, что не стоит добавлять в Sources
[ ] Copilot прямо говорит, что можно добавить позже
[ ] В onboarding-ответе используются дословные Sources Check headings: `Что уже подключено в Sources`, `Что обязательно добавить в Sources сейчас`, `Что не стоит добавлять в Sources`, `Что можно добавить позже`
[ ] Copilot не просит Google Drive, папки или весь репозиторий, если нужен только рабочий markdown-пакет
[ ] Copilot при проверке состава рабочего пакета опирается на [START HERE], а не на собственный список
[ ] Если рабочий markdown-пакет подключён полностью, copilot пишет позитивный статус без двойных отрицаний: `Рабочий markdown-пакет подключён полностью.`
[ ] Первый onboarding-ответ различает clean setup и setup with project artifacts, не превращая clean setup в тяжёлый audit report
[ ] Если passport status unclear, первый user-facing вопрос — о наличии паспорта проекта из другого Copilot, а не о режиме и не о цепочке ценности клиента
[ ] Если рабочий пакет подключён полностью, первый ответ не перечисляет все 14 файлов, а показывает grouped summary `Core: 4/4, Project setup: 10/10`
[ ] В exploration mode без продукта copilot не предлагает варианты, завязанные на существующий продукт, платформу, трафик или аналитику
[ ] Copilot не просит добавлять шумные raw-export материалы без явной пользы
[ ] Copilot объясняет простыми словами, что такое Sources
[ ] Copilot не ждёт, что пользователь сам догадается, что именно туда добавлять
[ ] Copilot спокойно принимает ответ `unknown` или `не знаю`, если пользователь чего-то не знает

## 4B. Evidence gaps and one-question UX
[ ] В no passport flow после цепочки ценности клиента copilot не выдаёт сразу большой Draft Project Passport, а продолжает Project Context Intake одним вопросом за шаг
[ ] В no passport flow evidence gap до draft фиксируется как missing context / unknown, а не как publish-blocking review претензия к пользователю
[ ] Evidence gap фиксируется в [DRAFT PROJECT PASSPORT] как unknown / missing project evidence / forbidden claim только после корректного draft, где evidence labels уже были заданы, или в existing passport flow
[ ] Premature draft с unasked / partial publish-critical evidence классифицируется как onboarding gap и возвращает поток к Project Context Intake
[ ] Первый post-draft вопрос по evidence gap оформлен как `[PASSPORT HARDENING INTERVIEW]` с `Поле паспорта:` и `Что изменится в паспорте:`
[ ] Если пользователь говорит, что паспорт уже есть в Sources, но имя/содержимое не видно явно, copilot задаёт один вопрос о названии файла или тексте паспорта, а не ревьюит по памяти
[ ] Если пользователь уже назвал файл паспорта в Sources, copilot не спрашивает отдельное разрешение открыть или прочитать файл
[ ] Пока нет ни имени файла паспорта, ни видимого текста паспорта, copilot не обещает будущие review / hardening stage names как план
[ ] Для старого паспорта без новых полей copilot использует безопасную формулировку `это не ошибка автора`
[ ] Ready-to-send письма, task, request и checklist не содержат разделов с несколькими вопросами через `?`
[ ] Внутренние пункты таких артефактов оформлены как labels / пункты для подтверждения без вопросительных знаков
[ ] Interview scripts, survey guides и question banks в onboarding/hardening оформлены как prompts / labels без `?`
[ ] Hardening queue items оформлены как noun phrases / decision areas без `?`

## 5A. Если выбран product mode
[ ] Заполнено название проекта
[ ] Заполнено, что это за продукт в одной фразе
[ ] Заполнено, чем здесь управляем
[ ] Заполнены контуры продукта, процесса клиента, текущего решения и out-of-scope
[ ] Заполнены отдельные подтверждения для цели: что CPO / владелец продукта решает сам, что требует legal/security/privacy/pricing/public claims/client commitments/leadership, а уже собранные роли клиента переиспользованы без повторного вопроса
[ ] Заполнен текущий этап PLC
[ ] Если релевантно, заполнен текущий этап внутри Product Discovery
[ ] Заполнен статус запуска по слоям: доступность продукта (product availability), внедрение у клиентов (customer rollout), коммерческий статус (commercial status), готовность данных и интеграций (data / integration readiness)
[ ] Заполнены цели на длинный горизонт
[ ] Заполнены цели на ближайший горизонт
[ ] Заполнено, что проверяем следующим сейчас
[ ] Заполнен горизонт решения
[ ] Заполнены глобальная цель, ближайшая цель, критерий достижения ближайшей цели и что сейчас не является целью
[ ] Заполнены ключевые сегменты
[ ] Заполнена основная ценность продукта
[ ] Заполнено, что нужно клиенту
[ ] Заполнено, что даёт продукт
[ ] Заполнено, что клиент с этим делает
[ ] Заполнено, что клиент получает в измеримом результате
[ ] Если цепочка ценности клиента не заполнена, явно указаны unknown, missing inputs, что проверить и какие claims нельзя делать
[ ] Заполнена текущая бизнес-модель
[ ] Заполнено, что уже понятно по выводу на рынок, если это релевантно
[ ] Заполнены допущения по экономике, если это релевантно
[ ] Метрики разделены на метрику ценности (value), бизнес-метрику (business), метрику использования (usage), метрику доказательности (proof / evidence) и ограничительную метрику (guardrail)
[ ] Заполнены подтверждённые данные
[ ] Разведены подтверждённое и предположения
[ ] Если есть PMF-claim, заполнены метрика PMF, текущее значение / норма / ориентир и допущения о норме
[ ] Если обсуждается переход к Product Growth, PMF не утверждается без отдельного PMF evidence block
[ ] Заполнены активные гипотезы
[ ] Гипотезы разложены на customer, value proposition, solution и business model
[ ] Отдельно названа current priority hypothesis и её validation status
[ ] Заполнены существующие материалы
[ ] Заполнены текущие эксперименты, если они есть
[ ] Названы отсутствующие материалы
[ ] Заполнены ограничения
[ ] Заполнены главные риски
[ ] Заполнено, что пока неизвестно
[ ] Заполнены зоны, которые нельзя решать без отдельного подтверждения
[ ] Указаны источники правды по продуктовым фактам, данным/метрикам, методологии и текущему решению
[ ] Указаны дата обновления, владелец обновления и триггеры обновления
[ ] Подготовлен [PROJECT PASSPORT] Паспорт проекта с product context
[ ] [PROJECT PASSPORT] содержит цепочку ценности клиента
[ ] [PROJECT PASSPORT] содержит PMF evidence или явное `not assessed`
[ ] [PROJECT PASSPORT] содержит Hypothesis map

## 5B. Если выбран exploration mode
[ ] Понятно, кто инициатор поиска
[ ] Понятно, почему вопрос возник сейчас
[ ] Понятно, какой результат ждут от exploration
[ ] Понятно, на что уже есть опора: навыки, доступы, данные, преимущества
[ ] Названы направления, которые уже рассматриваются
[ ] Названы потенциальные аудитории
[ ] Названы потенциальные проблемы или потребности
[ ] Собрана кандидатная цепочка ценности клиента как гипотеза, а не подтверждённый product context
[ ] Если кандидатная цепочка ценности клиента не заполнена, явно указаны unknown, missing inputs, что проверить и какие claims нельзя делать
[ ] Зафиксированы уже существующие сигналы
[ ] Разведены факты и допущения
[ ] Названы ограничения и риски
[ ] Названы самые сильные гипотезы направления
[ ] Назван следующий маленький тест
[ ] Понятно, при каких условиях можно перейти в product mode
[ ] Подготовлен [PROJECT PASSPORT] Паспорт проекта с exploration context
[ ] [PROJECT PASSPORT] содержит кандидатную цепочку ценности клиента или явно фиксирует missing inputs

## 6. Источники правды реально подключены
[ ] Подключены локальные документы, если они есть
[ ] Подключены исследования, если они есть
[ ] Подключены метрики, dashboards или analytics, если они есть
[ ] Подключены decision logs, если они есть
[ ] Понятно, какие источники актуальны, а какие устарели

## 7. Проверка качества настройки
[ ] Copilot понимает, что общий brain и локальные факты — это разные слои
[ ] Copilot не путает канон, метод и локальный контекст
[ ] Copilot не обещает лучшее решение без missing inputs
[ ] Decision-запросы не проходят без readiness check
[ ] Readiness check показывает тип решения, PAF-контекст, required inputs / artifacts, missing inputs, forbidden claims и next check
[ ] Discovery-вопросы маршрутизируются в customer, value proposition, solution и business model hypotheses
[ ] Acquisition / GTM-related вопросы не превращаются в новый канонический тип гипотезы
[ ] PMF не утверждается без PMF evidence block
[ ] PMF evidence block содержит метрику, связь метрики с потребностью, baseline / norm / benchmark, assumptions about norm, qualitative evidence, forbidden claims и next check
[ ] Для раннего PMF-обсуждения copilot фиксирует evidence gap без тяжёлого полного блока, если сильного PMF-claim ещё нет
[ ] Copilot не начинает с roadmap слишком рано
[ ] Copilot не уходит в тяжёлое проектирование без сигнала готовности
[ ] Copilot умеет прямо назвать локальный максимум
[ ] Copilot говорит простым русским языком
[ ] Copilot объясняет английские термины по-русски при первом упоминании
[ ] Copilot не делает вид, что product context уже есть, если на самом деле идёт exploration mode
[ ] Copilot не использует source docs как рабочую память проекта
[ ] Copilot не считает первый Draft Project Passport финальным источником правды
[ ] Copilot после draft passport спрашивает готовность к Passport Challenge Review
[ ] Copilot запускает Passport Challenge Review отдельным assistant-turn после согласия пользователя
[ ] Copilot не выгружает полный review-report по умолчанию, если достаточно compact review
[ ] Draft / Review / Hardening выводятся с дословными standalone stage-маркерами `[DRAFT PROJECT PASSPORT]`, `[PASSPORT CHALLENGE REVIEW]`, `[PASSPORT HARDENING INTERVIEW]`
[ ] Stage-маркеры не содержат пробелов внутри квадратных скобок и suffix вроде `compact`, `Question 1/3`, тире или двоеточия на той же строке
[ ] Post-draft assistant-turn не содержит review/hardening-блоки и останавливается на вопросе готовности к Passport Challenge Review
[ ] Passport Challenge Review включает Evidence, PAF Consistency, цепочку ценности клиента, SMART, Metrics, Human Checkpoints и Source Hygiene
[ ] Проверка цепочки ценности клиента идёт до SMART Review и Metrics Review
[ ] Review различает passport weak point, onboarding gap, missing project evidence, PAF consistency issue, customer value chain gap, SMART issue, metrics issue, human checkpoint issue, source hygiene issue, forbidden claim, publish blocker и wording issue
[ ] Hardening-вопросы предлагают 2-3 варианта улучшения слабых формулировок в формате A/B/C
[ ] Hardening-вопросы рекомендуют один вариант, если контекста достаточно
[ ] Hardening-вопросы по missing inputs оформлены как `[PASSPORT HARDENING INTERVIEW]`, а не как обычный intake-вопрос
[ ] Варианты A/B/C, hardening queue, шаблоны, checklist и формы внутри assistant-turn не добавляют дополнительные вопросительные знаки
[ ] Copilot не выбирает hardening decisions за пользователя
[ ] Final Passport Snapshot не появляется в первом post-draft ответе до ответов пользователя
[ ] Review маркирует факты, выводы, допущения, неопределённости и forbidden claims
[ ] Review не представляет локальные адаптации как канон PAF
[ ] Review не утверждает PMF, PCF, customer success или бизнес-эффект без evidence
[ ] No Hidden Review Criteria соблюдено: отсутствие поля, которое onboarding не спрашивал, классифицируется как onboarding gap / missing input / needs follow-up
[ ] Для старых паспортов доступна ретроспективная проверка старого паспорта
[ ] Copilot не обновляет Sources автоматически

## 8. Smoke tests

### Тест 0 — нейтральный вход
Запрос:
«Настрой продуктового копилота»

Хороший ответ:
[ ] Copilot принимает этот вход как валидный триггер
[ ] Copilot не делает вид, что инструмент только для CPO
[ ] Copilot сразу переходит к настройке
[ ] Copilot после onboarding готовит Project instructions, Draft Project Passport, Passport Challenge Review, Passport Hardening и Final Passport Snapshot как последовательный процесс, а не одним сплошным ответом

### Тест 1 — продукт уже есть
Запрос:
«У нас уже есть продукт. На какой стадии он сейчас и чего не хватает для уверенной диагностики?»

Хороший ответ:
[ ] Не путает PLC и Discovery
[ ] Показывает степень уверенности
[ ] Показывает, чего не хватает

### Тест 2 — продукта пока нет
Запрос:
«У меня пока нет продукта. Я только думаю, что вообще стоит делать. Помоги начать.»

Хороший ответ:
[ ] Не делает вид, что product context уже существует
[ ] Переходит в exploration mode
[ ] Помогает выбрать следующий маленький шаг
[ ] Не тащит в тяжёлое проектирование слишком рано

### Тест 3 — проверка логики Sources
Запрос:
«Что мне нужно добавить в Sources сейчас, а что не стоит добавлять?»

Хороший ответ:
[ ] Называет недостающие файлы рабочего пакета по [START HERE] и нужные типы проектных материалов
[ ] Разделяет must have / не стоит / optional
[ ] Не просит Google Drive, папки, весь репозиторий или лишний шум



### Тест 4 — локальный максимум
Запрос:
«Мы хотим просто запустить ещё одну фичу. Это хороший ход?»

Хороший ответ:
[ ] Говорит, что оптимизирует этот ход
[ ] Говорит, почему это похоже на локальный максимум
[ ] Не обещает лучшее решение

### Тест 5 — переход к проектированию
Запрос:
«Мы уже готовы идти в серьёзное проектирование или ещё нет?»

Хороший ответ:
[ ] Называет сигнал перехода
[ ] Называет, чего ещё не хватает
[ ] Называет следующий главный рабочий материал

### Тест 6 — передача в разработку
Запрос:
«Можно ли отдавать это в разработку?»

Хороший ответ:
[ ] Сначала определяет тип решения
[ ] Называет канонический PAF-контекст
[ ] Называет required inputs / artifacts
[ ] Показывает missing inputs
[ ] Показывает forbidden claims
[ ] Называет next check
[ ] Не отвечает сразу «да» или «нет», если входов не хватает

### Тест 7 — выбор фичи
Запрос:
«Стоит ли делать такую фичу?»

Хороший ответ:
[ ] Раскладывает вопрос на customer, value proposition, solution и business model hypotheses
[ ] Показывает, если затронуто несколько типов гипотез
[ ] Называет первую гипотезу для проверки
[ ] Называет подходящий класс проверки или эксперимента
[ ] Называет forbidden claims

### Тест 8 — PMF и переход к Growth
Запрос:
«У нас уже есть PMF, давай переходить к Growth.»

Хороший ответ:
[ ] Проверяет PMF evidence block
[ ] Называет PMF claim, segment, need и alternative
[ ] Проверяет метрику PMF и связь метрики с частотностью потребности
[ ] Проверяет baseline / norm / benchmark и assumptions about norm
[ ] Показывает qualitative evidence
[ ] Называет missing inputs и forbidden claims, если доказательств не хватает

### Тест 9 — ранняя идея
Запрос:
«У меня есть идея, что с ней делать?»

Хороший ответ:
[ ] Сохраняет dialogue-first режим
[ ] Сначала помогает прояснить суть идеи
[ ] Не выдаёт тяжёлый checklist сразу
[ ] Объясняет, что канонические проверки включатся при приближении к решению

### Тест 10 — passport hardening после onboarding
Запрос:
«Мы прошли онбординг. Можно добавить паспорт в Sources?»

Хороший ответ:
[ ] Говорит, что первый паспорт — draft
[ ] Проверяет, собрана ли цепочка ценности клиента
[ ] Не предлагает загрузить draft в Sources
[ ] Если draft уже показан, спрашивает готовность к Passport Challenge Review
[ ] Не просит пользователя самому ревьюить draft вместо Copilot review
[ ] Не объединяет Draft Project Passport, Passport Challenge Review, Passport Hardening Interview, Final Passport Snapshot и Project Instructions в один assistant-turn
[ ] После согласия пользователя запускает Passport Challenge Review отдельным assistant-turn
[ ] В review-turn находит critical и major weak points
[ ] В review-turn не выгружает полный review-report по умолчанию
[ ] В review-turn спрашивает готовность перейти к первому hardening-вопросу
[ ] После согласия пользователя переходит к Passport Hardening Interview отдельным assistant-turn
[ ] В hardening-turn задаёт первый hardening-вопрос
[ ] Hardening-вопрос содержит 2-3 варианта ответа в формате A/B/C и один рекомендованный вариант
[ ] Hardening-вопрос объясняет, какое поле паспорта изменится
[ ] Останавливается на первом hardening-вопросе и не выдаёт Final Passport Snapshot в том же ответе
[ ] Не выбирает hardening decisions за пользователя
[ ] Если пользователь уже добавил draft в Sources, первый вопрос касается удаления draft из Sources или замены его финальным паспортом после уточнений
[ ] Готовит Final Passport Snapshot только после ответов пользователя на hardening-вопросы
[ ] Объясняет, что финальный [PROJECT PASSPORT] пользователь сохраняет и добавляет в Sources вручную

### Тест 11 — старый паспорт без цепочки ценности клиента
Запрос:
«Проверь старый паспорт проекта, в нём нет цепочки клиентской ценности.»

Хороший ответ:
[ ] Запускает ретроспективную проверку старого паспорта
[ ] Объясняет, что старый onboarding не собирал цепочку ценности клиента
[ ] Классифицирует отсутствие действия клиента или измеримого результата клиента как onboarding gap / missing input / needs follow-up
[ ] Не называет это персональным дефектом автора паспорта

## 9. Дисциплина обновления
[ ] Понятно, кто обновляет контекст
[ ] Понятно, как часто он обновляется
[ ] Понятно, какие события требуют обновления
[ ] Понятно, где фиксируются новые решения

## 10. Финальный вердикт
[ ] Проект реально готов к работе
[ ] Проект ещё не готов — сначала нужно закрыть незаполненные пункты
