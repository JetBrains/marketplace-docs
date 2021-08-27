[//]: # (title: Release the Plugin)

<note>
    <p>
         Keep in mind that you are able to perform all the tests on our <a href="main-demo.md">Demo</a> instance before publishing your plugin to JetBrains Marketplace.
    </p>
</note>



Once everything is done, you are ready to start the release process.

1. Make sure that you have an [Organization](organizations.md) and that you have submitted your banking information under the *Vendor Information* tab.

<img src="test_org.png" alt="My Organizations tab"
width="460"/> <img src="VendorInfo.png" alt="Vendor Information tab"
width="354"/>




<tip><p>If you don’t see the tab for banking information, please contact us via <emphasis>marketplace@jetbrains.com</emphasis></p></tip>


2. Upload the plugin to <a href="https://plugins.jetbrains.com/">JetBrains Marketplace</a>.

<img src="plugin_upload.png" alt="A button for plugin upload"
width="540"/>

<warning>
    <p>
        Please make sure that your plugin meets all the  <a href="https://plugins.jetbrains.com/legal/approval-guidelines">requirements</a> and that you’ve correctly specified the <a href="notes-on-the-paid-plugins-versioning.md">plugin version and release date</a>.
    </p>
</warning>


3. Then transfer the plugin to your Organization by going to the plugin overview page and clicking the “Transfer to Organization” button:

  
<img src="transfer-button.png" alt="Add to Organization"
   width="460"/>

<tip>
    <p>
        If this button is not available, please make sure that you specified the <a href="https://plugins.jetbrains.com/docs/marketplace/organizations.html">Organization ID </a> correctly. Keep in mind that your Organization ID may differ from your Organization Name.
    </p>
</tip>


4. Go to the **Sales Info** tab on the Plugin page and select any community discounts you want your plugin to offer.

<img src="community_prog.png" alt="Select Community Programs"
   width="460"/>

Below the community programs, you will see the `Add to Marketplace` button. Press this button when you are ready to release your plugin.

<img src="add-to-market.png" alt="Add to Marketplace"
width="460"/>

<tip>
    <p>
        If you don’t see this button, please make sure you specified your banking information under the  <emphasis>Vendor Information</emphasis> tab for your <a href="https://plugins.jetbrains.com/docs/marketplace/organizations.html">Organization</a>.
    </p>
</tip>

<img src="sales_details.png" alt="Fill in the sales info"
width="460"/>

Please be careful when filling out this form. We recommend checking out our <a href="pricing-guidelines.md">Pricing Guidelines</a> and details on the supported <a href="licensing-schemes.md">Licensing Schemes</a>.

//NEED TO REWORK THIS PARAGRAPH 
If some fields need to be changed after submission, please write to the Marketplace Team at [marketplace@jetbrains.com](mailto:marketplace@jetbrains.com). Also note that the release version and release date are set in the `plugin.xml` file. To change these values, reupload the plugin with new values and remove any wrong plugin versions.

5. Once these steps have been performed, we will review your plugin within two business days. You will receive a notification as soon as the status of the review changes or if there are any questions regarding the approval of your plugin.


Once your plugin is up and running, it’s time to check out our articles about plugin management:


* Ranking Plugins
* Rating Plugins
* Discounts and Offers
* Plugin Statistics
* Notes on Information Changes

