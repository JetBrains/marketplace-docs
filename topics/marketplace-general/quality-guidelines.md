[//]: # (title: Quality Guidelines)

## Plugin Quality

JetBrains Marketplace users expect high-quality plugins. The long-term success of your plugin directly depends on the plugin's quality. The higher it is, the more installs, positive reviews, community involvement you get.

If you only plan to develop your plugin, please review these quality criteria before publishing. If you have plugins already published on the Marketplace, you may still consider reviewing the following criteria to further improve the plugin's quality.

Please note that these criteria extend the [Plugin Approval Criteria](https://plugins.jetbrains.com/legal/approval-guidelines) but aren't obligatory. However, you may still be asked to improve some aspects of your plugin according to these criteria when you upload a new plugin to the Marketplace.

## User Experience

Here you can find a few general advice regarding the overall expected user experience with the plugin.

* Please follow the [IntelliJ Platform UI Guidelines](https://jetbrains.design/intellij/);
* If the plugin adds menu items, toolbars, or other UI elements with text, please make sure that it is written in English;
* Keyboard shortcuts can enhance the experience by helping users to stay more productive. If you decided to add a shortcut, please ensure that there are no conflicts with the default shortcuts of the target IDEs (see [Action System](https://plugins.jetbrains.com/docs/intellij/basic-action-system.html) to find instructions on how to add shortcuts, menu items, and other UI elements);
* None of the notifications shown by plugin should contain advertising or content unrelated to the plugin functionality unless the user has explicitly opted in (for more information see [Notifications](https://plugins.jetbrains.com/docs/intellij/notifications.html?from=jetbrains.org));
* Graphics, icons, images, or other UI elements displayed by plugin should not be distorted (see [Working with Icons and Images](https://plugins.jetbrains.com/docs/intellij/work-with-icons-and-images.html));
* Make sure that none of the UI elements with text have cut-off letters or words;
* The plugin should not redefine any normal functions of the IDE misleadingly or confusingly.

## Plugin Publishing

![Upload New Plugin](upload-new-plugin.png)

When you upload a new plugin, please make sure to choose the correct **Category**. Categories are actively used by users to find new plugins. Therefore, misplacing a plugin may lead to a small number of plugin users.

If you want your plugin not to be generally available (e.g., it is an alpha/beta/EAP version), please add a [Custom Release Channel](https://plugins.jetbrains.com/docs/marketplace/custom-release-channels.html).

## Marketplace Plugin Page

The plugin page is the main page of your plugin on the JetBrains Marketplace. A page of high quality is key to a more significant number of downloads. 
Some of the elements on the plugin page are extracted from the [Plugin Configuration File — plugin.xml](https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html) and cannot be changed without uploading a new plugin version:
* Plugin URL (`<idea-plugin url="">`);
* Name (`<name>`);
* Description (`<description>`);
* Change notes of the latest version (`<change-notes>`);
* Vendor links (`<vendor>`).
The description and change notes can contain most HTML tags.

### Plugin Name
* The name shouldn't start with the letter "A" or the dot sign if it is not needed (e.g., "Code Enhancer" instead of "A Code Enhancer");
* The name should be written in the Latin symbols. It may as well contain numbers and some general, special symbols if needed (e.g., dot, a hyphen, parentheses);
* A short, memorable name is better than a long generic one;
* Don't overuse meaningless words (e.g., "Plain Text Support" is better than "Free Plain Text Support Plus Platinum Maximum Edition").

### Plugin Logo
You can find the instruction on how to change the plugin logo [here](https://plugins.jetbrains.com/docs/intellij/plugin-icon-file.html).
* The logo should be different from the [default logo](https://github.com/JetBrains/intellij-platform-plugin-template/blob/main/src/main/resources/META-INF/pluginIcon.svg) of the IntelliJ Platform Plugin Template;
* The logo should not resemble any of the JetBrains products' logos.
* If the logo contains text it should be readable;
* A simple, recognizable image is better than an overcomplicated one.

### Plugin Screenshots
* The screenshots should be of a high-quality;
* They shouldn't contain device images (e.g., a photo of your screen) or small text that will be illegible;
* They should help to understand the functionality of your plugin;
* None of the plugin screenshots should contain advertising or content unrelated to the plugin functionality;
* The screenshots shouldn't misleadingly represent your plugin;
* Please consider uploading the screenshots to the Marketplace instead of adding links to external resources to the plugin description;
* Color scheme and Theme plugins should have screenshots to represent the visual style they provide.

### Plugin Description
* The description should be detailed but not over-detailed. A couple of paragraphs to explain the basic functionality of the plugin and simple usage instructions (e.g., "Press `Escape` to focus the editor" or "Go to `File -> Settings -> Tools` to configure the plugin") should be enough;
* The very first line of the plugin description should contain a short plugin summary in English. It is needed for the Plugin Card, shown on the Marketplace or [embedded](https://plugins.jetbrains.com/docs/marketplace/embeddable-content.html) in your website;
* It might be a good idea to put some inline links to useful resources (e.g., issue tracker, [custom pages](https://plugins.jetbrains.com/docs/marketplace/custom-pages.html), forum, etc.) to the description;
* If your plugin requires additional configuration, please add a short instruction to the description. If the instruction is long, please add a link to it instead.

### Plugin links
* Please make sure that all of the external links on your plugin page are reachable from the Internet;
* If you add a source code repository link, please make sure that it is publicly available.

### Vendor Naming
If you plan to use your name as a vendor name, we recommend writing it in a standard way, "FirstName LastName" to enhance visual clarity.

### General Usage Instructions
* The **General Usage Instructions** should contain installation and configuration instructions. Additional instructions can be added to the **Documentation URL** or to the **Custom Pages**.
* Users cannot see the General Usage Instructions from within the IDE, so any necessary instructions should be added to the description.

### Change Notes
Please make sure to put a short summary of changes to the **Change Notes** of each plugin version. It helps to track the plugin progress, introduce new features, announce upcoming changes, and recap the bugfixes.
* To ease and speed up the understanding of change notes, please consider putting the new notes higher than the older one;
* If there are too many change notes, please consider adding them as a **Custom Page** or an external link instead with just a link in the `<change-notes>`.

### Custom Pages
To make the plugin description less bulky and not overcomplicated, add additional content (e.g., promo materials, documentation, description in a variety of languages) you can use **Custom Pages**. More information about them can be found [here](https://plugins.jetbrains.com/docs/marketplace/custom-pages.html).
