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
  "statements": [
    {
      "amount": 4.8,
      "created_at": "2020-11-19T20:31:54.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Brydge"
      }
    },
    ...
  ]
}
```

This endpoint gets the statements from the Network.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/${networkToken}/statements/company-network`

**Production**
`GET https://balance.brydge.io/v1/network/${networkToken}/statements/company-network`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| limit     | 20      | How many statements' rows you want to receive per page  |

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
  "statements": [
    {
      "amount": 4.8,
      "created_at": "2020-11-19T20:31:54.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Brydge"
      },
      "Payment": {
        "amount": 25,
        "installments": 1,
        "transaction_id": "b2d8a8f52e0847168bde818632a0aba2",
        "transaction_status": "succeeded",
        "receivers": [
          {
            "type": "seller",
            "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
            "amount": 20,
            "percentage": 0,
            "finalAmount": 19.2
          },
          {
            "type": "company_network",
            "token": "9460246d-3c0e-4318-8874-5f7acca63efb",
            "amount": 5,
            "percentage": 0,
            "finalAmount": 4.8
          }
        ],
        "created_at": "2020-11-19T20:31:54.000Z",
        "updated_at": "2020-11-19T20:31:54.000Z",
        "Customer": {
          "token": "6e790424-9ccb-46d5-a438-da224048c895",
          "first_name": "Michelle",
          "last_name": "Silva",
          "email": "michelle.zooper@zoop.com.br"
        },
        "Seller": {
          "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
          "name": "Brdyge LTDA",
          "business_name": "Brydge Paulista",
          "email": "paulista@brydge.com.br"
        },
        "Card": {
          "last4_digits": "************3308",
          "token": "b44a8cd6-dd42-491e-9f52-671ef5d1ac2e",
          "card_brand": "MasterCard"
        },
        "Subscription": null,
        "fees": 1
      }
    },
    ...
  ]
}
```

This endpoint gets the detailed statements from the Network.

#### HTTP Request

**Sandbox**<br />
`GET https://balance.brydge.com.br/v1/network/${networkToken}/statements/company-network/detailed`

**Production**<br />
`GET https://balance.brydge.io/v1/network/${networkToken}/statements/company-network/detailed`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| limit     | 20      | How many statements' rows you want to receive per page  |

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
  "statements": [
    {
      "amount": 4.8,
      "created_at": "2020-11-19T20:31:54.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Brydge"
      }
    },
    ...
  ]
}
```

This endpoint gets the statements from the Seller.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/seller/:sellerToken`

**Production**
`GET https://balance.brydge.io/v1/network/:networkToken/statements/seller/:sellerToken`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| limit     | 20      | How many statements' rows you want to receive per page  |

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
  "statements": [
    {
      "amount": 4.8,
      "created_at": "2020-11-19T20:31:54.000Z",
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Brydge"
      },
      "Payment": {
        "amount": 25,
        "installments": 1,
        "transaction_id": "b2d8a8f52e0847168bde818632a0aba2",
        "transaction_status": "succeeded",
        "receivers": [
          {
            "type": "seller",
            "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
            "amount": 20,
            "percentage": 0,
            "finalAmount": 19.2
          },
          {
            "type": "company_network",
            "token": "9460246d-3c0e-4318-8874-5f7acca63efb",
            "amount": 5,
            "percentage": 0,
            "finalAmount": 4.8
          }
        ],
        "created_at": "2020-11-19T20:31:54.000Z",
        "updated_at": "2020-11-19T20:31:54.000Z",
        "Customer": {
          "token": "6e790424-9ccb-46d5-a438-da224048c895",
          "first_name": "Michelle",
          "last_name": "Silva",
          "email": "michelle.zooper@zoop.com.br"
        },
        "Seller": {
          "token": "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
          "name": "Brdyge LTDA",
          "business_name": "Brydge Paulista",
          "email": "paulista@brydge.com.br"
        },
        "Card": {
          "last4_digits": "************3308",
          "token": "b44a8cd6-dd42-491e-9f52-671ef5d1ac2e",
          "card_brand": "MasterCard"
        },
        "Subscription": null,
        "fees": 1
      }
    },
    ...
  ]
}
```

This endpoint gets the detailed statements from the Seller.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/seller/:sellerToken/detailed`

**Production**
`GET https://balance.brydge.io/v1/network/:networkToken/statements/seller/:sellerToken/detailed`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| limit     | 20      | How many statements' rows you want to receive per page  |

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
  "statements": [
    {
      "amount": 10,
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Brydge Loja 1 LTDA"
      },
      "created_at": "2021-01-14T18:14:48.000Z"
    }
  ]
}
```

This endpoint gets the statements from the Customer.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/customer/:customerToken`

**Production**
`GET https://balance.brydge.io/v1/network/:networkToken/statements/customer/:customerToken`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| limit     | 20      | How many statements' rows you want to receive per page  |

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
  "statements": [
    {
      "amount": 10,
      "Source": {
        "name": "Credit Card"
      },
      "Sender": {
        "name": "Michelle Silva"
      },
      "Receiver": {
        "name": "Brydge Loja 1 LTDA"
      },
      "created_at": "2021-01-14T18:14:48.000Z",
      "Payment": {
        "amount": 10,
        "transaction_id": "c3164061bf3b4d1fb05986e94e01a33a",
        "transaction_status": "succeeded",
        "receivers": [
          {
            "type": "seller",
            "token": "dc89106e-312e-4fc6-a878-56d6c8d356b1",
            "amount": 10,
            "finalAmount": 10
          }
        ],
        "fees": 0,
        "created_at": "2021-01-14T18:14:48.000Z",
        "updated_at": "2021-01-14T18:14:48.000Z"
      }
    }
  ]
}
```

This endpoint gets the detailed statements from the Customer.

#### HTTP Request

**Sandbox**
`GET https://balance.brydge.com.br/v1/network/:networkToken/statements/customer/:customerToken/detailed `

**Production**
`GET https://balance.brydge.io/v1/network/:networkToken/statements/customer/:customerToken/detailed`

#### Query Parameters

| Parameter | Default | Description                                             |
| --------- | ------- | ------------------------------------------------------- |
| page      | 1       | The current page that you want from the Statements List |
| limit     | 20      | How many statements' rows you want to receive per page  |
