[//]: # (title: Notes on the paid plugins versioning)

There have been no constraints imposed on the plugin version format for plugins before the Marketplace introduction, but it seems that we have to introduce them now for paid plugins sold via JetBrains Marketplace. The primary reason for that is the simplicity of the unification of the versions so that there are no issues with non-standard versions in regards to the licensing mechanisms.

Let us give you a bit more context about how our products (and many of our plugins) releases are versioned. A few years back we have [introduced changes to its release and versioning](https://blog.jetbrains.com/blog/2016/03/09/jetbrains-toolbox-release-and-versioning-changes/), and we are pleased with this decision, so we'd recommend you to align your plugin release version numbers with JetBrains release version numbers for further sync (as users already know how the model works for our products.)

## Release Version Constraints

It's important to note that we would like to be as flexible as possible, so we don't have intentions to "lock" you to our versioning model, and the only rules we introduce are:

* The version number should be an `integer` (dots and other special symbols CAN be there, but WILL be ignored.)

* The next version should be bigger than the previous one (versions can't be descending.)

* The version number should consist of at least two characters.

You can easily use multi-component version numbers, and these constraints let you release your plugins with version numbers such as 2018.1, 2018.1.2, 1.1, 1.1.0, etc.

**(!) These are the rules for paid plugins via JetBrains Marketplace only, and they are not applied to other plugins.**

## release-version vs. version

[Paid plugins related changes](prepare-your-plugin-for-publication.md) to the plugin descriptor (*plugin.xml*) introduced a `release-version` in addition to the existing `version` parameter, and this part requires an additional explanation.

`version` parameter has been used for a long time as a full version number. It is used by the IDE and plugins repository to define the latest compatible update of the plugin for an IDE build so that it can be offered to be installed or downloaded.

`release-version` is related to licensing of the paid plugins, and it is different from the `version` of the plugin, as this one is a version number of the major release (i.e., release which happened on `release-date`). You shouldn't put a minor release version here to make sure that perpetual fallback license holders get access to minor updates of the major version.

For major releases (e.g., *2018.1*), `version` is going to be equal to `release-version`, but they would be different for minor releases (e.g., for a minor update of the plugin the `version` will be *2018.1.1*, and the `release-version` will be *2018.1*).

Please note that `release-version` is `integer`, so the *2018.1* version will be converted to *20181* when compared/used by the IDE. You can put it as *20181* to *plugin.xml* from the very start.
