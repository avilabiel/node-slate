# Subscriptions

### Get Subscription

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const subscriptionToken = "7246623f-4c38-461c-bb8f-230e9eb57a43";
const brydgeSandboxURL = "https://cashin.brydge.com.br";
const api = axios.axios.create({
  baseURL: brydgeSandboxURL,
});

const response = await axios.get(
    `/v1/network/${networkToken}/payment/credit-card/subscription/${subscriptionToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "sucess": true,
  "subscription": {
    "token": "7246623f-4c38-461c-bb8f-230e9eb57a43",
    "first_billing_date": "2020-12-17",
    "next_billing_date": "2020-12-25",
    "amount": 3,
    "description": "Weekly plan",
    "finished_at": null,
    "active": true,
    "createdAt": "2020-12-25T03:00:00.000Z",
    "updatedAt": null
  }
}
```

#### HTTP Request

**Sandbox**
`GET https://cashin.brydge.com.br/v1/network/:networkToken/payment/credit-card/subscription/:subscriptionToken`

**Production**
`GET https://cashin.brydge.io/v1/network/:networkToken/payment/credit-card/subscription/:subscriptionToken`

#### Query Parameters

None.

### Cancel Subscription

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const subscriptionToken = "7246623f-4c38-461c-bb8f-230e9eb57a43";
const brydgeSandboxURL = "https://cashin.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});
const response = await axios.delete(`/v1/network/${networkToken}/credit-card/subscription/${subscriptionToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "message": "Canceled Subscription"
}
```

This endpoint cancels a specific subscription.

#### HTTP Request

**Sandbox**
`DELETE https://cashin.brydge.com.br/v1/network/:networkToken/payment/credit-card/subscription/:subscriptionToken`

**Production**
`DELETE https://cashin.brydge.io/v1/network/:networkToken/payment/credit-card/subscription/:subscriptionToken`

#### Query Parameters

None.

### Get All Subscriptions

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://cashin.brydge.com.br";
const api = axios.axios.create({
  baseURL: brydgeSandboxURL,
});

const response = await axios.get(
    `/v1/network/${networkToken}/payment/credit-card/subscriptions`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "sucess": true,
  "subscription": [
    {
      "token": "7246623f-4c38-461c-bb8f-230e9eb57a43",
      "first_billing_date": "2020-12-17",
      "next_billing_date": "2020-12-25",
      "amount": 3,
      "description": "Weekly Plan",
      "finished_at": null,
      "active": true,
      "createdAt": "2020-12-25T03:00:00.000Z",
      "updatedAt": null
    },
    {
      "token": "1286623f-4c38-461c-bb8f-230e9eb57275",
      "first_billing_date": "2020-12-12",
      "next_billing_date": "2021-01-12",
      "amount": 12,
      "description": "Monthly Plan",
      "finished_at": null,
      "active": true,
      "createdAt": "2020-12-25T03:00:00.000Z",
      "updatedAt": null
    }
  ]
}
```

This endpoint will get all subscriptions generated under a Network. In other words, all Subscriptions from Sellers that belongs to this specific Network will be shown here.

#### HTTP Request

**Sandbox**
`GET https://cashin.brydge.com.br/v1/network/:networkToken/payment/credit-card/subscriptions`

**Production**
`GET https://cashin.brydge.io/v1/network/:networkToken/payment/credit-card/subscriptions`

#### Query Parameters

None.