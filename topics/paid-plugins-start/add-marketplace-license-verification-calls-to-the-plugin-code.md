[//]: # (title: Add Marketplace license verification calls to the plugin code)

Plugin creators need to [define the attributes](add-required-parameters.md) of their paid plugins in the plugin descriptor (`plugin.xml`) to start selling process. Then, all the licensing-related communication, including plugin license checks, is done on the IntelliJ Platform side. Licenses will first be checked by the IDE on startup. After that, there will be additional checks at least once a day.

However, you should verify on your own that a user has a license for the plugin by adding license verification calls to the plugin code. We recommend implementing this for the following reasons: 

* Even though the IDE checks the plugin license at least once a day, it’s never wrong to increase the security layer against piracy by adding this functionality to your plugin.

<note>
<p>Having the plugin perform license checks too often may lead to high CPU usage. That is why we recommend sticking to a few checks per day.</p>
</note>

* These verification calls could also be useful for your plugin scheme, for example if you’re developing a [free plugin with paid functionality](freemium.md). You can implement logic to notify users who aren't licensed that there is a paid functionality in your plugin, and have this notification appear during the license check.


To implement license verification on the plugin side, a plugin has to include a standard code provided by JetBrains, which checks that your plugin is licensed.

Here you will find an example [plugin](https://github.com/JetBrains/marketplace-makemecoffee-plugin) with product parameter declarations, as well as a license check:

* [CheckLicense](https://github.com/JetBrains/marketplace-makemecoffee-plugin/blob/master/src/main/java/com/company/license/CheckLicense.java)
* [Action](https://github.com/JetBrains/marketplace-makemecoffee-plugin/blob/master/src/main/java/actions/MakeCoffeeAction.java)



You can find the `CheckLicense` class in `license/CheckLicense.java`, which is then used in `actions/DemoAction.java` to check whether the plugin is licensed.

<tip>
  <p><code>LicensingFacade.getInstance() == null</code> means the LicensingFacade object is not initialized yet. So you cannot say for sure whether a plugin is licensed or not.</p>
  <p>As soon as <code>LicensingFacade.getInstance() != null</code>, all initialization procedures are now completed and the plugin can examine the state of the LicensingFacade object. Now the lack of a licensing stamp will definitely mean that the license is missing.</p>
</tip>

There are no private keys in the platform (otherwise, they could easily be extracted/leaked), so the IntelliJ Platform gets a signed confirmation of the license from the server (online or on-premises) or the signed offline key. The plugin licensing verification code uses the JetBrains public certificate, which helps us verify that the key is genuine.