# Summary

- [Introduction](#introduction)
- [Authentication](#authentication)
- [Using the API with JSON](#using-the-api-with-json)

# API

- [Supported account types](#supported-account-types)
- [Bank codes](#bank-codes)
- [Validating data](#validating-data)

# Introduction

The Transfeera API enables external applications to communicate with your account on our platform. This document explains the methods that are available.


# Authentication

In case you want to use our API please contact us by email at contato@transfeera.com, and we will give your API key.

With the token you obtained, on every request to our API include a header with the token like this:
```
x-api-key: {token}
```

All our requests are encrypted, ContaCerta does not accept requests made with simple HTTP, only HTTPS. The base URL to the API is https://contacerta-api.transfeera.com/.

All requests to the ContaCerta API must be sent with the User-Agent header. Use this header to tell us which application and email address to contact. Here is an example of how you can identify yourself using the User-Agent header:

```
User-Agent: Company (contact@company.com)
```

# Using the API with JSON

The API only supports JSON, we will not support another format. Even if you do not use the `Content-Type: application / json; charset = utf-8` the response will be in JSON and with charset utf-8.

# Supported account types
- CONTA_CORRENTE: Current account
- CONTA_POUPANCA: Savings account
- CONTA_FACIL: "conta fácil" account for Caixa Econômica and Banco do Brasil
- ENTIDADES_PUBLICAS: "entidades públicas" account for Caixa Econômica

# Bank codes
Use the default bank code assigned by FEBRABAN. Check a full list at https://www.codigobanco.com/.

# Validating data
### Request
`POST /validate`

### Body

```json
{
  "name": "José da Silva",
  "cpf_cnpj": "55998432118",
  "bank_code": "033",
  "agency": "1234",
  "agency_digit": "",
  "account": "123456",
  "account_digit": "3",
  "account_type": "CONTA_CORRENTE"
}
```

### Response
You will get the same dta you sent, with and additional object `_validation`, that will include the result of the validation, and our suggestions, if available.

If all teh data sent is valid, you will get:
```json
"_validation": {
  "valid": true,
  "errors": []
}
```

Or, if there is something wrong, the result will be similar to this:

```json
"_validation": {
  "valid": false,
  "errors": [
    {
      "message": "Dígito da Agência não é válido",
      "field": "agency_digit",
      "suggestion": {
        "agency_digit": "3"
      }
    }
  ]
}
```
