# Balance

## Networks

Since the Networks could receive money from a Payment Split, Networks should have a balance and their statements.

### Get Balance

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/balance/company-network`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "balance": {
    "available": 10000,
    "blocked": 0
  }
}
```

This endpoint retrieves the balance from the Network. Available is the amount that you can withdrawal, blocked is the amount that you will receive right after sell plan delay (E.g.: D+1 or D+30).

### Get Receivables

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/receivables/company-network`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "receivables": {
    "available_in_days": 4883.34,
    "qnt_available_in_days": 14
  }
}
```

Returns the how much will be available in days and how many transactions will be available right after sell play delay time (E.g.: D+1, D+30).

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/${networkToken}/receivables/company-network`

**Production**
`GET https://balance.brydge.io/v1/network/${networkToken}/receivables/company-network`

#### Query Parameters

#### Query Parameters

| Parameter | Default | Description                                                          |
| --------- | ------- | -------------------------------------------------------------------- |
| all       | false   | It returns receivables considering all companies (network + sellers) |

### Get Statements

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/statements/company-network`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "pagination": {
    "totalItems": 57,
    "totalPages": 3,
    "page": 1,
    "pageSize": 20
  },
  "statements": [
    {
      "amount": 298.98,
      "created_at": "2021-05-11T21:34:30.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Test Seller Company"
      },
      "Payment": {
        "transaction_id": "0ed2352342664449aa6ee6c64165bcfe",
        "transaction_status": "succeeded",
        "description": "Ticket: { number: 123456 }",
        "Seller": {
          "token": "c09a6212-7369-466b-9798-d8a032845cf6",
          "name": "Test Seller Company Inc.",
          "business_name": "Seller Company",
          "email": "butanta@brasilTest.com.br"
        }
      }
    }
  ]
}
```

Returns paginated statements from the Network.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/${networkToken}/statements/company-network`

**Production**
`GET https://balance.brydge.io/v1/network/${networkToken}/statements/company-network`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| pageSize  | 20      | How many statements' rows you want to receive per page  |

### Get Detailed Statements

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/statements/company-network/detailed`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "pagination": {
    "totalItems": 56,
    "totalPages": 2,
    "page": 1,
    "pageSize": 30
  },
  "statements": [
    {
      "amount": 298.98,
      "created_at": "2021-05-11T21:34:30.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "AUTO BRASIL ESTACIONAMENTOS E SERVICOS"
      },
      "Payment": {
        "amount": 350,
        "description": "Pagamento de ticket: { number: 123456 }",
        "installments": 1,
        "transaction_id": "0ed2352342664449aa6ee6c64165bcfe",
        "transaction_status": "succeeded",
        "receivers": [
          {
            "type": "seller",
            "token": "c09a6212-7369-466b-9798-d8a032845cf6",
            "amount": 300,
            "percentage": 0,
            "finalAmount": 298.98,
            "name": "BRASILTest BUTANTÃ"
          },
          {
            "type": "company_network",
            "token": "9460246d-3c0e-4318-8874-5f7acca63efb",
            "amount": 50,
            "percentage": 0,
            "finalAmount": 49.83,
            "name": "Brasil Test"
          }
        ],
        "created_at": "2021-05-11T21:34:30.000Z",
        "updated_at": "2021-05-11T21:34:30.000Z",
        "Customer": {
          "token": "6e790424-9ccb-46d5-a438-da224048c895",
          "first_name": "Michelle",
          "last_name": "Silva",
          "email": "michelle.brydgeer@brydge.com.br"
        },
        "Seller": {
          "token": "c09a6212-7369-466b-9798-d8a032845cf6",
          "name": "AUTO BRASIL ESTACIONAMENTOS E SERVICOS",
          "business_name": "BRASILTest BUTANTÃ",
          "email": "butanta@brasilTest.com.br"
        },
        "BrydgeCreditCardSellPlan": {
          "name": "D+1",
          "days_to_be_available": 1
        },
        "Card": {
          "last4_digits": "************5497",
          "token": "7f76eca3-9922-411a-89f8-aa7973c67e70",
          "card_brand": "Visa"
        },
        "Subscriber": null,
        "fees": 1.19,
        "availableOn": "2021-05-12T21:34:30.000Z"
      }
    },
    ...
  ],
}
```

This endpoint gets the detailed statements from the Network with pagination

#### HTTP Request

**Sandbox**<br />
`GET https://balance.brydge.com.br/v1/network/${networkToken}/statements/company-network/detailed`

**Production**<br />
`GET https://balance.brydge.io/v1/network/${networkToken}/statements/company-network/detailed`

#### Query Parameters

| Parameter | Default | Description                                                                       |
| --------- | ------- | --------------------------------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List                           |
| pageSize  | 20      | How many statements' rows you want to receive per page                            |
| all       | false   | It counts all companies from network (network + seller) instead of network itself |

### Sum Payments from Last Months

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const monthsQuantity = 2;
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(
  `/v1/network/${networkToken}/statements/company-network/sum/months/${monthsQuantity}/last`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "sum": [
    [
      {
        "month": January,
        "quantity": 157
      }
    ],
    [
      {
        "month": December,
        "quantity": 233
      }
    ]
  ]
}
```

This endpoint summarizes the payments from the last months from a specific Network.

#### HTTP Request

**Sandbox**<br />
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/company-network/sum/months/:monthsQuantity/last`

**Production**<br />
`GET https://balance.brydge.io/v1/network/:networkToken/statements/company-network/sum/months/:monthsQuantity/last`

#### Query Parameters

None.

### Sum Payments by Period

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const type = "day";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/statements/company-network/sum/${type}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "sum": {
    "total": 25,
    "quantity": 1
  }
}
```

This endpoint summarizes the payments made in a Network on this period.

#### Periods List

| Type    | Description                                           |
| ------- | ----------------------------------------------------- |
| daily   | It summarizes all payments made on this current day   |
| weekly  | It summarizes all payments made on this current week  |
| monthly | It summarizes all payments made on this current month |
| total   | It summarizes all payments made all the time          |

#### HTTP Request

**Sandbox**<br />
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/company-network/sum/:type`

**Production**<br />
`GET https://balance.brydge.io/v1/network/:networkToken/statements/company-network/sum/:type`

#### Query Parameters

None.

## Sellers

Since the Sellers will receive payments or could receive money from a Payment Split, Sellers should have a balance and their statements.

### Get Balance

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "e3eebad7-882f-4ae3-86e0-60a679ea7e0b";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/balance/seller/${sellerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "balance": {
    "available": 10000,
    "blocked": 0
  }
}
```

This endpoint retrieves the balance from the Network. Available is the amount that you can withdrawal, blocked is the amount that you will receive right after sell plan delay (E.g.: D+1 or D+30).

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/${networkToken}/balance/seller/${sellerToken}`

**Production**
`GET https://balance.brydge.io/v1/network/${networkToken}/balance/seller/${sellerToken}`

#### Query Parameters

None.

### Get Receivables

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "e3eebad7-882f-4ae3-86e0-60a679ea7e0b";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/receivables/seller/${sellerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "receivables": {
    "available_in_days": 4883.34,
    "qnt_available_in_days": 14
  }
}
```

Returns the how much will be available in days and how many transactions will be available right after sell play delay time (E.g.: D+1, D+30).

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/${networkToken}/receivables/seller/:sellerToken`

**Production**
`GET https://balance.brydge.io/v1/network/${networkToken}/receivables/seller/:sellerToken`

#### Query Parameters

None.

### Get Statements

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "e3eebad7-882f-4ae3-86e0-60a679ea7e0b";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/statements/seller/${sellerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "pagination": {
    "totalItems": 57,
    "totalPages": 3,
    "page": 1,
    "pageSize": 20
  },
  "statements": [
    {
      "amount": 298.98,
      "created_at": "2021-05-11T21:34:30.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Test Seller Company"
      },
      "Payment": {
        "transaction_id": "0ed2352342664449aa6ee6c64165bcfe",
        "transaction_status": "succeeded",
        "description": "Ticket: { number: 123456 }",
        "Seller": {
          "token": "c09a6212-7369-466b-9798-d8a032845cf6",
          "name": "Test Seller Company Inc.",
          "business_name": "Seller Company",
          "email": "butanta@brasilTest.com.br"
        }
      }
    },
```

Returns paginated statements from the Seller.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/${networkToken}/statements/company-network`

**Production**
`GET https://balance.brydge.io/v1/network/${networkToken}/statements/company-network`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| pageSize  | 20      | How many statements' rows you want to receive per page  |

### Get Detailed Statements

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "e3eebad7-882f-4ae3-86e0-60a679ea7e0b";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/statements/seller/${sellerToken}/detailed`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "pagination": {
    "totalItems": 58,
    "totalPages": 3,
    "page": 1,
    "pageSize": 20
  },
  "statements": [
    {
      "amount": 31.89,
      "created_at": "2021-04-22T18:04:55.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Gabriel Ávila"
      },
      "Receiver": {
        "name": "Brasil Test Paulista"
      },
      "Payment": {
        "amount": 40,
        "description": "Pagamento de ticket: { number: 123456 }",
        "installments": 1,
        "transaction_id": "f786746eac5d43c6bb2c0ad907233810",
        "transaction_status": "succeeded",
        "receivers": [
          {
            "type": "seller",
            "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
            "amount": 0,
            "percentage": 80,
            "finalAmount": 31.89,
            "name": "Brasil Test Paulista"
          },
          {
            "type": "company_network",
            "token": "9460246d-3c0e-4318-8874-5f7acca63efb",
            "amount": 0,
            "percentage": 20,
            "finalAmount": 7.97,
            "name": "Brasil Test"
          }
        ],
        "created_at": "2021-04-22T18:04:55.000Z",
        "updated_at": "2021-04-22T18:04:55.000Z",
        "Customer": {
          "token": "e3425b1e-9898-4aea-89c8-8331556bb241",
          "first_name": "Gabriel",
          "last_name": "Ávila",
          "email": "avilabiel@gmail.com"
        },
        "Seller": {
          "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
          "name": "Brasil Test Paulista LTDA",
          "business_name": "Brasil Test Paulista",
          "email": "paulista@brasiltest.com.br"
        },
        "BrydgeCreditCardSellPlan": {
          "name": "D+1",
          "days_to_be_available": 1
        },
        "Card": {
          "last4_digits": "************4014",
          "token": "cb313490-d3ad-408e-8227-b36c26e20b0a",
          "card_brand": "MasterCard"
        },
        "Subscriber": null,
        "fees": 0.14,
        "availableOn": "2021-04-23T18:04:55.000Z"
      }
    },
    ...
  ],
},
```

This endpoint gets the detailed statements from the Seller with pagination.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/seller/:sellerToken/detailed`

**Production**
`GET https://balance.brydge.io/v1/network/:networkToken/statements/seller/:sellerToken/detailed`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| pageSize  | 20      | How many statements' rows you want to receive per page  |

## Customers

### Get Statements

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const customerToken = "382184a-382d-hsa3-4882-849c932jduw";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});


const response = await axios.get(`/v1/network/${networkToken}/statements/customer/:${customerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "pagination": {
    "totalItems": 57,
    "totalPages": 3,
    "page": 1,
    "pageSize": 20
  },
  "statements": [
    {
      "amount": 298.98,
      "created_at": "2021-05-11T21:34:30.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Test Seller Company"
      },
      "Payment": {
        "transaction_id": "0ed2352342664449aa6ee6c64165bcfe",
        "transaction_status": "succeeded",
        "description": "Ticket: { number: 123456 }",
        "Seller": {
          "token": "c09a6212-7369-466b-9798-d8a032845cf6",
          "name": "Test Seller Company Inc.",
          "business_name": "Seller Company",
          "email": "butanta@brasilTest.com.br"
        }
      }
    }
  ]
}
```

This endpoint gets the statements from the Customer with pagination.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/customer/:customerToken`

**Production**
`GET https://balance.brydge.io/v1/network/:networkToken/statements/customer/:customerToken`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| pageSize  | 20      | How many statements' rows you want to receive per page  |

### Get Detailed Statements

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const customerToken = "382184a-382d-hsa3-4882-849c932jduw";
const brydgeSandboxURL = "https://balance.brydge.com.br";
const api = axios.axios.create({
  baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/statements/customer/${customerToken}/detailed`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "pagination": {
    "totalItems": 58,
    "totalPages": 3,
    "page": 1,
    "pageSize": 20
  },
  "statements": [
    {
      "amount": 31.89,
      "created_at": "2021-04-22T18:04:55.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Gabriel Ávila"
      },
      "Receiver": {
        "name": "Brasil Test Paulista"
      },
      "Payment": {
        "amount": 40,
        "description": "Pagamento de ticket: { number: 123456 }",
        "installments": 1,
        "transaction_id": "f786746eac5d43c6bb2c0ad907233810",
        "transaction_status": "succeeded",
        "receivers": [
          {
            "type": "seller",
            "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
            "amount": 0,
            "percentage": 80,
            "finalAmount": 31.89,
            "name": "Brasil Test Paulista"
          },
          {
            "type": "company_network",
            "token": "9460246d-3c0e-4318-8874-5f7acca63efb",
            "amount": 0,
            "percentage": 20,
            "finalAmount": 7.97,
            "name": "Brasil Test"
          }
        ],
        "created_at": "2021-04-22T18:04:55.000Z",
        "updated_at": "2021-04-22T18:04:55.000Z",
        "Customer": {
          "token": "e3425b1e-9898-4aea-89c8-8331556bb241",
          "first_name": "Gabriel",
          "last_name": "Ávila",
          "email": "avilabiel@gmail.com"
        },
        "Seller": {
          "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
          "name": "Brasil Test Paulista LTDA",
          "business_name": "Brasil Test Paulista",
          "email": "paulista@brasiltest.com.br"
        },
        "BrydgeCreditCardSellPlan": {
          "name": "D+1",
          "days_to_be_available": 1
        },
        "Card": {
          "last4_digits": "************4014",
          "token": "cb313490-d3ad-408e-8227-b36c26e20b0a",
          "card_brand": "MasterCard"
        },
        "Subscriber": null,
        "fees": 0.14,
        "availableOn": "2021-04-23T18:04:55.000Z"
      }
    },
    ...
  ],
},
```

This endpoint gets the detailed statements from the Customer with pagination.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/customer/:customerToken/detailed `

**Production**
`GET https://balance.brydge.io/v1/network/:networkToken/statements/customer/:customerToken/detailed`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| pageSize  | 20      | How many statements' rows you want to receive per page  |
