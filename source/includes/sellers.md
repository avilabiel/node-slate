# Sellers

## Basic

To get a seller allowed to receive and make payments, we should:

1. Create the seller with Basic Information
2. Provide all necessary information like Phones, Addresses, Owners and Documents
3. Then, request the approval of KYC process

Only approved Sellers could receive and make payments on Brydge Ecosystem. Here, we are dealing with the step 1.

<aside class=warning>
This KYC process is very important to protect us against money laundry and some legal processes.
</aside>

### Create a Seller

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/seller`, {
  seller: {
		cnpj:"90787484000153",
		name:"Brydge IO LTDA",
	  email:"teste@brydge.io",
    password: "123mudar",
		business_name: "Brydge IO",
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
  "seller": {
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
    "updatedAt": "2020-11-23T21:38:59.709Z",
    "createdAt": "2020-11-23T21:38:59.709Z"
  }
}
```

This endpoint creates a new seller with the basic information. Right after, this you can access the Portal with Seller's credentials.

#### MCCs List

| ID  | Code | Category                   | Description                                                                          |
| --- | ---- | -------------------------- | ------------------------------------------------------------------------------------ |
| 1   | 5300 | Alimentação                | Atacado                                                                              |
| 2   | 5422 | Alimentação                | Casas de Carne / Peixaria                                                            |
| 3   | 5441 | Alimentação                | Docerias / Confeitarias / Rotisserie                                                 |
| 4   | 5499 | Alimentação                | Feira livre                                                                          |
| 5   | 5499 | Alimentação                | Hortifruit / Granjeiros                                                              |
| 6   | 5499 | Alimentação                | Lojas de Conveniência                                                                |
| 7   | 5499 | Alimentação                | Mercearia e Bebidas                                                                  |
| 8   | 5411 | Alimentação                | Alimentação em geral                                                                 |
| 9   | 5631 | Vestuário                  | Bijouterias                                                                          |
| 10  | 5948 | Vestuário                  | Calçados / Bolsas / Malas                                                            |
| 11  | 5977 | Vestuário                  | Cosméticos / Produtos de beleza                                                      |
| 12  | 7216 | Vestuário                  | Lavanderia / Tinturaria                                                              |
| 13  | 5192 | Vestuário                  | Magazines                                                                            |
| 14  | 5691 | Vestuário                  | Roupas masc., fem., inf., geral                                                      |
| 15  | 5137 | Vestuário                  | Uniformes                                                                            |
| 16  | 9999 |                            | Test Merchant Type                                                                   |
| 17  | 5039 | Moradia                    | Material de Construção                                                               |
| 18  | 5045 | Diversos                   | Computadores, Periféricos e Software                                                 |
| 19  | 5111 | Diversos                   | Papelaria, Material de Escritório                                                    |
| 20  | 5192 | Diversos                   | Banca de Jornal                                                                      |
| 21  | 5193 | Diversos                   | Floricultura                                                                         |
| 22  | 5411 | Alimentação                | Supermercado                                                                         |
| 23  | 5462 | Alimentação                | Padaria                                                                              |
| 24  | 5541 | Veículos                   | Posto de Combustível                                                                 |
| 25  | 5651 | Vestuário                  | Vestuário                                                                            |
| 26  | 5732 | Diversos                   | Eletrônicos                                                                          |
| 27  | 5812 | Alimentação                | Restaurante                                                                          |
| 28  | 5813 | Turismo & Entretenimento   | Bar e Casa Noturna                                                                   |
| 29  | 5814 | Alimentação                | Restaurante Fast Food                                                                |
| 30  | 5912 | Saúde                      | Farmácia, Drogaria                                                                   |
| 31  | 5942 | Educação                   | Livraria                                                                             |
| 32  | 5944 | Vestuário                  | Joalheria                                                                            |
| 33  | 5945 | Lazer                      | Loja de Brinquedos                                                                   |
| 34  | 8062 | Saúde                      | Hospital / Maternidade                                                               |
| 35  | 8011 | Saúde                      | Médico                                                                               |
| 36  | 8021 | Saúde                      | Dentista                                                                             |
| 37  | 8043 | Saúde                      | Óticas                                                                               |
| 38  | 742  | Saúde                      | Veterinário / Clínica veterinária                                                    |
| 39  | 8099 | Saúde                      | Saúde em geral                                                                       |
| 40  | 8249 | Veículos                   | Auto escola                                                                          |
| 41  | 5532 | Veículos                   | Borracharia                                                                          |
| 42  | 7523 | Veículos                   | Estacionamento                                                                       |
| 43  | 7542 | Veículos                   | Lava rápido                                                                          |
| 44  | 7512 | Veículos                   | Locadora de veículos                                                                 |
| 45  | 4784 | Veículos                   | Pedágio                                                                              |
| 46  | 4121 | Veículos                   | Táxi / Cia de táxi                                                                   |
| 47  | 5511 | Veículos                   | Veículos em geral                                                                    |
| 48  | 4789 | Turismo & Entretenimento   | Cia marítima                                                                         |
| 49  | 4722 | Turismo & Entretenimento   | Agências turismo                                                                     |
| 50  | 6211 | Turismo & Entretenimento   | Casa de câmbio                                                                       |
| 51  | 4011 | Turismo & Entretenimento   | Cia ferrovia                                                                         |
| 52  | 4214 | Turismo & Entretenimento   | Cia terrestre                                                                        |
| 53  | 7832 | Turismo & Entretenimento   | Cinema                                                                               |
| 54  | 7997 | Turismo & Entretenimento   | Clube                                                                                |
| 55  | 7011 | Turismo & Entretenimento   | Hotel / Pousada / Motel / Flat                                                       |
| 56  | 4722 | Turismo & Entretenimento   | Turismo em geral                                                                     |
| 57  | 7997 | Lazer                      | Academias em geral                                                                   |
| 58  | 7997 | Lazer                      | Aluguel de quadras                                                                   |
| 59  | 5971 | Lazer                      | Arte                                                                                 |
| 60  | 5735 | Lazer                      | Artigos música - Discos / CD / DVD                                                   |
| 61  | 5941 | Lazer                      | Artigos pesca / Caça / Camping                                                       |
| 62  | 7298 | Lazer                      | Personal Trainer                                                                     |
| 63  | 5937 | Lazer                      | Pintura / Desenho                                                                    |
| 64  | 5999 | Lazer                      | Produtos Eróticos (SEX SHOP)                                                         |
| 65  | 7230 | Lazer                      | Salão de Beleza                                                                      |
| 66  | 5993 | Lazer                      | Tabacaria                                                                            |
| 67  | 8111 | Diversos                   | Advogados / Escritório advocacia                                                     |
| 68  | 5970 | Diversos                   | Artesanato                                                                           |
| 69  | 8661 | Diversos                   | Associações religiosas                                                               |
| 70  | 8651 | Diversos                   | Associações políticas                                                                |
| 71  | 8999 | Diversos                   | Cartório                                                                             |
| 72  | 5499 | Diversos                   | Casa lotérica                                                                        |
| 73  | 6300 | Diversos                   | Cia seguro                                                                           |
| 74  | 4215 | Diversos                   | Despachante                                                                          |
| 75  | 8931 | Diversos                   | Escritório contabilidade                                                             |
| 76  | 7399 | Diversos                   | Feiras e eventos                                                                     |
| 77  | 5309 | Diversos                   | Produtos importados                                                                  |
| 78  | 4812 | Diversos                   | Provedor acesso internet                                                             |
| 79  | 4814 | Diversos                   | Recarga bilhete único / Celular                                                      |
| 80  | 9399 | Diversos                   | Serviços públicos                                                                    |
| 81  | 4899 | Diversos                   | TV por assinatura                                                                    |
| 82  | 5963 | Diversos                   | Venda em domicílio                                                                   |
| 83  | 2741 | Educação                   | Editora                                                                              |
| 84  | 8211 | Educação                   | Escola / Cursos em geral                                                             |
| 85  | 8220 | Educação                   | Escola / Faculdade                                                                   |
| 86  | 4789 | Educação                   | Transporte escolar                                                                   |
| 87  | 8299 | Educação                   | Educação em geral                                                                    |
| 88  | 8699 | Moradia                    | Adm. de condomínios                                                                  |
| 89  | 8911 | Moradia                    | Empreiteiros / Arquitetos / Engenheiros                                              |
| 90  | 1520 | Moradia                    | Imobiliárias / Construtoras / Incorporadoras                                         |
| 91  | 8062 | Saúde                      | Clínicas e Institutos especializados                                                 |
| 92  | 5995 | Saúde                      | Artigos para animais / Petshop                                                       |
| 93  | 8050 | Saúde                      | Casa de asilo                                                                        |
| 94  | 8099 | Saúde                      | Fono / Nutricionista / Físio / Psicólogo                                             |
| 95  | 7011 | Moradia                    | Cama / Mesa / Banho                                                                  |
| 96  | 5251 | Moradia                    | Chaveiros                                                                            |
| 97  | 4900 | Moradia                    | Concessionárias (Gás, Energia, Água)                                                 |
| 98  | 6513 | Moradia                    | Móveis em geral                                                                      |
| 99  | 5812 | Alimentação                | Pizzaria                                                                             |
| 100 | 5231 | Moradia                    | Tinta e Material de pintura                                                          |
| 101 | 5039 | Moradia                    | Moradia em geral                                                                     |
| 102 | 5039 | Moradia                    | Lojas de Departamento                                                                |
| 103 | 8099 | Diversos                   | Profissionais Liberais                                                               |
| 104 | 5965 | PSP / Serviços financeiros | Outras atividades auxiliares dos serviços financeiros não especificado anteriormente |

#### HTTP Request

**Sandbox**
`POST https://register.brydge.com.br/v1/network/:networkToken/seller`

**Production**
`POST https://register.brydge.io/v1/network/:networkToken/seller`

#### Query Parameters

None.

### Get a Seller by CNPJ

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const cnpj = "01394674000180";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/cnpj/${cnpj}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "seller": {
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
    "updatedAt": "2020-11-23T21:38:59.709Z",
    "createdAt": "2020-11-23T21:38:59.709Z"
  }
}
```

This endpoint takes information from a specific seller by CNPJ.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/cnpj/:cnpj`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/cnpj/:cnpj`

#### Query Parameters

None.

### Get a Seller by Token

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "seller": {
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
    "updatedAt": "2020-11-23T21:38:59.709Z",
    "createdAt": "2020-11-23T21:38:59.709Z"
  }
}
```

This endpoint takes information from a specific seller by Token.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken`

#### Query Parameters

None.

### Update a Seller

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}`, {
	seller: {
		cnpj:"90787484000153",
		name:"Brydge IO LTDA",
	  email:"teste@brydge.io",
		business_name: "Brydge IO",
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
  "msg": "Seller was updated"
}
```

This endpoint updates the information for a specific seller.

<aside class=notice>
You can pass any Seller's field here, it's not necessarly to send all its fields.
</aside>

#### HTTP Request

**Sandbox**
`PUT https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken`

**Production**
`PUT https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken`

#### Query Parameters

None.

## Phones

### Create a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/seller/${sellerToken}/phone`, {
	phone: {
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
  "phone": {
    "token": "d881ba21-92ad-4837-a672-4821ffc83b5c",
    "CompanyNetwork": {
      "token": "9460246d-3c0e-4318-8874-5f7acca63efc"
    },
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
`POST https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/phone`

**Production**
`POST https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/phone`

#### Query Parameters

None.

### Get a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const phoneToken = "d881ba21-92ad-4837-a672-4821ffc83b5c";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}/phone/${phoneToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "phone": {
    "token": "d881ba21-92ad-4837-a672-4821ffc83b5c",
    "CompanyNetwork": {
      "token": "9460246d-3c0e-4318-8874-5f7acca63efc"
    },
    "active": true,
    "area_code": 13,
    "country_code": 55,
    "number": "2583564",
    "updatedAt": "2020-11-27T19:11:44.091Z",
    "createdAt": "2020-11-27T19:11:44.091Z"
  }
}
```

This endpoint takes information from a specific seller.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/phone/:phoneToken`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/phone/:phoneToken`

#### Query Parameters

None.

### Update a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const phoneToken = "d881ba21-92ad-4837-a672-4821ffc83b5c";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}/phone/${phoneToken}`, {
	phone: {
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
  "msg": "Seller's phone was updated"
}
```

This endpoint updates information for a specific seller's phone.

<aside class=notice>
You can pass any Phone's field here, it's not necessarly to send all its fields.
</aside>

#### HTTP Request

**Sandbox**
`PUT https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/phone/:phoneToken`

**Production**
`PUT https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/phone/:phoneToken`

#### Query Parameters

None.

### Delete a Phone

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const phoneToken = "d881ba21-92ad-4837-a672-4821ffc83b5c";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.delete(`/v1/network/${networkToken}/seller/${sellerToken}/phone/${phoneToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "msg": "Seller's was phone deleted"
}
```

This endpoint delete a specific seller's phone.

<aside class=warning>
Only phones from not <strong>approved</strong> sellers can be deleted. If the seller is already approved, this endpoint will return this message:
<br ><br >
<i>
"This phone cannot be deleted because this seller is already approved. Try to update it"
</i>
</aside>

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/phone/:phoneToken`

**Production**
`GET https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/phone/:phoneToken`

#### Query Parameters

None.

## Addresses

### Create a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/seller/${sellerToken}/address`, {
	address:{
      line1:"Av Americas",
      line2:"500",
      line3:"Citta América", // optional
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
  "address": {
    "token": "d881ba21-92ad-4837-a672-4821ffc83b5c",
    "CompanyNetwork": {
      "token": "9460246d-3c0e-4318-8874-5f7acca63efc"
    },
    "street": "Av Americas",
    "number": "500",
    "neighborhood": "Barra da Tijuca",
    "complement": "Citta América",
    "city": "Rio de Janeiro",
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
`POST https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/address`

**Production**
`POST https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/address`

#### Query Parameters

None.

### Get a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const addressToken = "10ab9f3d-7523-48da-b580-4ca09ff92d53";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}/address/${addressToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "address": {
    "token": "d881ba21-92ad-4837-a672-4821ffc83b5c",
    "CompanyNetwork": {
      "token": "9460246d-3c0e-4318-8874-5f7acca63efc"
    },
    "street": "Av Americas",
    "number": "500",
    "neighborhood": "Barra da Tijuca",
    "complement": "Citta América",
    "city": "Rio de Janeiro",
    "state": "RJ",
    "zip_code": "22845046",
    "country_code": "BR",
    "updatedAt": "2020-11-27T19:10:37.198Z",
    "createdAt": "2020-11-27T19:10:37.198Z"
  }
}
```

This endpoint takes information from a specific seller's address.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/address/:addressToken`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/address/:addressToken`

#### Query Parameters

None.

### Update a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const addressToken = "10ab9f3d-7523-48da-b580-4ca09ff92d53";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}/address/${addressToken}`, {
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
  "msg": "Seller's address was updated"
}
```

This endpoint updates information for a specific seller's address.

<aside class=notice>
You can pass any Address' field here, it's not necessarly to send all its fields.
</aside>

#### HTTP Request

**Sandbox**
`PUT https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/address/:addressToken`

**Production**
`PUT https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/address/:addressToken`

#### Query Parameters

None.

### Delete a Address

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const addressToken = "10ab9f3d-7523-48da-b580-4ca09ff92d53";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.delete(`/v1/network/${networkToken}/seller/${sellerToken}/address/${addressToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "msg": "Seller's address was deleted"
}
```

This endpoint deletes a specific seller's address.

<aside class=warning>
Only addresses from not <strong>approved</strong> sellers can be deleted. If the seller is already approved, this endpoint will return this message:
<br ><br >
<i>
"This address cannot be deleted because this seller is already approved. Try to update it"
</i>
</aside>

#### HTTP Request

**Sandbox**
`DELETE https://register.brydge.com.br/v1//network/:networkToken/seller/:sellerToken/address/:addressToken`

**Production**
`DELETE https://register.brydge.io/v1//network/:networkToken/seller/:sellerToken/address/:addressToken`

#### Query Parameters

None.

## Owner

The Seller's owner.

### Create a Owner

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
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
  "owner": {
    "token": "10ab9f3d-7523-48da-b580-4ca09ff92d53",
    "CompanyNetwork": {
      "token": "9460246d-3c0e-4318-8874-5f7acca63efc"
    },
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
`POST https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/owner`

**Production**
`POST https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/owner`

#### Query Parameters

None.

### Get a Owner

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const ownerToken = "10ab9f3d-7523-48da-b580-4ca09ff92d53";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}/owner/${ownerToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "owner": {
    "token": "10ab9f3d-7523-48da-b580-4ca09ff92d53",
    "CompanyNetwork": {
      "token": "9460246d-3c0e-4318-8874-5f7acca63efc"
    },
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

This endpoint takes information from a specific seller's owner.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/owner/:ownerToken`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/owner/:ownerToken`

#### Query Parameters

None.

### Update a Owner

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const ownerToken = "10ab9f3d-7523-48da-b580-4ca09ff92d53";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.update(`/v1/network/${networkToken}/seller/${sellerToken}/owner/${ownerToken}`, {
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
  "msg": "Seller's owner was updated"
}
```

This endpoint updates information for a specific seller's owner.

<aside class=notice>
You can pass any Owner's field here, it's not necessarly to send all its fields.
</aside>

#### HTTP Request

**Sandbox**
`PUT https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/owner/:ownerToken`

**Production**
`PUT https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/owner/:ownerToken`

#### Query Parameters

None.

## Documents

### Upload a Document

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "382184a-382d-hsa3-4882-849c932jduw";
const documentType = "cnpj";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(
  `/v1/network/${networkToken}/seller/${sellerToken}/document/${documentType}`,
  {
	  file: <UPLOADED_FILE>
  }, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
    }
  }
);
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "msg": "Upload has been made",
  "url": "https://brydge-register-upload.s3.amazonaws.com/seller/83281jnds8231nb.png"
}
```

This endpoints uploads a document to a Seller. This process is important for KYC. Only approved Sellers can receive and make payments.

<aside class=notice>
Use enctype="multipart/form-data"
</aside>

<aside class=warning>
It's possible to send more than one document for each Document Type
</aside>

#### Document Types

| Type          | Description                                                                                   |
| ------------- | --------------------------------------------------------------------------------------------- |
| identificacao | Document with a picture from the Seller's Owner (RG, CPF or CNH)                              |
| atividade     | License (alvará), product purchase invoice (nota fiscal) or business card (cartão de visitas) |
| residencia    | Electricity, telephone or gas bill in the name of the Seller's Owner or family                |
| cnpj          | CNPJ Card                                                                                     |

#### HTTP Request

**Sandbox**
`POST https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/document/:documentType`

**Production**
`POST https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/document/:documentType`

#### Query Parameters

None.

## Approval

### Create an Approval Request

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
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
  "message": "Seller has been approved",
  "approval": {
    "status": "pending",
    "created_at": "2020-11-27T19:12:04+00:00",
    "updated_at": "2020-11-27T19:12:04+00:00"
  }
}
```

Only approved sellers can receive and make payments on Brydge API. For a seller to be approved, the following information must be sent:

1. Seller's Data
2. Seller's Phone
3. Seller's Address
4. Seller's Owner
5. Seller's Documents
6. Seller's Owner Documents

Only with this information is it possible for a seller to be approved.

This endpoint requests the approval from KYC process for a new seller.

<aside class=notice>
This KYC process is very important to protect us against money laundry and some legal processes.
</aside>

<aside class=warning>
This process is <strong>asynchronous</strong> and it could take until <strong>3 business days to be approved or rejected</strong>.
</aside>

#### HTTP Request

**Sandbox**
`POST https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/approval`

**Production**
`POST https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/approval`

#### Query Parameters

None.

### Check Approval Status

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(`/v1/network/${networkToken}/seller/${sellerToken}/approval`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "approval": {
    "status": "approved",
    "created_at": "2020-11-27T19:12:04+00:00",
    "updated_at": "2020-11-27T19:12:04+00:00"
  }
}
```

Checks the Approval Status from an Approval Request to a specific Seller.

<aside class=notice>
This KYC process is very important to protect us against money laundry and some legal processes.
</aside>

<aside class=warning>
This process is <strong>asynchronous</strong> and it could take until <strong>3 business days to be approved or rejected</strong>.
</aside>

#### Statuses List

| Status        | Description                                 |
| ------------- | ------------------------------------------- |
| approved      | Approval request was approved               |
| pending       | KYC Team is still analyzing the request     |
| rejected      | Approval request was rejected               |
| not requested | Approval request has been not requested yet |

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/approval`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/approval`

#### Query Parameters

None.

## Bank Accounts

Sellers can withdrawal money since they receive payments. For that, they need to create bank accounts.

### Create a Bank Account

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.post(`/v1/network/${networkToken}/seller/${sellerToken}/bank-account`, {
	bank_account: {
    token: "e84ad069-ff20-4952-bf8d-40e9da9e1d59",
    id_bank: 1,
    agency_number: "1234",
    account_number: "254421-2",
    type: "checking",
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
  "bank_account": {
    "token": "cf157c3d-5295-4251-ba9d-04ffceeba971",
    "id_bank": 1,
    "agency_number": "1234",
    "account_number": "254421-2",
    "type": "checking",
    "active": true,
    "createdAt": "2020-01-30T13:28:47.000Z",
    "updatedAt": "2020-01-30T13:28:47.000Z"
  }
}
```

This endpoint creates a new Seller's bank account.

<aside class=warning>
The Seller must be approved to use this endpoint.
</aside>

#### HTTP Request

**Sandbox**
`POST https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/bank-account`

**Production**
`POST https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/bank-account`

#### Query Parameters

None.

### Get all Bank Accounts

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const bankAccountToken = "cf157c3d-5295-4251-ba9d-04ffceeba971";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(
  `/v1/network/${networkToken}/seller/${sellerToken}/bank-accounts`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "bank_accounts": [
    {
      "token": "cf157c3d-5295-4251-ba9d-04ffceeba971",
      "id_bank": 1,
      "agency_number": "1234",
      "account_number": "254421-2",
      "type": "checking",
      "active": true,
      "createdAt": "2020-01-30T13:28:47.000Z",
      "updatedAt": "2020-01-30T13:28:47.000Z"
    },
    ...
  ]
}
```

This endpoint takes information from all Seller's bank accounts.

<aside class=warning>
The Seller must be approved to use this endpoint.
</aside>

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/bank-accounts`

**Production**
`GET https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/bank-accounts`

### Delete Bank Account

```javascript
const networkToken = "9460246d-3c0e-4318-8874-5f7acca63efc";
const sellerToken = "7fc5e37f-5760-4848-bb9f-6a3e40977903";
const bankAccountToken = "cf157c3d-5295-4251-ba9d-04ffceeba971";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(
  `/v1/network/${networkToken}/seller/${sellerToken}/bank-account/${bankAccountToken}`, {
    headers: {
      api_key: <API_KEY_FROM_YOUR_COMPANY>
   }
});
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "msg": "Seller's bank account was deleted"
}
```

This endpoint deletes a Seller's bank account.

<aside class=warning>
The Seller must be approved to use this endpoint.
</aside>

#### HTTP Request

**Sandbox**<br />
`DELETE https://register.brydge.com.br/v1/network/:networkToken/seller/:sellerToken/bank-account/:bankAccountToken`

**Production**<br />
`DELETE https://register.brydge.io/v1/network/:networkToken/seller/:sellerToken/bank-account/:bankAccountToken`

## Authentication

It's possible to authenticate your sellers.

### Authenticate User

```javascript
const username = "test@brydge.com.br";
const password = "123default";
const brydgeSandboxURL = "https://register.brydge.com.br";
const api = axios. axios.create({
    baseURL: brydgeSandboxURL,
});

const response = await axios.get(
  `/v1/user/authenticate`, {
	    username,
	    password
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
  "user": {
    "name": "Brasil Park",
    "email": "test@brydge.com.br",
    "type": "seller",
    "token": "af8c6f4b-3452-4301-9668-5c44166123f4",
    "companyNetworkToken": "9460246d-3c0e-4318-8874-5f7acca63efb"
  }
}
```

If the username and password matches, it returns the current user, user type, its token and its company network token.

When the user is not found, the response will be:

```json
{
  "success": false,
  "message": "User not found"
}
```

#### Query Parameters

None.

#### HTTP Request

**Sandbox**
`GET https://register.brydge.com.br/v1/user/authenticate`

**Production**
`GET https://register.brydge.io/v1/user/authenticate`
