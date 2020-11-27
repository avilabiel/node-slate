# Customers

## Basic
This endpoint creates a new customer with the basic information. To get a customer allowed to make payments, we should: 

1. Create the customer, 
2. Provide all necessary information like Phones and Addresses
3. Then, request the approval of KYC process (very quick).

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

This endpoint creates a Customer with Basic Information.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/customer`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/customer`

#### Query Parameters

None.

### Get a Customer

### Update a Customer

### Delete a Customer

## Phones
### Create a Phone

### Get a Phone

### Update a Phone

### Delete a Phone

## Addresses
### Create a Address

### Get a Address

### Update a Address

### Delete a Address

## Approval
### Request KYC Approval