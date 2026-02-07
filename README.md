## Project: PropTech Platform - Construction Deals & Requests (Auth-service - Registration)
>PropTech / платформа заявок и сделок - регистрация и подтверждение email через REST API (FE-BE контракт)

**Цель:** зафиксировать договоренности FE-BE по блоку регистрации для MVP и сделать поведение API предсказуемым для реализации и приемки.

**Что сделано:** подготовлен пакет API-документации auth-service как единый источник договоренностей по регистрации:
- контракт запросов/ответов (OpenAPI),
- описание эндпоинтов с примерами payload,
- единый стандарт ошибок (единый формат ErrorResponse + матрица HTTP-кодов по сценариям).

**Функциональный scope:**
- `POST /auth/register` - создание аккаунта
- `POST /auth/verify` - подтверждение email по коду
- `POST /auth/request_verification_code/` - повторная отправка кода (rate limit/cooldown)

**Нефункциональные договоренности:**
- единый формат ошибок для всех методов (ErrorResponse),
- поддержка диагностируемости (служебные поля для трассировки в ошибках),
- правила обработки ограничений на повторные запросы (через `429` и `Retry-After`).

**Security scope:** вынесен в отдельную часть документации (не входит в текущий пакет регистрации).

**Артефакты:**
- [`Auth-service API (Registration) - OpenAPI Contract.md`](https://github.com/goodwintt23-cpu/project-07-auth-service-rest-api/blob/main/01.Auth-service%20API%20(Registration)%20-%20OpenAPI%20Contract.md#auth-service-api-registration---openapi-contract)
- [`Auth-service API (Registration) - Endpoints.md`](https://github.com/goodwintt23-cpu/project-07-auth-service-rest-api/blob/main/02.Auth-service%20API%20(Registration)%20-%20Endpoints.md)
- [`Ошибки и коды ответов API (auth-service).md`](https://github.com/goodwintt23-cpu/project-07-auth-service-rest-api/blob/main/03.%D0%9E%D1%88%D0%B8%D0%B1%D0%BA%D0%B8%20%D0%B8%20%D0%BA%D0%BE%D0%B4%D1%8B%20%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D0%BE%D0%B2%20API%20(auth-service).md)
