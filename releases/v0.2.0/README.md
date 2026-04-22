# v0.2.0

Это заметка о релизе `v0.2.0`.
Это не стартовая точка для запуска.

Если хочешь понять, что это за copilot и как его запустить, начни с корневого [README.md](../../README.md).

## Что изменилось

- CPO Copilot теперь должен выполнять compact decision readiness check перед сильными продуктовыми решениями.
- Product discovery / decision-вопросы маршрутизируются по четырём каноническим типам гипотез: customer, value proposition, solution и business model.
- PMF нельзя утверждать без отдельной доказательной базы: метрики, связи метрики с потребностью, baseline / norm / benchmark, assumptions about norm, qualitative evidence, forbidden claims и next check.
- Product Project Passport Template теперь содержит отдельные разделы `PMF evidence` и `Hypothesis map`.
- PMF evidence block не включается как тяжёлый формат для любого раннего обсуждения PMF; полный блок обязателен для сильных PMF-выводов и решений.

## Проверено

- OpenClaw diff-check: Н1, Н2 и Н3 закрыты.
- Runtime smoke-test: запуск проекта, product mode, PMF evidence, Hypothesis map и acquisition / GTM-related routing проверены на рабочих запросах.
- Release precheck: рабочий markdown-пакет, launch prompt, START HERE, README, setup checklist и post-setup cleanup согласованы.
