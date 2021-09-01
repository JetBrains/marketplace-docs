[//]: # (title: Preparing Your Plugin for Publication)


The process of plugin development can be challenging. For more detailed guidance about how to develop plugins successfully, feel free to check out our [IntelliJ Platform Plugin SDK](https://plugins.jetbrains.com/docs/intellij/welcome.html) documentation, which goes deeper into the plugin creation process and covers the basics of working with the IntelliJ Platform.

If your plugin is technically ready, you can begin working through the steps required to prepare it for publishing:

1. [Define the required parameters](add-required-parameters.md) in the plugin descriptor (plugin.xml).

2. Create an [Organization](organizations.md) and make sure the Organization ID is added to [the plugin descriptor (plugin.xml)](https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html).

3. Make sure the plugin meets [the approval criteria](https://plugins.jetbrains.com/legal/approval-guidelines).


<control>Optional steps:</control>

* [Obfuscate the plugin code](obfuscate-the-plugin.md)

* [Add marketplace license verification calls](add-marketplace-license-verification-calls-to-the-plugin-code.md)
