[//]: # (title: Start testig on Marketplace Demo)

Once you have [obtained the credentials](demo-obtain-creds.md) and gotten familiar with the [Marketplace Demo limitations](demo-limitations.md), you’re ready to hop in and start your tests.

<note>
<p>Please note that information about the plugin you are testing might be exposed to other Marketplace program users who are using the same test stand.</p>
</note>

## Marketplace sign in

Please access the [Marketplace Demo instance](https://master.demo.marketplace.intellij.net/) and use the credentials you have [obtained](demo-obtain-creds.md) from JetBrains. Unfortunately, you can't use the "sign in via Google Account" option, as we can't connect it to non-JetBrains emails (the JetBrains team should use the "sign in via Google Account" option exclusively). Use the username/password option.

<warning>
<p>Make sure to change the password on the first sign in.</p>
</warning>


## Marketplace Demo plugin upload

Once you access the Marketplace Demo instance, you should log into the Marketplace application itself:

<img src="hub-login.png" alt="Hub Login Window"
width="354"/>

Please use your normal [Hub](https://hub.jetbrains.com) account, the same as you would use on the production instance.

After that, feel free to upload a new plugin following the steps described in the [Release the Plugin](release-plugin.md) section. Once all the steps are completed, please reach out to the JetBrains team via [marketplace@jetbrains.com](mailto:marketplace@jetbrains.com) or [Slack](https://plugins.jetbrains.com/slack) asking us to approve the plugin. We’ll review it within 1-2 business days and send you a confirmation.

<note>
<p>You might notice plugins copied from the Production instance. Please keep in mind that it is NOT possible to download such plugins/updates. Only plugins/updates uploaded to this Marketplace Demo instance will be accessible.</p>
</note>


As soon as your plugin is approved, it will be marked as a Paid Plugin available for sale. You as a plugin vendor should see the “Pricing” tab here:

<img src="pricing-admin.png" alt="Pricing page for a vendor"
width="460"/>

To see how it would look to the end-user, please switch to the preview mode here:

<img src="pricing-user.png" alt="Pricing page for a user"
width="460"/>

## How to test the purchase process?

Please change the link accordingly where ```{ID}``` = PRODUCT CODE

### Personal license

<emphasis>Use the direct link to the shop:</emphasis>

* https://mp.jpf-demo.aws.intellij.net/shop/buy?item=P:N:```{ID}```:Y
* https://mp.jpf-demo.aws.intellij.net/shop/buy?item=P:N:```{ID}```:M

<emphasis>For a quote:</emphasis>
  
* https://mp.jpf-demo.aws.intellij.net/shop/quote?item=P:N:```{ID}```:Y  
* https://mp.jpf-demo.aws.intellij.net/shop/quote?item=P:N:```{ID}```:M


<emphasis>Or go to buy page from the plugin overview:<emphasis>

* https://marketplace.demo.plugins.aws.intellij.net/plugin/```{ID}```

### Commercial license

<emphasis>Use the direct link on the shop:</emphasis>

* https://mp.jpf-demo.aws.intellij.net/shop/buy?item=C:N:```{ID}```:Y
* https://mp.jpf-demo.aws.intellij.net/shop/buy?item=C:N:```{ID}```:M

<emphasis>For a quote:</emphasis>

* https://mp.jpf-demo.aws.intellij.net/shop/quote?item=C:N:```{ID}```:Y 
* https://mp.jpf-demo.aws.intellij.net/shop/quote?item=C:N:```{ID}```:M


<emphasis>Or go to buy page from the plugin overview</emphasis>

* https://marketplace.demo.plugins.aws.intellij.net/plugin/```{ID}```

### Payment information on the checkout

At the checkout form, you need to use special test cards/payment information provided to us by Adyen (our payment provider): [https://docs.adyen.com/development-resources/test-cards/test-card-numbers/](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/)


<warning> 
<p>Please make sure NOT TO USE real data, only use the Adyen-provided data.</p>
</warning>

## How to test emails sent by the Sales System?

Feel free to check all the emails you as a user might receive: sign up, license purchase, etc.

Due to the sensitivity of the data produced during the testing (such as license keys, order information, etc.), we don’t send out any emails from the Marketplace Demo Sales Systems.

That is why all of the outgoing emails can be viewed at a special URL: [https://mp.jpf-demo.aws.intellij.net/emails](https://mp.jpf-demo.aws.intellij.net/emails)

Please create a test user with credentials similar to this:

```Email: test.test@gmail.com```

```Username: TestTest```

```Password: FJKDr478fdjhsj__```


<note>
<p>Please note that outgoing emails sent by the Marketplace Demo sales stand are available to all testers.</p>
</note>

Please use responsibly and don't use any confidential names/information there. Please note that information about the plugin you are testing might be exposed to other Beta program users. If you need private testing, please reach out to us and we’ll try to arrange it.


## What to test?


You might consider testing and reviewing your plugin:


<emphasis>As a Vendor:</emphasis>

* Review Vendor Cabinet
* Update a plugin (new version upload)
* Check Pricing information and Sales Info
* Review Purchase Terms



<emphasis>As an User:</emphasis>


* Evaluate a plugin
* Purchase plugin via the Store
* Orders/Quotes/etc. via Sales System
* Emails



Feel free to reach out to us via [marketplace@jetbrains.com](mailto:marketplace@jetbrains.com) if you have any issues or require our assistance.

Happy testing!

The Marketplace team