# Skill — API Design

## Purpose

Diseñar y documentar APIs de TumiPay utilizando obligatoriamente el estándar corporativo de APIs como baseline contractual.

El estándar de referencia es:

```text
IT-PROD-001 — Especificación API Componentes Estándar
Versión: 01
```

Este Skill debe garantizar que todas las APIs nuevas mantengan consistencia en:

* Nomenclatura.
* Recursos.
* HTTP methods.
* Versionamiento.
* JSON.
* Headers.
* Request / Response.
* Identificadores.
* Fechas y timestamps.
* Montos.
* Errores.
* Códigos funcionales.
* Idempotencia.
* Trazabilidad.
* Seguridad.
* OpenAPI.

El estándar corporativo debe considerarse **normativo** para el diseño de APIs.

No debe sustituirse por preferencias del agente, framework, lenguaje de programación o implementación del componente.

---

# Scope

Este Skill es responsable exclusivamente del diseño arquitectónico y contractual de APIs.

Incluye:

* API resources.
* Endpoints.
* HTTP methods.
* API versioning.
* Request contracts.
* Response contracts.
* Headers.
* Query parameters.
* Path parameters.
* Error contracts.
* Functional codes.
* Validation model.
* Identifiers.
* Timestamps.
* Monetary values.
* Idempotency.
* Traceability.
* Security requirements.
* OpenAPI contracts.
* API catalog entries.
* API standards compliance.

No incluye:

* Implementación del código.
* Controllers.
* Services.
* Repositories.
* Database implementation.
* Deployment implementation.
* CI/CD.
* Provider-specific implementation.

No debe modificar silenciosamente otros dominios arquitectónicos.

---

# Authoritative API Standard

La fuente normativa para el diseño de APIs es:

```text
IT-PROD-001
Especificación API Componentes Estándar
Versión 01
```

El documento define que todas las APIs de TumiPay deben mantener un contrato homogéneo en:

* Endpoint naming.
* JSON attributes.
* Request / response.
* HTTP headers.
* Data types.
* Lengths.
* Required / optional fields.
* Identifiers.
* Dates / timestamps.
* Errors.
* Functional codes.
* Idempotency.
* Traceability.
* OpenAPI.

No reinterpretar estas reglas cuando el estándar ya define explícitamente el comportamiento.

---

# Standard Precedence

Cuando exista una definición explícita en `IT-PROD-001`, debe prevalecer sobre:

1. Preferencias del agente.
2. Preferencias del desarrollador.
3. Convenciones particulares del componente.
4. Framework utilizado.
5. Lenguaje de programación.
6. Patrones genéricos de Internet.

La precedencia es:

```text
IT-PROD-001
    ↓
Platform Architecture
    ↓
Domain / Context Contract
    ↓
Component Architecture
    ↓
Implementation
```

Una implementación nunca debe contradecir el contrato arquitectónico.

---

# Handling Missing Standards

Si `IT-PROD-001` no define un aspecto concreto:

NO inventarlo como si fuera parte del estándar.

Clasificarlo como:

```text
🔵 Derived by Architecture
🟡 Architectural Assumption
🔴 Pending Decision
```

Cuando sea necesario definir una convención adicional:

1. Identificar que el estándar no la cubre.
2. Proponer la convención.
3. Documentarla como decisión arquitectónica o estándar complementario.
4. No modificar `IT-PROD-001` automáticamente.
5. Mantener trazabilidad entre la API y la decisión.

Ejemplo:

```text
IT-PROD-001
    ↓
No define pagination model
    ↓
Architecture proposes cursor pagination
    ↓
ADR / Platform API Standard
    ↓
API contract
```

---

# Inputs

* Business capabilities.
* Domain model.
* Bounded Context.
* Component architecture.
* Integration architecture.
* API requirements.
* API standards.
* Existing API catalog.
* Existing API contracts.
* Existing OpenAPI specifications.
* Existing ADRs.
* Security requirements.
* Consumer requirements.

---

# Required Input

Antes de diseñar una API, el agente debe identificar:

```text
Domain
Bounded Context
Capability
Component
Resource
Consumer
Ownership
Security model
```

Si alguno de estos elementos es desconocido y resulta necesario para diseñar correctamente la API, debe registrarse como:

```text
Pending Decision
```

No inventar ownership.

---

# Outputs

Este Skill puede producir:

```text
API Catalog Entry
API Resource Definition
Endpoint Definition
Request Contract
Response Contract
Error Contract
OpenAPI Contract
API Examples
API Standards Compliance Report
API Traceability
```

Los contratos completos deben almacenarse en:

```text
05-api-and-integration/contracts/
```

---

# Allowed Repository Areas

Este Skill puede modificar únicamente:

```text
05-api-and-integration/api-catalog/
05-api-and-integration/api-standards/
05-api-and-integration/contracts/
13-standards/api/
14-traceability/
12-architecture-decisions/
```

`12-architecture-decisions/` y `14-traceability/` solamente cuando el diseño de la API requiera una decisión o trazabilidad adicional.

No modificar directamente:

```text
01-context/
02-domain/
03-platform-architecture/
04-components/
06-data-architecture/
07-security/
08-reliability/
09-observability/
10-infrastructure/
```

Si el diseño de la API detecta un problema en alguno de estos dominios:

* No modificarlo silenciosamente.
* Registrar el impacto.
* Crear una Open Question o ADR.
* Solicitar la actualización mediante el Skill correspondiente.

---

# Dependencies

Required:

```text
component-architecture
integration-architecture
```

Recommended:

```text
event-contracts
domain-modeling
bounded-context-design
security-architecture
architecture-traceability
architecture-review
```

---

# Operating Procedure

## Step 1 — Read Repository Instructions

Leer:

```text
AGENTS.md
```

y este Skill.

---

## Step 2 — Read API Standard

Leer el estándar:

```text
IT-PROD-001 — Especificación API Componentes Estándar
```

El agente debe utilizar el documento como baseline normativo.

---

## Step 3 — Inspect Existing APIs

Antes de crear una API:

* Buscar APIs existentes del mismo dominio.
* Buscar recursos similares.
* Buscar DTOs reutilizables.
* Buscar headers existentes.
* Buscar functional codes.
* Buscar errores.
* Buscar OpenAPI.
* Buscar convenciones específicas del dominio.

No duplicar contratos existentes.

---

# Step 4 — Identify API Context

Determinar:

```text
API ID
Domain
Bounded Context
Capability
Component
Owner
Consumers
Resource
```

La API debe tener ownership explícito.

---

# Step 5 — Design Resource

Utilizar REST.

Los recursos deben utilizar nombres plurales cuando representen colecciones.

Ejemplo:

```http
/accounts
/transactions
/beneficiaries
/transfers
```

Evitar endpoints RPC como:

```http
/createTransfer
/processTransfer
/getTransfer
```

Esta regla forma parte del estándar corporativo.

---

# Step 6 — Define Version

Todas las APIs deben incluir versión.

Formato:

```text
/v1/...
```

Ejemplo:

```http
/tp/payment/adapter/v1/payin/transaction
```

Cambios incompatibles requieren nueva versión mayor.

No modificar silenciosamente un contrato publicado.

---

# Step 7 — Define HTTP Method

Utilizar:

| Method | Purpose                     |
| ------ | --------------------------- |
| GET    | Consulta                    |
| POST   | Creación / ejecución        |
| PUT    | Reemplazo completo          |
| PATCH  | Actualización parcial       |
| DELETE | Eliminación / desactivación |

Debe evitarse el uso incorrecto de métodos HTTP.

---

# Step 8 — Apply JSON Naming Standard

Todos los atributos JSON deben utilizar:

```text
snake_case
```

Ejemplo:

```json
{
  "transaction_id": "123",
  "reference_id": "REF-001",
  "created_at": "2026-06-13T15:01:10Z"
}
```

Nunca:

```json
{
  "transactionId": "123",
  "referenceId": "REF-001",
  "createdAt": "..."
}
```

Esta regla es obligatoria.

---

# Step 9 — Define Standard Headers

Evaluar y documentar:

```text
Content-Type
X-Api-Key
X-Idempotency-Key
X-Request-ID
X-Merchant-ID
```

No todos son obligatorios para todos los endpoints.

El contrato debe indicar:

```text
Required
Optional
Conditional
```

## `X-Idempotency-Key` debe utilizarse especialmente en operaciones que crean o modifican transacciones o producen efectos financieros.

# Step 10 — Authentication and Authorization

Cada API debe documentar:

```text
Authentication
Authorization
Security Scheme
Required Headers
Scopes / Roles
Sensitive Data
Audit Requirements
```

El estándar define `X-Api-Key` para los componentes internos contemplados en el estándar.

Para APIs externas, la autenticación/autorización debe definirse explícitamente según el dominio y canal.

No asumir que `X-Api-Key` es universal para todas las APIs de TumiPay.

---

# Step 11 — Request Contract

Cada endpoint debe definir explícitamente:

```text
Name
Description
Data Type
Required / Optional / Conditional
Validation
```

Aplicar:

* snake_case.
* Longitudes.
* Formats.
* Regex.
* Enums.
* Ranges.
* Nullable.
* Required.
* Conditional requirements.

Las validaciones deben formar parte del contrato OpenAPI cuando sea posible.

---

# Step 12 — Reuse Common DTOs

Reutilizar modelos cuando la semántica sea la misma.

Ejemplos:

```text
AmountDto
DocumentDto
TransactionDto
ValidationError
```

No crear estructuras equivalentes innecesariamente.

Ejemplo incorrecto:

```text
AccountBalanceAmount
TransferAmount
PaymentAmount
TransactionAmount
```

si todos representan conceptualmente el mismo objeto.

Preferir:

```text
AmountDto
```

cuando la semántica sea realmente equivalente.

---

# Step 13 — Standard Amount Model

Para valores monetarios utilizar:

```json
{
  "value": 8000,
  "currency": "COP"
}
```

Reglas:

```text
value → Long
currency → ISO 4217
```

El valor monetario se representa en la unidad mínima de la moneda.

No utilizar:

```text
float
double
```

para dinero.

---

# Step 14 — Currency

Utilizar ISO 4217.

Ejemplo:

```json
{
  "currency": "COP"
}
```

Formato:

```text
String(3)
```

---

# Step 15 — Identifiers

Mantener identificadores semánticamente diferenciados.

Ejemplos:

```text
transaction_id
reference_id
account_id
user_id
beneficiary_id
device_id
provider_transaction_id
adapter_transaction_id
```

No reutilizar un identificador para significados diferentes.

Distinguir especialmente:

```text
transaction_id
reference_id
adapter_transaction_id
provider_transaction_id
```

porque representan diferentes niveles de identificación y trazabilidad.

---

# Step 16 — Timestamps

Utilizar:

```text
ISO 8601 UTC
```

Formato:

```text
YYYY-MM-DDTHH:mm:ss[.fraction]Z
```

Ejemplo:

```json
{
  "created_at": "2026-06-13T15:01:09.720010831Z",
  "updated_at": "2026-06-13T15:01:11.617649962Z",
  "processed_at": "2026-06-13T15:01:11.608725828Z"
}
```

No utilizar timezone local ni fechas ambiguas.

---

# Step 17 — Standard Response

Las APIs deben utilizar:

```text
BaseApiResponse<T>
```

con:

```json
{
  "code": "PROCESS_COMPLETED",
  "status": "SUCCESS",
  "message": "Operation completed successfully",
  "data": {}
}
```

Los campos estándar son:

```text
code
status
message
data
```

---

# Step 18 — Functional Code

El campo:

```text
code
```

debe:

* Ser String.
* Tener máximo 60 caracteres.
* Ser estable.
* Ser descriptivo.
* Utilizar `UPPER_SNAKE_CASE`.
* Ser independiente de `message`.
* Ser procesable programáticamente.

Ejemplos:

```text
PROCESS_COMPLETED
VALIDATION_ERROR
RESOURCE_NOT_FOUND
DUPLICATE_TRANSACTION
INTERNAL_SERVER_ERROR
PROVIDER_TRANSACTION_ERROR
```

---

# Step 19 — Status

Utilizar:

```text
SUCCESS
ERROR
FAILED
```

No utilizar `status` como sustituto de un estado de negocio.

Distinguir:

```text
operation_status
```

de:

```text
transaction_status
```

El primero representa el resultado de la operación realizada por el componente.

## El segundo representa el estado de la transacción dentro de su lifecycle.

# Step 20 — Validation Errors

Utilizar:

```json
{
  "code": "VALIDATION_ERROR",
  "status": "ERROR",
  "message": "Validation failed",
  "data": [
    {
      "field": "transaction.transaction_id",
      "message": "The transaction_id is required"
    }
  ]
}
```

Cuando existan múltiples errores:

* Retornar todos cuando sea posible.
* No solamente el primero.
* `field` debe representar la ruta del atributo.

Ejemplo:

```text
transaction.transaction_id
beneficiary.document.document_number
bank_account.account_number
metadata.merchant_id
```

---

# Step 21 — HTTP Status vs Functional Code

No utilizar HTTP status como sustituto del código funcional.

Debe existir:

```text
HTTP Status
+
Functional Code
```

Ejemplo:

```http
HTTP 400
```

con:

```json
{
  "code": "VALIDATION_ERROR",
  "status": "ERROR"
}
```

HTTP representa la categoría técnica.

`code` representa el resultado funcional.

---

# Step 22 — Enums

Cuando un campo tenga valores limitados:

* Definir enum en OpenAPI.
* Utilizar `UPPER_SNAKE_CASE`.
* Documentar valores.
* No cambiar la semántica de valores existentes.

Ejemplo:

```text
BANK_TRANSFER
CARD
CASH
QR
PSE
```

---

# Step 23 — Metadata

Utilizar:

```json
{
  "metadata": {}
}
```

únicamente para información adicional/extensible.

No utilizar `metadata` para esconder campos core del dominio.

Si un dato es parte fundamental del contrato, debe ser modelado explícitamente.

---

# Step 24 — External Provider Payloads

Cuando exista integración con proveedores:

```text
TumiPay Domain
        ↓
Provider Adapter
        ↓
Provider Contract
```

Nunca:

```text
TumiPay API
        ↓
Provider Native Payload
```

El modelo externo no debe contaminar el modelo core de TumiPay.

Cuando corresponda, evidencia técnica como:

```text
provider_request
provider_response
```

puede conservarse de acuerdo con el contrato y las políticas de seguridad.

---

# Step 25 — Transaction State

Cuando la API maneje transacciones, documentar explícitamente:

```text
transaction_status
```

y su state machine.

Estados definidos por el estándar incluyen:

```text
PENDING
APPROVED
REJECTED
EXPIRED
ERROR
CANCELLED
```

No mezclar:

```text
operation_status
```

con:

```text
transaction_status
```

Si el dominio requiere estados adicionales, registrarlos como:

```text
Derived
```

o:

```text
Pending Decision
```

según corresponda.

---

# Step 26 — Idempotency

Toda operación que pueda:

* Crear una transacción.
* Modificar estado crítico.
* Mover dinero.
* Generar efectos financieros.

debe analizarse para idempotencia.

Utilizar:

```http
X-Idempotency-Key: <unique-key>
```

El contrato debe documentar:

```text
Required / Optional
Retention
Scope
Duplicate behavior
Response behavior
```

No asumir silenciosamente el período de retención si no está definido por la plataforma.

---

# Step 27 — Pagination

Para endpoints que devuelvan colecciones debe evaluarse la necesidad de paginación.

El estándar `IT-PROD-001` **no define actualmente un modelo normativo específico de paginación**.

Por tanto:

```text
NO asumir que page/page_size es el estándar corporativo.
```

Si el API requiere paginación:

1. Revisar `13-standards/api/`.
2. Revisar APIs existentes.
3. Revisar decisiones arquitectónicas.
4. Identificar el estándar vigente.
5. Si no existe, registrar una propuesta o Pending Decision.

Nunca presentar un modelo de paginación nuevo como parte de `IT-PROD-001` sin modificar formalmente el estándar.

---

# Step 28 — Filtering

Los query parameters deben:

* Utilizar snake_case.
* Tener nombres descriptivos.
* Definir tipo.
* Definir obligatoriedad.
* Definir valores permitidos.
* Definir formato.

Ejemplo:

```http
GET /transactions?transaction_id=123
```

---

# Step 29 — OpenAPI

Toda API debe tener OpenAPI.

Debe documentar como mínimo:

```text
openapi
info
servers
tags
paths
parameters
headers
requestBody
responses
schemas
securitySchemes
```

Cada endpoint:

```text
Summary
Description
HTTP Method
Path
Parameters
Headers
Request Schema
Response Schema
Error Responses
Examples
```

---

# Step 30 — API Contract Location

El contrato completo debe vivir en:

```text
05-api-and-integration/contracts/
```

El API catalog debe contener solamente la información necesaria para catalogar y navegar las APIs.

No duplicar el contrato completo en:

```text
api-catalog/
```

---

# Step 31 — API Catalog

Cada API debe tener como mínimo:

```text
API ID
API Name
Domain
Bounded Context
Component
Owner
Consumers
Version
Base Path
Authentication
Status
Contract Reference
Related Requirements
Related Capabilities
```

---

# Step 32 — Traceability

Cada API debe mantener:

```text
Requirement
    ↓
Capability
    ↓
Domain
    ↓
Bounded Context
    ↓
Component
    ↓
API
    ↓
Data
```

Utilizar IDs estables:

```text
REQ-XXX
CAP-XXX
DOM-XXX
CTX-XXX
COMP-XXX
API-XXX
DATA-XXX
```

---

# Step 33 — API Design Review

Antes de declarar una API completa, ejecutar una revisión contra:

```text
IT-PROD-001
```

La revisión debe identificar:

```text
Compliant
Non-Compliant
Not Applicable
Pending Decision
```

No marcar como `Compliant` algo que el estándar no define.

---

# Step 34 — API Compliance Matrix

Cuando la API sea relevante o crítica, generar:

| Rule        | Standard Requirement       | API Implementation | Status           |
| ----------- | -------------------------- | ------------------ | ---------------- |
| REST        | REST                       | REST               | Compliant        |
| Version     | `/v1/...`                  | `/v1/...`          | Compliant        |
| JSON        | snake_case                 | snake_case         | Compliant        |
| Response    | BaseApiResponse            | BaseApiResponse    | Compliant        |
| Errors      | Functional code            | Defined            | Compliant        |
| Idempotency | Required when applicable   | Defined            | Compliant        |
| Pagination  | Not defined by IT-PROD-001 | Pending            | Pending Decision |
| OpenAPI     | Required                   | OpenAPI            | Compliant        |

La matriz debe diferenciar claramente:

```text
Standard requirement
vs
Architecture extension
```

---

# Step 35 — API Change Management

Cuando se modifique una API existente:

1. Identificar consumidores.
2. Identificar versión.
3. Identificar breaking change.
4. Revisar compatibilidad.
5. Revisar OpenAPI.
6. Revisar functional codes.
7. Revisar DTOs.
8. Revisar events/webhooks afectados.
9. Revisar traceability.
10. Crear ADR si la decisión es arquitectónicamente significativa.

Nunca modificar silenciosamente un contrato publicado.

---

# Rules

* `IT-PROD-001` es obligatorio.
* No inventar reglas que el estándar no define.
* No contradecir el estándar.
* Utilizar REST.
* Utilizar versionamiento.
* Utilizar `snake_case`.
* Utilizar recursos REST correctamente.
* Utilizar `BaseApiResponse`.
* Utilizar `code/status/message/data`.
* Utilizar `ValidationError`.
* Utilizar códigos funcionales estables.
* Utilizar ISO 8601 UTC.
* Utilizar identificadores semánticamente diferenciados.
* Utilizar ISO 4217.
* No utilizar float/double para dinero.
* Analizar idempotencia en operaciones críticas.
* Mantener trazabilidad.
* Generar OpenAPI.
* Reutilizar DTOs cuando la semántica sea equivalente.
* Mantener contratos externos separados del modelo core.
* No duplicar estándares.
* No modificar silenciosamente otros dominios.

---

# Forbidden

El Skill no debe:

* Crear APIs sin revisar `IT-PROD-001`.
* Crear un estándar alternativo sin ADR.
* Inventar campos estándar.
* Inventar functional codes como si fueran corporativos.
* Inventar headers obligatorios.
* Inventar un modelo de paginación como estándar corporativo.
* Copiar payloads de proveedores directamente al dominio.
* Utilizar camelCase.
* Utilizar RPC innecesario.
* Utilizar `float` / `double` para dinero.
* Hacer depender la lógica de negocio del campo `message`.
* Duplicar DTOs conceptualmente equivalentes.
* Modificar contratos publicados silenciosamente.
* Mezclar `operation_status` con `transaction_status`.

---

# Quality Gate

Una API solamente puede considerarse `READY` cuando:

## Architecture

* [ ] Domain identificado.
* [ ] Bounded Context identificado.
* [ ] Capability identificada.
* [ ] Component identificado.
* [ ] Ownership definido.
* [ ] Consumers identificados.

## Endpoint

* [ ] REST.
* [ ] Resource correctamente modelado.
* [ ] HTTP method correcto.
* [ ] Version definida.
* [ ] Path validado.

## JSON

* [ ] snake_case.
* [ ] Campos semánticamente claros.
* [ ] DTOs reutilizados cuando corresponda.
* [ ] Enums definidos.

## Request

* [ ] Headers.
* [ ] Path parameters.
* [ ] Query parameters.
* [ ] Body.
* [ ] Required / Optional / Conditional.
* [ ] Validations.

## Response

* [ ] `code`.
* [ ] `status`.
* [ ] `message`.
* [ ] `data`.
* [ ] Response DTO.
* [ ] Success example.
* [ ] Error examples.

## Errors

* [ ] HTTP status.
* [ ] Functional code.
* [ ] ValidationError.
* [ ] Business errors.
* [ ] Technical errors.

## Security

* [ ] Authentication.
* [ ] Authorization.
* [ ] Security headers.
* [ ] Sensitive fields.

## Transaction

Cuando aplique:

* [ ] Idempotency.
* [ ] Transaction state.
* [ ] Operation state.
* [ ] Retry behavior.
* [ ] Concurrency.
* [ ] Reversal / compensation.

## Money

Cuando aplique:

* [ ] Amount model.
* [ ] Integer monetary values.
* [ ] Currency.
* [ ] Currency scale.

## Traceability

* [ ] X-Request-ID.
* [ ] Business identifiers.
* [ ] Correlation.
* [ ] Audit requirements.

## Documentation

* [ ] OpenAPI.
* [ ] Examples.
* [ ] Error examples.
* [ ] Catalog entry.
* [ ] Traceability.
* [ ] Compliance matrix.

---

# Final Rule

> **Every TumiPay API must comply with IT-PROD-001 unless an explicit architectural decision defines an approved extension or exception.**

The agent must never silently override the corporate API standard.

When the standard does not define a behavior, the agent must distinguish:

```text
Corporate Standard
        ↓
Architecture Decision
        ↓
API Contract
```

rather than presenting an architectural convention as if it were already part of the corporate standard.
