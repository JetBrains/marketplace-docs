[//]: # (title: How to anonymously and uniquely identify a user of a paid plugin?)

As a plugin developer, you may want to collect some usage statistics. You may also want to uniquely and anonymously identify users in order to make said statistics more precise and insightful.

First of all, you must explicitly get user's consent for doing this. After that, you can add this code to your plugin:

```java
final LicensingFacade instance = LicensingFacade.getInstance();
return instance == null ? null : instance.getLicensedToMessage();
```

This code will return the `LicensedTo` value which is unique for a given user. It will be kept during the plugin's reinstallation and is also derived from the JetBrains Account.
To make it anonymous you can hash the `LicensedTo` value and send only the hash.
