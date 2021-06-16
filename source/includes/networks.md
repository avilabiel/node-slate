# Networks

Networks have sellers and customers inside of them. They are like the parent that have children. Also, Networks have the possibility to configure some properties, fees, and more.

## Sell Plans

Sell Plans are the plans that Brydge has to your company process credit cards: D+1, D+10, D+30. Each Sell Plan has your own fees.

### Get Sell Plan Fees

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellPlan = "D+1";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(
  `/v1/network/${networkToken}/sell-plan/fees?sellPlan=${sellPlan}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
  });
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "fees": [
    {
      "type": "credit",
      "installment": 1,
      "CardBrand": {
        "name": "Mastercard"
      },
      "percentage_fee": 1.75,
      "fixed_fee": 0
    },
    {
      "type": "credit",
      "installment": 2,
      "CardBrand": {
        "name": "Mastercard"
      },
      "percentage_fee": 2.69,
      "fixed_fee": 0
    },
    {
      "type": "credit",
      "installment": 3,
      "CardBrand": {
        "name": "Mastercard"
      },
      "percentage_fee": 3.36,
      "fixed_fee": 0
    }
    // ...
  ]
}
```

Returns the sell plan and its fees for each card brand available.

#### Query Parameters

| Parameter | Default | Description                         |
| --------- | ------- | ----------------------------------- |
| sellPlan  | none    | The sell plan that will be returned |

#### HTTP Request

**Sandbox**
`PUT https://register.brydge.com.br/v1/network/:networkToken/sell-plan/fees`

**Production**
`PUT https://register.brydge.io/v1/network/:networkToken/sell-plan/fees`

### Get Sell Plan History

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellPlan = "D+1";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(
  `/v1/network/${networkToken}/sell-plan/history`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
  });
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "history": [
    {
      "old_sell_plan": "D+1",
      "new_sell_plan": "D+30",
      "created_at": "2021-03-16T15:30:03.000Z"
    },
    {
      "old_sell_plan": "D+30",
      "new_sell_plan": "D+1",
      "created_at": "2021-03-16T15:27:47.000Z"
    },
    {
      "old_sell_plan": "D+1",
      "new_sell_plan": "D+30",
      "created_at": "2021-03-16T15:27:35.000Z"
    }
    // ...
  ]
}
```

Returns the current sell plan and the history of changes. The current sell plan is the `new_sell_plan` of the first item from the returned list (history[0].new_sell_plan).

#### Query Parameters

None.

#### HTTP Request

**Sandbox**
`PUT https://register.brydge.com.br/v1/network/:networkToken/sell-plan/history`

**Production**
`PUT https://register.brydge.io/v1/network/:networkToken/sell-plan/history`

### Update Sell Plan

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const newCreditCardSellPlan = "D+1";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.put(
  `/v1/network/${networkToken}/sell-plan`, {
    sell_plan: newCreditCardSellPlan
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
  "message": "Sells Plan updated from the Network and all its approved Sellers"
}
```

This endpoint changes the current sell plan for a specific Network and its approved Sellers.

<aside class=warning>
This change could take one whole day (24hs) to be applied.
</aside>

<aside class=warning>
Only the approved companies will get this change.
</aside>

#### Sell Plans List

| Type | Description                                                                  | Default |
| ---- | ---------------------------------------------------------------------------- | ------- |
| D+1  | All credit card payments will be available on your balance on D+1 (in 1 day) | Yes     |

#### HTTP Request

**Sandbox**
`PUT https://register.brydge.com.br/v1/network/:networkToken/sell-plan`

**Production**
`PUT https://register.brydge.io/v1/network/:networkToken/sell-plan`
