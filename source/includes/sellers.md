# Sellers

## Basic

### Create a Seller
To get a seller allowed to receive and make payments, we should:

1. Create the seller with Basic Information
2. Provide all necessary information like Phones, Addresses, Owners and Documents (when necessary)
3. Then, request the approval of KYC process (asynchronously)

Only approved Sellers could receive and make payments on Brydge Ecosystem. Here, we are dealing with the step 1.

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/seller`, {
  seller: {
		cnpj:"90787484000153",
		name:"Brydge IO",
	  email:"teste@brydge.io",
		business_name: "Brydge IO LTDA",
		mcc: "26",
		type:"business",
		revenue:"50.000",
		establishment_format: "LTDA",
		establishment_date:"2020-10-01"
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
    "id": 3,
    "token": "c48494f1-65e0-4d17-bc36-5abc7f874a2c",
    "cnpj": "90787484000153",
    "name": "Brydge IO",
    "email": "teste@brydge.io",
    "business_name": "Brydge IO LTDA",
    "mcc": "26",
    "type": "business",
    "revenue": 50,
    "establishment_format": "LTDA",
    "establishment_date": "2020-10-01T00:00:00.000Z",
    "CompanyNetworkSellers": [
      {
        "id": 3,
        "id_company_network": 1,
        "active": true,
        "id_seller": 3,
        "updatedAt": "2020-11-23T21:39:00.001Z",
        "createdAt": "2020-11-23T21:39:00.001Z"
      }
    ],
    "updatedAt": "2020-11-23T21:38:59.709Z",
    "createdAt": "2020-11-23T21:38:59.709Z"
  }
}
```

This endpoint creates a new seller with the basic information.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller`

#### Query Parameters

None.

### Get a Seller

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${cnpj}`, {
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
    "cnpj": "01394674000180",
    "token": "7fc5e37f-5760-4848-bb9f-6a3e40977903",
    "name": "Brydge IO",
    "email": "teste@brydge.io",
    "type": "business",
    "revenue": 50,
    "establishment_format": "LTDA",
    "establishment_date": "2020-10-01T00:00:00.000Z",
    "mcc": "26",
    "statement_descriptor": "Recarga De Crédito"
  }
}
```

This endpoint takes information from a specific seller.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:cnpj`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:cnpj`

#### Query Parameters

None.

### Update a Seller

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}`, {
	seller: {
		cnpj:"83134069000135",
		name:"Brydge IO",
	  email:"teste@brydge.io",
		statement_descriptor: "Recarga De Crédito",
		mcc: "26",
		type:"business",
		revenue:"50.000",
		establishment_format: "LTDA",
		establishment_date:"2020-10-01"
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
  "msg": "Seller updated"
}
```

This endpoint updates information for a specific seller.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken`

#### Query Parameters

None.

### Delete a Seller

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.delete(`/v1/network/${networkToken}/seller/${sellerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "msg": "Seller deleted"
}
```

This endpoint delete a specific seller.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken`

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

const response = await axios.post(`/v1/network/${networkToken}/seller/${sellerToken}/phone`, {
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
    "id_company_network_seller": 3,
    "active": true,
    "area_code": 13,
    "country_code": 55,
    "number": "2583564",
    "updatedAt": "2020-11-27T19:11:44.091Z",
    "createdAt": "2020-11-27T19:11:44.091Z"
  }
}
```

This endpoint creates a new seller's phone.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/phone`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/phone`

#### Query Parameters

None.

### Get a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}/phone/${phone_id}`, {
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
    "id_company_network_seller": 1,
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

This endpoint takes information from a specific seller.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/phone/:phone_id`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/phone/:phone_id`

#### Query Parameters

None.

### Update a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}/phone/${phone_id}`, {
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
  "msg": "Seller's phone updated"
}
```

This endpoint updates information for a specific seller's phone.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/phone/:phone_id`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/phone/:phone_id`

#### Query Parameters

None.

### Delete a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.delete(`/v1/network/${networkToken}/seller/${sellerToken}/phone/${phone_id}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "msg": "Seller's phone deleted"
}
```

This endpoint delete a specific seller's phone.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/phone/:phone_id`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/phone/:phone_id`

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

const response = await axios.post(`/v1/network/${networkToken}/seller/${sellerToken}/address`, {
	address:{
			line1:"Av Americas, 500",
			line2:"Citta América",
      city:"Rio de Janeiro",
			neighborhood:"Barra da Tijuca",
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
    "id_company_network_seller": 3,
    "street": "Av Americas, 500  Citta América",
    "city": "Rio de Janeiro",
    "neighborhood": "Barra da Tijuca",
    "state": "RJ",
    "zip_code": "22845046",
    "country_code": "BR",
    "updatedAt": "2020-11-27T19:10:37.198Z",
    "createdAt": "2020-11-27T19:10:37.198Z"
  }
}
```

This endpoint creates a new seller's address.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/address`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/address`

#### Query Parameters

None.

### Get a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}/address/${address_id}`, {
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
    "id_company_network_seller": 1,
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

This endpoint takes information from a specific seller's address.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/address/:address_id`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/address/:address_id`

#### Query Parameters

None.

### Update a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}/address/${address_id}`, {
	address:{
			line1:"Av Americas, 200",
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
  "msg": "Seller's address updated"
}
```

This endpoint updates information for a specific seller's address.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/address/:address_id`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/address/:address_id`

#### Query Parameters

None.

## Owner

### Create a Owner

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/seller/${sellerToken}/owner`, {
	owner: {
		first_name: "Maria",
		last_name: "Adil",
		email: "brianbusiness3@gmail.com",
		phone_number: "3082892282",
		cpf: "94492195084",
		birthdate: "1980-12-30"
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
    "id_company_network_seller": 3,
    "first_name": "Maria",
    "last_name": "Adil",
    "email": "brianbusiness3@gmail.com",
    "phone_number": "3082892282",
    "cpf": "94492195084",
    "birthdate": "1980-12-30T00:00:00.000Z",
    "updatedAt": "2020-11-24T14:54:12.410Z",
    "createdAt": "2020-11-24T14:54:12.410Z"
  }
}
```

This endpoint creates a new seller's owner.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/owner`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/owner`

#### Query Parameters

None.

### Get a Owner

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}/owner/${owner_id}`, {
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
    "id_company_network_seller": 1,
    "first_name": "Maria",
    "last_name": "Adil",
    "email": "brianbusiness3@gmail.com",
    "phone_number": "3082892282",
    "cpf": "94492195084",
    "birthdate": "1980-12-30T00:00:00.000Z",
    "createdAt": "2020-10-20T14:43:59.000Z",
    "updatedAt": "2020-10-20T14:54:07.000Z"
  }
}
```

This endpoint takes information from a specific seller's owner.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/owner/:owner_id`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/owner/:owner_id`

#### Query Parameters

None.

### Update a Owner

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}/owner/${owner_id}`, {
	owner: {
			first_name: "Joao",
			last_name: "Adil",
			email: "brianbusiness3@gmail.com",
			phone_number: "3082892282",
			cpf: "94492195084",
			birthdate: "1980-12-30"
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
  "msg": "Seller's owner updated"
}
```

This endpoint updates information for a specific seller's phone.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/owner/:owner_id`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/owner/:owner_id`

#### Query Parameters

None.

## Approval

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/seller/${sellerToken}/approval`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "message": "Seller has been created",
  "data": {
    "id": "64820be3b0614205830e47d19b3601ee",
    "status": "pending",
    "resource": "seller",
    "type": "business",
    "description": null,
    "account_balance": "0.00",
    "current_balance": "0.00",
    "business_name": "Brydge IO",
    "business_phone": "55-13-2583564",
    "business_email": "joao.zooper@zoop.com.br",
    "business_website": null,
    "business_description": null,
    "business_opening_date": "2020-10-01",
    "business_facebook": null,
    "business_twitter": null,
    "ein": "90787484000153",
    "statement_descriptor": "Brydge IO LTDA",
    "mcc": "26",
    "business_address": {
      "line1": "Av Americas, 500  Citta América",
      "line2": null,
      "line3": null,
      "neighborhood": "Barra da Tijuca",
      "city": "Rio de Janeiro",
      "state": "RJ",
      "postal_code": "22845046",
      "country_code": "BR"
    },
    "owner": {
      "first_name": "Joao",
      "last_name": "Adil",
      "email": "brianbusiness3@gmail.com",
      "phone_number": "3082892282",
      "taxpayer_id": "94492195084",
      "birthdate": "1980-12-30",
      "address": {
        "line1": null,
        "line2": null,
        "line3": null,
        "neighborhood": null,
        "city": null,
        "state": null,
        "postal_code": null,
        "country_code": null
      }
    },
    "show_profile_online": false,
    "is_mobile": false,
    "decline_on_fail_security_code": false,
    "decline_on_fail_zipcode": false,
    "delinquent": false,
    "payment_methods": null,
    "default_debit": null,
    "default_credit": null,
    "merchant_code": null,
    "terminal_code": null,
    "uri": "/v1/marketplaces/9b6a5d460fab42549c4b3c9838863793/sellers/businesses/",
    "marketplace_id": "9b6a5d460fab42549c4b3c9838863793",
    "metadata": {},
    "created_at": "2020-11-24T14:54:35+00:00",
    "updated_at": "2020-11-24T14:54:35+00:00"
  }
}
```

This endpoint approves a new seller with the basic information.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/approval`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/approval`

#### Query Parameters

None.

### Request KYC Approval

For a seller to be approved, the following information must be sent:

1. Seller's Data
2. Seller's Phone
3. Seller's Address
4. Seller's Owner
5. Seller's Documents

Only with this information is it possible for a seller to have approval.
