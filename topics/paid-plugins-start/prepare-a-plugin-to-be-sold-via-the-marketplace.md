[//]: # (title: 3. Prepare a plugin to be sold via the marketplace [plugin.xml parameters])

Every plugin sold via JetBrains Marketplace must define [additional parameters in the plugin descriptor (plugin.xml)](https://www.jetbrains.org/intellij/sdk/docs/basics/plugin_structure/plugin_configuration_file.html) in the `<product-descriptor>` tag, such as:

1. `code` - a Plugin Product Code obtained from JetBrains on the previous step (type: `varchar`, 15 characters max.)

It is used to "connect" a particular plugin to a product in JetBrains sales systems.

Please see [this article](obtain-a-product-code-from-jetbrains.md) for full requirements for the Product Code.

2. `release-date` - date of the major version release in a format of `YYYYMMDD` (type: `integer`).

It is a crucial parameter as the whole subscription model depends on it - perpetual fallback licenses and licensing term calculation rely on the `release-date`.

3. `release-version` - a major version number (type: `integer`).

It is different from the version of the plugin, as this one is a version number of the major release (== release which happened on `release-date`). You shouldn't put a minor release version here to make sure that perpetual fallback license holders get access to minor updates of the major version.

(please read a [separate article on the versioning of paid plugins](notes-on-the-paid-plugins-versioning.md))

Example:

```xml
<product-descriptor code="PPAIDPLUGIN" release-date="20180918" release-version="20181"/>
```


Means that a plugin with a Product Code `PPAIDPLUGIN` had its major version release (`2018.1`) on `June 20th, 2018`. Subsequent minor updates (e.g., `2018.1.1`, `2018.1.2`, `2018.1.x`) should have the same `release-date` and `release-version` before the next major version is released (`2018.2`) so that those users who have got a perpetual fallback license can use an opportunity to get the latest minor update of the major version they have got an access to.