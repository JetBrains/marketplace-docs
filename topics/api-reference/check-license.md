[//]: # (title: Check license API)

If you are the author of a paid plugin, you can check whether the user with the specified email address has a license or not.

You should create a `permanentToken` in [My Tokens](https://plugins.jetbrains.com/author/me/tokens) tab within your JetBrains Marketplace profile dashboard.

CURL command template:
```Shell
curl -H "Authorization: Bearer <permanentToken>" -X GET https://plugins.jetbrains.com/api/marketplace/plugin/{productCode}/license?email={email}
```

where `productCode` is the [Product Code](https://plugins.jetbrains.com/docs/marketplace/obtain-a-product-code-from-jetbrains.html) of your plugin and 
`email` is an email of the user you would like to check.

The response has the following format:
```json
{
  "licenses": [
    {
      "type": "string",
      "trial": "boolean?",
      "period": "string?",
      "startFrom": "string($date)",
      "validTill": "string($date)?",
      "overuseTill": "string($date)?",
      "ownerCode": "integer",
      "ownerType": "string",
      "ownerEmail": "string"
    }
  ]
 }
```

The response example:
```json
{
  "licenses": [
    {
      "type": "PERSONAL",
      "trial": false,
      "period": "Annual",
      "startFrom": "[2019,6,26]",
      "validTill": "[2020,6,25]",
      "overuseTill": "[2020,7,2]",
      "ownerCode": 1234567,
      "ownerType": "Personal",
      "ownerEmail": "test.test@gmail.com"
    }
  ]
}
```
