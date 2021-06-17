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

<aside class=warning>
You must replace <code>API_KEY_FROM_YOUR_COMPANY</code> with your personal API key. 
</aside>

<aside class=notice>
If you don't have an API Key, please request it to Brydge Support.
</aside>
