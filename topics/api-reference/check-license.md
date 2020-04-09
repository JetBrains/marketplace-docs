[//]: # (title: Check License API)

If you paid plugin author you can check if the user with the specific email has valid license or not.

You should have a [**hubPermanentToken**](https://www.jetbrains.com/help/hub/Manage-Permanent-Tokens.html) at [JetBrains Hub](https://hub.jetbrains.com/users/me?tab=authentification) with Marketplace in Scope.

Curl command template:
```Shell
curl -H "Authorization: Bearer <hubPermanentToken>"  -X GET https://plugins.jetbrains.com//api/marketplace/plugin/{productCode}/license?email={email}"
```

where `productCode` is [Product Code](../paid-plugins-start/obtain-a-product-code-from-jetbrains.md) of your plugin and 
`email` is an email of the user you would like to check.