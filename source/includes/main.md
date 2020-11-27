# Introduction

Welcome to the Brydge API! You can use our API to access Brydge API endpoints, which can process payments, create digital banks and more easily.

We have language bindings only in Javascript (yet)! You can view code examples in the dark area to the right.

***We want to build bridges, not walls!***

# Authentication

> To authorize, you must to add the api_key on every request:

```javascript
const response = await axios({
   url: "https://api.brydge.com.br/v1/test",
   method: "get",
   headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> Make sure to replace `<API_KEY_FROM_YOUR_COMPANY>` with your API key.

Brydge uses API keys to allow access to the API. Please contact us to get your API Key.

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`api_key: <API_KEY_FROM_YOUR_COMPANY>`

<aside class=notice>
You must replace <code>API_KEY_FROM_YOUR_COMPANY</code> with your personal API key.
</aside>
