[//]: # (title: Technical implementation of the marketplace in the product)

## Support for the marketplace in the product

All the licensing-related communication with JetBrains licensing servers is done on the IntelliJ Platform side, not on the plugin side, so that you don't need to bundle our licensing checks code with your plugin or copy-paste licensing-specific functionality.

This approach lets us keep the licensing mechanism as a "black box," which ensures higher protection against piracy, as well as decreases the amount of work to be done on the plugin vendor side.

There are no private keys in the platform (otherwise, they can easily be extracted/leaked), so the IntelliJ Platform is getting a signed confirmation of the license from the server (online or on-premises) or the signed offline key. The plugin licensing verification code is using JetBrains' public certificate, which helps us verify that the key is a genuine one.

If the key couldn't be verified at the start of the IDE, the plugin will be disabled, and IDE will be re-started. The user won't be able to work with the plugin unless they provide a valid license key. 

Another thing which we have supported on the IntelliJ Platform side is a way to provide multiple license keys in a single instance of the IDE, as, otherwise, it would not be possible to support all the use cases, and now we can have a license key for a product, multiple plugins, and they even can be issued to multiple licensees.

![Multiple Licensing Dialog](multiple_licenses.png)

The whole product part is already available since the 2018.2 release of IntelliJ IDEA-based IDEs, but there have been significant additions, so the paid plugins part is fully operational since 2019.1 version of IntelliJ IDEA-based IDEs. [Database Tools and SQL plugin](https://plugins.jetbrains.com/plugin/10925-database-tools-and-sql) has been licensed via this mechanism since 2018.2.

## How is it different for Community Edition / Educational Edition / other IDEs built on top of IntelliJ Platform?

The support for Community Edition (and other free and open-source editions) of IntelliJ IDEA-based IDEs, as well as all IDEs built on top of open-source IntelliJ Platform, has been launched at the beginning of 2020. It might still take some time until the relevant changes arrive to third-party IDEs (depends on their release cycle), e.g., Android Studio will support paid Marketplace plugins after Android Studio 4.0 is released.

Licensing mechanism is delivered to the IDE as a special plugin, and your paid plugin should depend on this plugin to function in Community and other Community Edition-based IDEs.

## What should be supported on the plugin side?

First of all, a plugin has to identify itself as a paid marketplace plugin in the `plugin.xml` providing `productCode,` `release-date,` and `release-version` attributes (you can read more about them in [a dedicated article](prepare-a-plugin-to-be-sold-via-the-marketplace.md).)

As the next step, you need to add some calls from the plugin, and JetBrains is providing a standard licensing code to be added to the plugin distribution. All the licensing checks are done on the platform side, but the plugin has to verify that the platform checked and verified that a user has a license for this particular plugin (and specific plugin version), and shut down its operations if the license is not there. To do so, a plugin has to [include a standard code provided by JetBrains](add-marketplace-license-verification-calls-to-the-plugin-code.md) which would be checking that your plugin is licensed. 

## Obfuscation & Protection

We recommend you to obfuscate the paid plugin before uploading it to the plugins repository. Every application can be hacked, but proper obfuscation makes this job much harder.

At JetBrains, we had a lot of experience with [Zelix Klassmaster](https://www.zelix.com/klassmaster/index.html).

Read more about the obfuscation [in the dedicated article](obfuscate-the-plugin.md).
