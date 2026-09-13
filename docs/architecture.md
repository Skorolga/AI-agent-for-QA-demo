# Архитектура AI QA Agent

## 1. Входные данные

### UI / Web
- TXT
- Markdown
- DOCX
- PDF

### API
- OpenAPI 3.x
- Swagger 2.0
- JSON / YAML

## 2. Аналитический слой

Для UI/Web агент анализирует:

- функциональные требования;
- пользовательские сценарии;
- роли;
- данные и состояния;
- интеграции;
- нефункциональные требования;
- неоднозначности;
- риски.

Для API дополнительно анализируются:

- endpoints;
- HTTP methods;
- request/response contracts;
- parameters;
- schemas;
- status codes;
- authentication;
- data constraints;
- inter-endpoint dependencies.

## 3. QA-артефакты

```text
Requirements / OpenAPI
        ↓
Analysis
        ↓
Questions
        ↓
Test Plan
        ↓
Test Conditions
        ↓
Test Cases
        ↓
Traceability Matrix
        ↓
QA Review
```

## 4. Automation layer

После формирования test cases агент оценивает пригодность кейсов к автоматизации.

```text
Test Cases
   ↓
Recommended / Optional / Manual
   ↓
QA selects cases
   ↓
Python / Java
   ↓
Automation project
```

## 5. UI automation

### Python
`pytest + Playwright + Allure`

### Java
`JUnit 5 + Selenium + Allure`

## 6. API automation

### Python
`pytest + httpx + jsonschema + Allure`

### Java
`JUnit 5 + REST Assured + Jackson + AssertJ + Allure`

## 7. Performance layer

Отдельный поток для API:

```text
Selected API scenarios
        ↓
Load profile
        ↓
k6 / Locust / Gatling / JMeter
        ↓
Load-test project
```

Профили:

- Smoke
- Load
- Stress
- Spike
- Soak

## 8. Safety

Для нагрузочного тестирования используются ограничения:

- целевой URL не захардкожен;
- `BASE_URL` передаётся через environment variable;
- нужен флаг `ALLOW_LOAD_TESTS=true`;
- destructive operations не должны запускаться по умолчанию.

## 9. Traceability

Целевая связь:

```text
Requirement
→ Test Condition
→ Test Case
→ Automation Candidate
→ Automated Test
```

Это позволяет сохранять прозрачную связь между требованиями и фактическими проверками.
