# API Test Cases — demo

## ATC-001 — POST /orders — создание заказа с валидными данными
- Приоритет: P0
- Operation: POST /orders
- Test Condition: ATCND-001
- Request:
  - `productId`: непустая строка
  - `quantity`: 1
- Шаги:
  1. Отправить POST /orders.
- Ожидаемый status: 201
- Ожидаемый response/schema:
  - response соответствует `Order`.
- Automation: Recommended
- Automation reason: контрактная регрессионная проверка с однозначным ожидаемым результатом.

## ATC-003 — POST /orders — quantity меньше минимального значения
- Приоритет: P1
- Operation: POST /orders
- Test Condition: ATCND-003
- Request:
  - валидный `productId`
  - `quantity`: 0
- Шаги:
  1. Отправить POST /orders.
- Ожидаемый status: 400
- Automation: Recommended
- Automation reason: стабильная негативная проверка ограничения схемы.

## ATC-007 — GET /orders/{orderId} — неизвестный заказ
- Приоритет: P1
- Operation: GET /orders/{orderId}
- Test Condition: ATCND-007
- Предусловия:
  - известен `orderId`, отсутствующий в тестовом контуре.
- Шаги:
  1. Отправить GET для неизвестного orderId.
- Ожидаемый status: 404
- Automation: Recommended
- Automation reason: типовой негативный API regression scenario.
