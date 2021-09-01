[//]: # (title: Plugin Overview page)

The core elements of a plugin’s Overview page are extracted from the [Plugin Configuration File — plugin.xml](https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html) and cannot be changed without uploading a new plugin version. These extracted elements include the plugin’s name, a link to the plugin website (if there is one), the plugin’s description, and change notes. 

<chapter title="Plugin name">
    <p>The plugin’s name is added in the plugin.xml file, under the ```name``` tag. Use a short, relevant, memorable name that’s 1- 4 words long  (max 20 characters).</p>
</chapter>

<table>
    <tr>
        <td>
            ✅ Do:
        </td>
        <td>
            ❌ Don't:
        </td>
    </tr>
    <tr>
        <td>
<list>
<li>Write the name in the Latin alphabet (Exception: language packs).</li>
<li>Write the name in title case.</li>
<li>Use an original name. (Check whether the name you want is already in use on JetBrains Marketplace).</li>
</list>

<control>Example:</control>
<p>✅ "Plain Text Support"</p>
<p>❌ "Free Plain Text Support Plus Platinum Maximum Edition”</p>
        </td>
        <td>
<list>
<li>Use the word “Plugin” in the name.</li>
<li>Include “JetBrains” or supported JetBrains products in the name. (Compatible products are displayed separately on the plugin page).</li>
</list>
            
<control>Example:</control>
<p>❌ "XYZ CLion Plugin”</p>
<p>❌ "IntelliJer"</p>
<list>
<li>Infringe on any third-party trademarks.</li>
<li>Use punctuation marks when not explicitly needed or as a separator instead of spaces. (Some punctuation marks are permitted but discouraged).</li>
</list>

<control>Example:</control>
<p>❌ “XYZ.Language.Plugin”</p>
<list>
<li>Include functionality descriptions, version info, or other notes.</li>
</list>

<control>Example:</control>
<p>❌ “XYZ - Free Version”</p>
        </td>
    </tr>
</table>

<chapter title="Product compatibility">
</chapter>


The list of compatible products is displayed under the “Buy” or “Get” button (depending on whether you are publishing a free plugin or a paid one).

//SCREENSHOT

[The compatibility strategy](https://plugins.jetbrains.com/docs/intellij/plugin-compatibility.html) is determined by the plugin.xml file. You can also manually reconfigure the list of compatible products in the admin panel under the General Information section.

//SCREENSHOT