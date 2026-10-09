# Проверка CI
## Событие, ветка и SHA
Workflow Python quality на main, SHA: https://github.com/AlexPlays070/pm03-day07/pull/1; Python 3.11 и 3.12.
## Красный запуск
URL: https://github.com/AlexPlays070/pm03-day07/pull/1/changes/062e1d0e152a803a26f2b0a655490123c3ff5f2e Job: tests (3.11/3.12), упавший step: Run tests.
Упали test_at_limit, test_high_priority, test_low_priority: ожидалось False, получено True (>= вместо >).
## Исправление
Вернул оператор > коммитом "Restore strict SLA boundary". PR: https://github.com/AlexPlays070/pm03-day07/pull/1/changes/28438ac262d73de1aec77737f027182f22fbd4c5
## Зелёный запуск на Python 3.11 и 3.12
URL: https://github.com/AlexPlays070/pm03-day07/pull/1/commits/071abe923071c49715b8470db2d162220a0ff54b , https://github.com/AlexPlays070/pm03-day07/pull/1/changes/dd6c0ae6ca7e9b094cc8757cf8658cae9b360990 Оба job зелёные.
## Два новых сценария
test_negative_elapsed: -1 даёт ValueError.
test_unknown_priority: "urgent" даёт ValueError. Всего 8 тестов.
## Что автоматическая проверка пока не покрывает
Не проверяются типы входа, кроме числа и строки; Python вне 3.11 и 3.12; нет проверки стиля кода.
