# AI QA Agent — Public Demo

**AI QA Agent — desktop-инструмент для автоматизации QA workflow: от анализа требований и OpenAPI до тест-дизайна и генерации автотестов.**

Публичный репозиторий показывает возможности проекта на demo-данных. Полный исходный код и внутренние промпты хранятся в private repository.

## Что умеет

- **UI / Web:** анализ требований, выявление пробелов и рисков, Test Plan, Test Conditions, Test Cases, Traceability Matrix и QA Review.
- **API:** анализ OpenAPI / Swagger, endpoint'ов, параметров, request/response schemas, status codes, авторизации, негативных и граничных сценариев.
- **Traceability:** связь `Requirement → Test Condition → Test Case → Automated Test`.
- **Automation candidates:** агент оценивает кейсы как `Recommended / Optional / Manual`, после чего QA выбирает, что автоматизировать.
- **Генерация автотестов:** Python или Java для UI и API.
- **Нагрузочное тестирование API:** генерация проектов для k6, Locust, Gatling и JMeter.

## Automation stacks

| Направление | Python | Java |
|---|---|---|
| UI | pytest + Playwright + Allure | JUnit 5 + Selenium + Allure |
| API | pytest + httpx + jsonschema + Allure | JUnit 5 + REST Assured + Jackson + AssertJ + Allure |

**Load testing:** k6 / Locust / Gatling / JMeter.

## Как работает

```text
Requirements / OpenAPI
        ↓
Analysis
        ↓
Test Plan + Questions
        ↓
Test Conditions
        ↓
Test Cases
        ↓
Traceability Matrix
        ↓
QA selects cases for automation
        ↓
Python / Java autotest project
```

Подробнее об архитектуре: [docs/architecture.md](docs/architecture.md)

## Примеры

### UI / Web

- [Requirements Analysis](examples/ui/requirements_analysis.md)
- [Test Plan](examples/ui/test_plan.md)
- [Test Conditions](examples/ui/test_conditions.md)
- [Traceability Matrix](examples/ui/traceability_matrix.md)
- [Test Cases](examples/ui/test_cases.md)
- [QA Review](examples/ui/qa_review.md)

### API

- [Sample OpenAPI](examples/api/example_openapi.yaml)
- [API Analysis](examples/api/api_analysis.md)
- [API Test Conditions](examples/api/api_test_conditions.md)
- [API Traceability Matrix](examples/api/api_traceability.md)
- [API Test Cases](examples/api/api_test_cases.md)

## Screenshots

Скриншоты актуальной версии интерфейса будут добавлены в `docs/screenshots/`.

Планируется показать:

- выбор режима UI / API;
- сформированный пакет QA-артефактов;
- выбор test cases для автоматизации;
- выбор Python / Java;
- API-режим с OpenAPI / Swagger;
- генерацию нагрузочного проекта.

## О проекте

Проект демонстрирует AI-assisted подход к QA: LLM помогает анализировать требования, проектировать проверки и генерировать код, но решение о покрытии и автоматизации остаётся за QA-инженером.
