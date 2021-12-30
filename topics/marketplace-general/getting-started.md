[//]: # (title: Getting started)

# Introduction

If you are new to plugins, please start here.

Plugins extend the core functionality of [IntelliJ Platform](https://plugins.jetbrains.com/docs/intellij/intellij-platform.html) IDEs. 


By installing plugins, you can get the following features, among others:
* Integration with version control systems, Docker, Kubernetes, and other technologies
* Coding assistance support for various languages and frameworks
* Shortcut hints, live previews, and File Watchers
* Edu courses, including coding exercises that can help you to learn a new programming language
* Themes, color schemes, backgrounds, progress bars, and other visual customizations


You can browse the plugins in the [JetBrains Marketplace](https://plugins.jetbrains.com/). 

![Marketplace Main page](marketplace-main-page.png)

If you want to install a plugin, you can click the Get button. If you have the IDE running at the moment, the button will change to **'Install to IDE'** and the plugin will be installed directly in your IDE.
![Install to IDE](install-to-ide.gif)

You can then [manage the installed plugins](https://www.jetbrains.com/help/idea/managing-plugins.html) in your IDE.

When an update is available, you will get a notification in your IDE to install the updates and (sometimes) restart the IDE.
![Updates Available](update-available.png)

# Plugin development

Technology evolves quickly, and authors upload dozens of new plugins (and updates to existing ones) every day. If you cannot find the plugin you need, you can ask the community to create one for you, or you can even create it yourself.

## If you want someone to create a plugin for you
* Check if there is already such a request on the [Plugin Ideas](https://plugins.jetbrains.com/plugin-ideas) list and vote for it or submit your idea.
* Join the [JetBrains Platform Slack](https://plugins.jetbrains.com/slack) or the [Plugin Development forums](https://intellij-support.jetbrains.com/hc/en-us/community/topics/200366979-IntelliJ-IDEA-Open-API-and-Plugin-Development) and discuss the idea with the community.

![Plugin Ideas](plugin-ideas.png)

## If you want to develop a plugin
* Consider checking the [Plugin Ideas](https://plugins.jetbrains.com/plugin-ideas) list and bringing the requested features to life.
* Check the [IntelliJ Platform SDK docs](https://plugins.jetbrains.com/docs/intellij/welcome.html).
* Join the [JetBrains Platform Slack](https://plugins.jetbrains.com/slack) or the [Plugin Development forums](https://intellij-support.jetbrains.com/hc/en-us/community/topics/200366979-IntelliJ-IDEA-Open-API-and-Plugin-Development) to discuss any questions related to plugin development with the community.
* Check the [IntelliJ Platform UI Guidelines](https://jetbrains.design/intellij/) to create consistent and usable user interfaces.
* [Browse the source files](https://plugins.jetbrains.com/intellij-platform-explorer) of open-source IntelliJ Platform plugins hosted on GitHub to find inspiration when implementing your ideas for IntelliJ-based IDE extensions.

![IntelliJ Platform Explorer](intellij-platform-explorer.png)

# Publish plugin

## Submitting a plugin

Before you submit your plugin, please check the [Quality Guidelines](https://plugins.jetbrains.com/docs/marketplace/plugin-overview-page.html) to improve the overall quality of your plugin and start preparing your plugin's page.

To publish a plugin on the JetBrains Marketplace
1. Click the **'Upload plugin'** button.
2. Read and accept the [JetBrains Plugin Marketplace Developer Agreement](https://plugins.jetbrains.com/legal/developer-agreement).
3. Select the proper license.
4. Select the most suitable tag.
5. Select a [release channel](https://plugins.jetbrains.com/docs/marketplace/custom-release-channels.html).

![Upload New Plugin](upload-new-plugin.gif)

## Plugin approval

Once a plugin has been submitted, the Marketplace Team checks it according to the [Approval Guidelines](https://plugins.jetbrains.com/legal/approval-guidelines). Please expect approval or a reply within two business days and note that the answer will be sent to the email address associated with your Marketplace account.
![Email Address](email.png)

## Plugin page overview

While you are waiting for approval, you can familiarize yourself with your plugin's page.
![Plugin Page](plugin-ui.png)
On the **Overview** tab you can check the plugin's [download statistics](https://plugins.jetbrains.com/docs/marketplace/download-statistics.html).

In the **Media** section, you can upload screenshots and add a video. 

![General Information](general-information.png)
In the **General Information** and **Vendor Information** sections, you can add/remove tags, change the license, add/remove authors, add copyrights, and add source code link.

![Description](description-usage.png)
In the next two sections, you can check the **Description** extracted from the [configuration file — plugin.xml](https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html), and add **Getting Started** instructions.

![Embeddables](embeddables.png)
In the **Embeddables** section, you can copy the code for [embeddable](https://plugins.jetbrains.com/docs/marketplace/embeddable-content.html) Plugin Card and the **'Install to IDE'** button.

![Contacts & Resources](contacts-resources.png)
In the next section, you can add links to your plugin’s issue tracker, documentation, forum, and add custom contacts. If your plugin adds [Features](https://plugins.jetbrains.com/docs/intellij/about.html#part-v-features), you can also check them in the **Technical Information** section.

![Update Page](update-page.png)
On the **Versions** tab, you can check the individual updates for your plugin. The most interesting parts here are the **Compatibility Range**, where you can manually set the compatible versions of the update, number of downloads for this update, and **Compatibility Verification**, where you can check the results of the verification performed by the [IntelliJ Plugin Verifier](https://github.com/JetBrains/intellij-plugin-verifier).
![Update Page 2](update-page2.png)

![Reviews](reviews.png)
On the **Reviews** tab, you can check the [rating](https://plugins.jetbrains.com/docs/marketplace/plugins-rating.html) and reviews for your plugin. You can also reply to the reviews.

On the **Custom Pages** tab, you can add a [Custom Page](https://plugins.jetbrains.com/docs/marketplace/custom-pages.html) to provide your users with additional information such as documentation, marketing landing pages, etc.

On the **Analytics** tab, you can see a dashboard with interactive charts, including download stats, sales graphs (for paid plugins), and some web analytics. More information can be found in [this article](https://plugins.jetbrains.com/docs/marketplace/analytics-tab.html).

Next to the tabs, there are several buttons.

![Notification settings](notifications.png)
If you click on the Bell button, you can manage your notification settings.

The 'Preview' button allows you to check how the plugin's page will look publicly.

![Upload New Update](new-update.png)
The **'Upload Update'** button is for uploading a new update for your plugin. You can select a different release channel for each update (useful for EAP/Beta/Nightly/Stable approach).

![removal](removal.png)
To remove the plugin, click the button with three dots next to the 'Upload Update' button.

# What's next

You can start generating income from your plugin by selling it on JetBrains Marketplace. Check out [this page](https://plugins.jetbrains.com/docs/marketplace/paid-plugins-marketplace.html) for an overview and general information.

To try selling your plugin on Marketplace, please follow [this step-by-step guide](https://plugins.jetbrains.com/docs/marketplace/step-by-step-guide-to-putting-plugin-up-for-sale.html).
