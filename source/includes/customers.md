# Customers

## Basic
To get a customer allowed to make payments, we should:

1. Create the customer with Basic Information
2. Provide all necessary information like Phones, Addresses
3. Then, request the approval of KYC process (synchronously)

Only approved Customers could make payments on Brydge Ecosystem. Here, we are dealing with the step 1.

### Create a Customer

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/customer`, {
	customer: {
        cpf: "41235235214",
        first_name: "Rafael",
        last_name: "Silva",
        email: "teste@gmail.com",
        birthdate: "1985-03-21"
	}
}, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "id": 1,
    "cpf": "41235235214",
    "token": "cf157c3d-5295-4251-ba9d-04ffceeba971",
    "id_zoop": null,
    "first_name": "Rafael",
    "last_name": "Silva",
    "email": "teste@gmail.com",
    "birthdate": "1985-03-21T00:00:00.000Z",
    "createdAt": "2020-01-30T13:28:47.000Z",
    "updatedAt": "2020-01-30T13:28:47.000Z"
  }
}
```

This endpoint creates a new customer with the basic information.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer`

#### Query Parameters

None.

### Get a Customer

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/customer/${cpf}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "cpf": "41235235214",
    "token": "cf157c3d-5295-4251-ba9d-04ffceeba971",
    "first_name": "Rafael",
    "last_name": "Silva",
    "email": "teste@gmail.com",
    "birthdate": "1985-03-21T00:00:00.000Z"
  }
}
```

This endpoint takes information from a specific customer.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer/:cpf`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer/:cpf`

#### Query Parameters

None.

### Update a Customer

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/customer/${customerToken}`, {
	customer: {
        cpf: "41235235214",
        first_name: "Rafael",
        last_name: "Silva",
        email: "teste@gmail.com",
        birthdate: "1985-03-21"
	}
}, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "msg": "Customer updated"
}
```

This endpoint updates information for a specific customer.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer/:customerToken`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer/:customerToken`

#### Query Parameters

None.

### Delete a Customer

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.delete(`/v1/network/${networkToken}/customer/${customerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "msg": "Customer deleted"
}
```

This endpoint delete a specific customer.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer/:customerToken`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer/:customerToken`

#### Query Parameters

None.

## Phones

### Create a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/customer/${customerToken}/phone`, {
	phone:{
		 area_code: 13,
		 country_code:55,
		 number: "2583564"
	 }
}, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "id": 1,
    "id_company_network_customer": 3,
    "active": true,
    "area_code": 13,
    "country_code": 55,
    "number": "2583564",
    "updatedAt": "2020-11-27T19:11:44.091Z",
    "createdAt": "2020-11-27T19:11:44.091Z"
  }
}
```

This endpoint creates a new customer's phone.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/customer/:customerToken/phone`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/customer/:customerToken/phone`

#### Query Parameters

None.

### Get a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/customer/${customerToken}/phone/${phone_id}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "data": {
    "id": 1,
    "id_company_network_customer": 1,
    "area_code": 13,
    "country_code": 55,
    "number": "2583564",
    "active": true,
    "deleted_at": "2020-10-20T14:34:21.000Z",
    "createdAt": "2020-10-20T14:05:59.000Z",
    "updatedAt": "2020-10-20T14:34:21.000Z"
  }
}
```

This endpoint takes information from a specific customer.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/customer/:customerToken/phone/:phone_id`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/customer/:customerToken/phone/:phone_id`

#### Query Parameters

None.

### Update a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/customer/${customerToken}/phone/${phone_id}`, {
	phone:{
		 area_code: 13,
		 country_code:55,
		 number: "23456789"
	 }
}, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "msg": "Customer's phone updated"
}
```

This endpoint updates information for a specific customer's phone.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer/:customerToken/phone/:phone_id`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer/:customerToken/phone/:phone_id`

#### Query Parameters

None.

### Delete a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.delete(`/v1/network/${networkToken}/customer/${customerToken}/phone/${phone_id}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "msg": "Customer's phone deleted"
}
```

This endpoint delete a specific customer's phone.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/customer/:customerToken/phone/:phone_id`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/customer/:customerToken/phone/:phone_id`

#### Query Parameters

None.

## Addresses

### Create a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/customer/${customerToken}/address`, {
	address:{
			line1:"Av Americas, 500",
			line2:"Citta América",
			neighborhood:"Barra da Tijuca",
			city:"Rio de Janeiro",
			state:"RJ",
			zip_code:"22845046",
			country_code:"BR"
		}
}, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "data": {
    "id": 1,
    "id_company_network_customer": 3,
    "street": "Av Americas, 500  Citta América",
    "neighborhood": "Barra da Tijuca",
    "city": "Rio de Janeiro",
    "state": "RJ",
    "zip_code": "22845046",
    "country_code": "BR",
    "updatedAt": "2020-11-27T19:10:37.198Z",
    "createdAt": "2020-11-27T19:10:37.198Z"
  }
}
```

This endpoint creates a new customer's address.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer/:customerToken/address`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer/:customerToken/address`

#### Query Parameters

None.

### Get a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/customer/${customerToken}/address/${address_id}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "data": {
    "id": 1,
    "id_company_network_customer": 1,
    "state": "RJ",
    "city": "Rio de Janeiro",
    "zip_code": "22845046",
    "street": "Av Americas, 500  Citta América",
    "complement": null,
    "neighborhood": "Barra da Tijuca",
    "country_code": "BR",
    "createdAt": "2020-10-20T14:04:53.000Z",
    "updatedAt": "2020-10-20T14:32:09.000Z"
  }
}
```

This endpoint takes information from a specific customer's address.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/customer/:customerToken/address/:address_id`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/customer/:customerToken/address/:address_id`

#### Query Parameters

None.

### Update a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/customer/${customerToken}/address/${address_id}`, {
	address:{
			line1:"AAv Americas, 200",
			line2:"Citta América",
			city:"Rio de Janeiro",
			state:"RJ",
		  neighborhood:"Barra da Tijuca",
			zip_code:"22845046",
			country_code:"BR"
		}
}, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "msg": "Customer's address updated"
}
```

This endpoint updates information for a specific customer's address.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/customer/:customerToken/address/:address_id`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/customer/:customerToken/address/:address_id`

#### Query Parameters

None.

## Approval

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/customer/${customerToken}/approval`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "message": "Customer has been created",
  "data": {
    "id": "99c94033afbe48aa81c11edbcf60ede9",
    "status": "active",
    "resource": "buyer",
    "account_balance": "0.00",
    "current_balance": "0.00",
    "first_name": "michellexx",
    "last_name": "teste",
    "taxpayer_id": "86446184077",
    "description": null,
    "email": "michelle.zooper@zoop.com.br",
    "phone_number": "55-13-2583564",
    "facebook": null,
    "twitter": null,
    "address": {
      "line1": "Av Americas, 500  Citta América",
      "line2": null,
      "line3": null,
      "neighborhood": "Barra da Tijuca",
      "city": "Rio de Janeiro",
      "state": "RJ",
      "postal_code": "22845046",
      "country_code": "BR"
    },
    "delinquent": false,
    "payment_methods": null,
    "default_debit": null,
    "default_credit": null,
    "default_receipt_delivery_method": null,
    "uri": "/v1/marketplaces/9b6a5d460fab42549c4b3c9838863793/buyers/99c94033afbe48aa81c11edbcf60ede9",
    "metadata": {},
    "created_at": "2020-11-27T19:12:04+00:00",
    "updated_at": "2020-11-27T19:12:04+00:00"
  }
}
```

This endpoint approves a new customer with the basic information.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer/:customerToken/approval`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer/:customerToken/approval`

#### Query Parameters

None.

### Request KYC Approval

For a customer to be approved, the following information must be sent:

1. Customer's data
2. Phones
3. Address

Only with this information is it possible for a customer to have approval.
