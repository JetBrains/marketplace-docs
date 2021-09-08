[//]: # (title: Plugin Overview page)

The core elements of a plugin’s Overview page are extracted from the [Plugin Configuration File — plugin.xml](https://plugins.jetbrains.com/docs/intellij/plugin-configuration-file.html) and cannot be changed without uploading a new plugin version. These extracted elements include the plugin’s name, a link to the plugin website (if there is one), the plugin’s description, and change notes.

## Plugin name

The plugin’s name is added in the plugin.xml file, under the ```name``` tag. Use a short, relevant, memorable name that’s 1- 4 words long  (max 20 characters).

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

## Product compatibility


The list of compatible products is displayed under the “Buy” or “Get” button (depending on whether you are publishing a free plugin or a paid one).

<img src="compatibility.png" alt="Compatibility Overview Page"
width="706"/>

[The compatibility strategy](https://plugins.jetbrains.com/docs/intellij/plugin-compatibility.html) is determined by the plugin.xml file. You can also manually reconfigure the list of compatible products in the admin panel under the General Information section.

<img src="compatibility2.png" alt="Compatibility Admin Page"
width="460"/>

## Plugin description

The plugin description should be added to the plugin.xml file under the ```description``` tag. It can contain most HTML tags, and it is displayed in the Plugin Manager inside JetBrains IDEs and on the plugin listing page on [JetBrains Marketplace](https://plugins.jetbrains.com/).

Make sure your description is concise and offers a clear value proposition. It should be easy to understand at a glance what the product offers.

<img src="testplugin.png" alt="Description Example"
width="460"/>

<table>
    <tr>
        <td>
            ✅ DO:
        </td>
        <td>
            ❌ DON’T:
        </td>
    </tr>
    <tr>
        <td>
            <list>
               <li>Use English as the primary language (the English description should come first if you decide to include localized descriptions).</li>
               <li>Use correct spelling and grammar.</li> 
               <li>Use direct wording and avoid the use of marketing adjectives like "simple", "lightweight", or "professional".</li>
            </list>
        </td>
        <td>
            <list>
               <li>Reference brands that you’re not affiliated with.</li>
               <li>Make unverifiable claims.</li>
               <li>Include inappropriate content, such as the promotion of third-party services,  profane or offensive language, etc.</li>
               <li>Use non-standard capitalization, unless it’s a part of a brand name.</li> 
            </list>
        </td>
    </tr>
</table>

<control>Tips and Tricks:</control>

* The first line of the plugin description should contain a short plugin summary in English (up to 170 characters). This will be used for the plugin’s preview card on the  Marketplace site. Note that you can’t amend the text of a plugin card separately. You can also [embed](embeddable-content.md) the card on your website.
* Make sure that your description has been proofread and that it is formatted properly before you upload your plugin.
* Use bullet points to describe the plugin’s main benefits.
* Put some inline links to useful resources (issue tracker, forum, etc.) to the description. This way, the links will be available from the Plugin Manager inside IDEs.
* Draft the description with SEO keywords in mind, but please avoid keyword stuffing.

## Plugin logo

The plugin logo should be added directly to the plugin’s distribution file. You can find the detailed requirements and instructions on how to add the plugin logo [here](https://plugins.jetbrains.com/docs/intellij/plugin-icon-file.html). The general recommendation is to use a simple, recognizable, eye-catching image. It is better to avoid including text, but If the logo contains it, the text should be readable.

<note><p>Note, that you can choose not to use a logo.</p></note>

<control>❌ DON’T:</control>

* Use the [default logo](https://github.com/JetBrains/intellij-platform-plugin-template/blob/main/src/main/resources/META-INF/pluginIcon.svg) of the [IntelliJ Platform Plugin Template](https://github.com/JetBrains/intellij-platform-plugin-template) or [IntelliJ SDK Code Samples](https://github.com/JetBrains/intellij-sdk-code-samples).
* Create a logo that merely consists of text repeating your plugin name.
* Use a logo that resembles any of the JetBrains product logos or the logos of any other brands.


## Media


The media section is the first element that users will see on the plugin page, and it is one of the best ways to show your plugin in action. You can add screenshots and video under the Media section in the admin panel of the plugin page after uploading your plugin.

<img src="media.png" alt="Fields for Media"
width="460"/>

<control>Screenshots</control>

We recommend adding screenshots that display plugin features. You can use a gif showing some action or add overlay text to clarify what a screenshot depicts.
Note: Theme plugins must have screenshots that display the visual style they provide.
The recommended screenshot size is 1280 x 800 px (16:10 aspect ratio). You can also add informational slides in addition to screenshots.

<table>
    <tr>
        <td>
            ✅ DO:
        </td>
        <td>
            ❌ DON’T:
        </td>
    </tr>
    <tr>
        <td>
            <list>
               <li>Display the interface of the relevant JetBrains product.</li>
               <li>Use the default IDE theme in screenshots (Exception: theme plugins should represent the visual style they provide)</li>
               <li>Use high-quality images with legible texts.</li>
               <li>Include only relevant information.</li>
            </list>
        </td>
        <td>
            <list>
                <li>Upload screenshots with different aspect ratios.</li>
                <li>Add screenshots that misleadingly represent your plugin.</li>
                <li>Advertise third-party products or brands or include any other content unrelated to plugin functionality.</li>
                <li>Include any personal information.</li>
                <li>Include desktop backgrounds and browser windows in your screenshots.</li>
            </list>
        </td>
    </tr>
</table>

<control>Video</control>

If you've got a product video on YouTube, you can add the URL to it. We recommend using a short promo or demo video that’s less than 5 minutes long. A video can help you improve user interaction with your listing.


## Tags

Plugin tags are displayed above the plugin name on the plugin page and are used as search filters. You should select at least one plugin tag while uploading the plugin (in the Plugin Upload form). You can also change tags later under the General Information section on the admin panel.

<img src="tags.png" alt="Fields for Tags"
width="460"/>

Choose your tags wisely, as they will affect searchability. Don’t select categories that the plugin does not fit. If you feel that an appropriate tag is missing, please contact the Marketplace team at [marketplace@jetbrains.com](mailto:marketplace@jetbrains.com), and we will consider adding it.

## General Usage Instructions

You can choose to add general usage instructions to your page on the admin panel. These instructions will be displayed on the plugin page,  and you can use HTML tags to add formatting. Consider outlining the key steps for getting started, such as how to install and configure your plugin. These instructions should not include just  a link to an external help doc. Additional instructions can be added to the Documentation URL or to a [Custom page](custom-pages.md).

<img src="general-instructions.png" alt="Fields for instructions"
width="460"/>

Use concise, action-oriented headlines, and structure them clearly: (e.g. “1. Launch IDE 2. Go to File -> Settings -> Tools to configure the plugin...”)


## Change Notes


Change notes help you track the progress you’ve made on your plugin, introduce new features, announce changes, and recap bug fixes.

To add change notes, write a short summary of the changes in a new plugin version inside the ```change-notes``` tag of the plugin.xml file. The latest change notes will be displayed in the What’s new section of a plugin page and in the Plugin Manager inside IDEs. If there are too many change notes, please consider adding them as a [Custom page](custom-pages.md) and providing a link to it or to an external page in the change notes.

## Plugin Links

You can add links to your website, issue tracker, forum page, source code, documentation, and license to your plugin page. They will be displayed in the Additional Information section.

Please make sure that all of the external links on your plugin page are reachable from the internet. If you add a source code repository link, please make sure that it is publicly available.

<img src="additiona-info.png" alt="Additional Information"
width="460"/>

In order to display your vendor site and email address on the Plugin page, you should fill in the optional "url" and “email” attributes in the plugin.xml file:


```
 <vendor url="https://www.company.com" email="support@company.com"> Company Inc.</vendor>
 ```

Note that if you have a plugin transferred to an [Organization](organizations.md), the Vendor link will lead to an organization page.
Links to the bug tracker, forum, and source code can be added in an admin panel under the Technical Information section.
The license link should be added upon upload (in the Plugin Upload form) and can be edited in the General Information section.

A vendor website can be added in the plugin.xml file:

```
 <idea-plugin url="https://www.com.com/plugin">.
```

Note that the “Plugin homepage” link in the plugin manager in IDEs links to your Marketplace plugin page, not the website you specified under the ```idea-plugin``` tag.

<img src="homepage.png" alt="Plugin Homepage"
width="460"/>