---
id: activation-codes
title: Activation Codes
---

Contains the information about Activation Codes in the mediQuo ecosystem.

### Authentication and rate limits

| Authentication                                | Rate limits             |
| --------------------------------------------- | ----------------------- |
| [HTTP Headers](/docs/overview#authentication) | 600 requests per minute |

Learn more about [rate limits](/docs/overview#rate-limiting).

### Attributes

| Name       | Type                  | Description                                                   |
| ---------- | --------------------- | ------------------------------------------------------------- |
| code       | string                | The activation code                                           |
| tag        | string **(optional)** | The value that identifies your activation code in your system |
| active     | boolean               | If the activation code is active or not                       |
| expires_at | string **(optional)** | The date when the activation code will be unavailable         |

## Create Activation Code

```
POST /v1/activation-codes
```

### Endpoint URL

`https://sdk.mediquo.com/v1/activation-codes`

### Request parameters

| Name | Type   | Description                                                   |
| ---- | ------ | ------------------------------------------------------------- |
| code | string | The code that the user will introduce                         |
| tag  | string | The value that identifies your activation code in your system |

#### Example request

```json
{
  "code": "MYTESTCODE123",
  "tag": "2020123ABC"
}
```

### Response fields

| Name    | Type   | Description      |
| ------- | ------ | ---------------- |
| message | string | Response message |

### Default response

```json
Status: 200 OK
```

```json
{
  "message": "Success"
}
```

## Get Activation Codes

```
GET /v1/activation-codes
```

Use this endpoint to retrieve activation codes. Can be filtered with query params for the given tag.

### Endpoint URL

`https://sdk.mediquo.com/v1/activation-codes`

### Query parameters

| Name | Type    | Description                                                   |
| ---- | ------- | ------------------------------------------------------------- |
| code | string  | The activation code                                           |
| tag  | string  | The value that identifies your activation code in your system |
| page | integer | Pagination page                                               |

### Response fields

| Name       | Type    | Description                                                   |
| ---------- | ------- | ------------------------------------------------------------- |
| code       | string  | The activation code                                           |
| tag        | string  | The value that identifies your activation code in your system |
| active     | boolean | If the activation code is active or not                       |
| created_at | string  | The creation date of the activation code                      |

### Default response

```json
Status: 200 OK
```

```json
{
  "code": "MYTESTCODE123",
  "tag": "2020123ABC",
  "active": true
}
```

## Activate Activation Code

```
PUT /v1/activation-codes/<code>/activate
```

Use this endpoint to reactivate an activation code

### Endpoint URL

`https://sdk.mediquo.com/v1/activation-codes/<id>/activate`

### Request parameters

| Name | Type   | Description     |
| ---- | ------ | --------------- |
| code | string | Activation code |

### Response fields

| Name    | Type   | Description      |
| ------- | ------ | ---------------- |
| message | string | Response message |

### Default response

```json
Status: 200 OK
```

```json
{
  "message": "Success"
}
```

## Deactivate Activation Code

```
PUT /v1/activation-codes/<id>/deactivate
```

Use this endpoint to deactivate an activation code.

### Endpoint URL

`https://sdk.mediquo.com/v1/activation-codes/<code>/deactivate`

### Request parameters

| Name | Type   | Description     |
| ---- | ------ | --------------- |
| code | string | Activation code |

### Response fields

| Name    | Type   | Description      |
| ------- | ------ | ---------------- |
| message | string | Response message |

### Default response

```json
Status: 200 OK
```

```json
{
  "message": "Success"
}
```
## Send Activation Code

```
PUT /v1/activation-codes/<id>/send
```

Use this endpoint to send a notification to the user with the generated activation code. This will send an email and/or an SMS depending of the information you provided in the request.

> This endpoint by default is disabled. To be able to use it, you should request access to your mediQuo account manager

### Endpoint URL

`https://sdk.mediquo.com/v1/activation-codes/<code>/send`

### Request parameters

| Name | Type   | Description     |
| ---- | ------ | --------------- |
| name | string | Patient name |
| prefix | string **(required if phone is set)** | Patient prefix (`+34`) |
| phone | string **(required if prefix is set)** | Patient phone |
| email | string **(optional)** | Patient email |
| language | string **(optional)** | Language of message (only for email). Accepted languages 'es', 'en', 'pt , 'de'. Default: 'es' |

### Response fields

| Name    | Type   | Description      |
| ------- | ------ | ---------------- |
| message | string | Response message |

### Default response

```json
Status: 200 OK
```
```json
{
  "message": "Success"
}
```