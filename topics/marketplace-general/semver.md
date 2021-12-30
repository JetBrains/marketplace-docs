[//]: # (title: Semantic Versioning)

**SemVer** (Semantic Versioning) is a scheme that defines the rules to name the subsequent versions of libraries, projects, products, etc.

The most straightforward usage case is the following version format:
```
MAJOR.MINOR.PATCH
```

There are also more rules and possibilities to distinguish some builds, like:
```
1.8.2-beta.1.10+somebuild 
```

All the available rules that SemVer standard defines can be found in the official documentation at [https://semver.org](https://semver.org).

To check if the given version number matches SemVer rules, you can use:

* [Regex101 sandboxes](https://semver.org/#is-there-a-suggested-regular-expression-regex-to-check-a-semver-string)
* An online checker, [for example](https://jubianchi.github.io/semver-check)

To turn on SemVer for your plugin, tick the **SemVer Only** option on the plugin page:

![SemVer Only](semver_ui.png)

If you tick this option, the Marketplace begins checking versions against SemVer rules with the next update upload. If the version meets the rules, Marketplace compares the maximum version among existing updates with the new update version. If the existing update has greater version than the new one, the update will be uploaded without changing the plugin page. Otherwise, the following fields will be extracted from the update [configuration file — plugin.xml](https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html):
* Plugin URL `<idea-plugin url="">`
* Name `<name></name>`
* Vendor information `<vendor url="" email=""></vendor>`
* Description `<description></description>`
If you try to upload a new update with the non-SemVer version you will receive the following error:

![SemVer Error](semver_error.png)

As of now, the main benefit to turn on the SemVer option is the ability to upload an update with minor fixes without changing the information on the plugin page. In the nearest future we will start sorting updates of the plugins with SemVer enabled by their version. As of now, the updates are sorted by upload timestamp.
