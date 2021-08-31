[//]: # (title: Add marketplace license verification calls to the plugin code)

Plugin creators need to [define the attributes](add-required-parameters.md) of their paid plugins in the plugin descriptor (`plugin.xml`) to start selling process. Then, all the licensing-related communication, including plugin license checks, is done on the IntelliJ Platform side. Licenses will first be checked by the IDE on startup. After that, there will be additional checks at least once a day, so you don't need to bundle it with your plugin or copy-paste licensing-specific functionality.

This approach lets us keep the licensing mechanism as a "black box", which ensures higher protection against piracy and also decreases the amount of work to be done on the plugin vendor side.

In the meantime, you could add an additional feature to your plugin that would allow it to verify on its own that a user has a license for this particular plugin (and specific plugin version). We’d like to emphasize that this is an <control>optional step</control>, but it’s one we recommend implementing for the following reasons:

* Even though the IDE checks the plugin license at least once a day, it’s never wrong to increase the security layer against piracy by adding this functionality to your plugin.

<note>
<p>Having the plugin perform license checks too often may lead to high CPU usage. That is why we recommend sticking to a few checks per day.</p>
</note>

* These verification calls could also be useful for your plugin scheme, for example if you’re developing a [free plugin with paid functionality](free-functionality.md). You can implement logic to notify users who aren't licensed that there is a paid functionality in your plugin, and have this notification appear during the license check.


To implement license verification on the plugin side, a plugin has to include a standard code provided by JetBrains, which checks that your plugin is licensed.

Here you will find an example [plugin](https://github.com/JetBrains/marketplace-makemecoffee-plugin) with product parameter declarations, as well as a license check:

* [CheckLicense](https://github.com/JetBrains/marketplace-makemecoffee-plugin/blob/master/src/main/java/com/company/license/CheckLicense.java)
* [Action](https://github.com/JetBrains/marketplace-makemecoffee-plugin/blob/master/src/main/java/actions/MakeCoffeeAction.java)



You can find the `CheckLicense` class in `license/CheckLicense.java`, which is then used in `actions/DemoAction.java` to check whether the plugin is licensed (in an actual use case, your plugin should not work if the plugin is not licensed.)



There are no private keys in the platform (otherwise, they could easily be extracted/leaked), so the IntelliJ Platform gets a signed confirmation of the license from the server (online or on-premises) or the signed offline key. The plugin licensing verification code uses the JetBrains public certificate, which helps us verify that the key is genuine.