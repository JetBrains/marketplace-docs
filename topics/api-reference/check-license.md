[//]: # (title: Check License API)

If you are the author of a paid plugin, you can check whether the user with the specified email address has a valid license or not.

You should have a [**hubPermanentToken**](https://www.jetbrains.com/help/hub/Manage-Permanent-Tokens.html) at [JetBrains Hub](https://hub.jetbrains.com/users/me?tab=authentification) with Marketplace in Scope.

Curl command template:
```Shell
curl -H "Authorization: Bearer <hubPermanentToken>" -X GET https://plugins.jetbrains.com/api/marketplace/plugin/{productCode}/license?email={email}
```

where `productCode` is the [Product Code](../paid-plugins-start/obtain-a-product-code-from-jetbrains.md) of your plugin and 
`email` is an email of the user you would like to check.

The response has the following format:
```json
{
  "licenses": [
    {
      "type": "string",
      "trial": "boolean",
      "period": "string",
      "startFrom": "string($date)",
      "validTill": "string($date)",
      "overuseTill": "string($date)"
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
      "startFrom": "26/06/2019",
      "validTill": "25/06/2020",
      "overuseTill": "02/07/2020"
    }
  ]
}
```