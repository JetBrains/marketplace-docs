[//]: # (title: How to add required parameters for paid plugins)

Every plugin sold via JetBrains Marketplace must define the following parameters in the [plugin descriptor (plugin.xml)](https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html), which can be found in the `<product-descriptor>`:

1. `code` - a [Plugin Product Code](obtain-a-product-code-from-jetbrains.md) obtained from JetBrains (type: `varchar`, 15 characters max.).
   This is used to connect a particular plugin to a product in the JetBrains Sales system.

2. `release-date` - date of the major version release, written in the ‘YYYYMMDD’ format (type: `integer`).

This is one of the most crucial parameters, as the subscription model depends on it. [Perpetual fallback licenses](https://sales.jetbrains.com/hc/en-gb/articles/207240845-What-is-perpetual-fallback-license-) and licensing term calculations rely on the `release-date` and `release-version`.

3. `release-version` - a major version in a special number format (type: `integer`). 

The number should contain at least 2 digits, as it will be split into 2 numbers, the second of which will contain only one digit. Take, for example, `release-version=20201`. The first number would be `2020` and the second one `1`.  

This is different from the [version](notes-on-the-paid-plugins-versioning.md) of the plugin, as this is a version number of the major release (i.e. the release that happened on `release-date`). 

<note>
<p>Please make sure the `release-version` and the ‘version’ parameters match. They should have similar integers at the beginning, like `release-version=20201`  and `version=2020.1.1.`</p>
</note>

Let’s take a look at an example:

The initial release of a new plugin will be the first major release. That is why the parameters will look something like this in the plugin.xml file:


 ```xml
    <product-descriptor code="PTESTPLUGIN" release-date="20210818" release-version="20211"/>
<version>2021.1.0</version>
   ```

<note><p>If you’re building the plugin with Gradle, the plugin version is defined in the plugins section of a project's build.gradle file. For more detailed information, please refer <a href="https://plugins.jetbrains.com/docs/intellij/gradle-guide.html#controlling-downloads-by-the-gradle-plugin">here</a>.</p></note>

According to the `release-date` parameter, this plugin can be purchased starting from `August 18, 2021`. Its major version release is `2021.1`, and that number should not be changed in your further minor updates. As for the `version` parameter, it is equal to `release-version` initially, but it will be different for minor releases. 

Here is an example of a minor update: 

 ```xml
    <product-descriptor code="PPAIDPLUGIN" release-date="20210818" release-version="20211"/>
    <version>2021.1.1</version>
```


As you can see, only the `version` parameter has been changed. Subsequent minor updates (e.g. `2021.1.1`, `2021.1.2`, `2021.1.x`) should have the same `release-date` and `release-version`. This will allow your users who have a perpetual fallback license to get the latest minor update of the major version they have access to. 

<tip><p>A plugin version with an altered `release-version` and `release-date` is considered a new stable version of the plugin, and in this case the current active trial licenses are reset.</p></tip>

4. `optional` – not a required parameter (type: `boolean`). This should be set to `true` if you would like to add the free functionality to your plugin. Please see [this article](free-functionality.md) for more information about free functionality. The default value of this parameter is `false`.
