[//]: # (title: 6. Test the plugin licensing on the demo instance)

## Intro

JetBrains' Marketplace and Business Application Development teams prepared a fully-functioning Marketplace Demo instance for you which can be used for full testing of the paid plugins marketplace in a safe and protected environment. It is always kept functioning, so that you can test the whole solution before releasing it to the public.

You should have gotten your personal credentials to access the Marketplace Demo instance together with the Product Code assigned by JetBrains (credentials have been sent in a separate email for those who got the Product Code earlier.) If you don't have your credentials yet, please reach out to JetBrains via [marketplace@jetbrains.com](mailto:marketplace@jetbrains.com) email or other channels.

You need your credentials to access both the plugins repository part and the shop part, and you will need to provide your credentials separately for both of these separate applications (so it is normal that you might be required to re-provide your credentials when going from the plugins repository to the shop.)

Endpoints necessary for IDE functioning are open and don't require credentials to be accessed.

## Marketplace Demo Instance Limitations (!Important)

* It is an internal demo of the marketplace, please do not share the access, license keys generated or any other information you are getting at this internal demo.

* In order to route the IDE requests to the Marketplace Demo instance, you are modifying internal parameters of the IDE. Don't forget to remove custom *VM Options* and *Properties* after the testing, otherwise, your IDE experience might be disrupted at any time.

* It is NOT possible to generate offline license keys (aka Offline Activation Codes) at the demo stand due to security purposes. It will be possible to generate the offline license keys on production (read more about the offline keys at https://sales.jetbrains.com/hc/en-gb/articles/207240825-How-do-I-manage-and-distribute-licenses-within-my-organization-.)

* It is NOT possible to download plugins / updates which have been copied from Production instance of the plugins repository. Only plugins / updates uploaded to this Marketplace Demo instance will be accessible.

* Outgoing emails sent by the demo sales stand are available to all testers. Please use responsibly and don't use any confidential names / information there. Please note that information about the plugin you are testing might be exposed to other Marketplace program users who are using the same test stand, so please reach out to us if you can't allow that to happen - we'll arrange the private testing.

* The standard user we are normally using:

```
Email: test.test@gmail.com
Username: TestTest
Password: FJKDr478fdjhsj__
```

* The stand is cleared every Monday at 3 am in the morning (Central European Time), so all the plugins / purchases will be removed. Marketplace team will be re-uploading all plugins currently in a testing mode (incl. at least one demo plugin) at around 10 am Central European Time.

## Test Setup at the Marketplace Demo Instance

1. Access the Marketplace Demo instance at https://marketplace.demo.plugins.aws.intellij.net/, use credentials you have obtained from JetBrains. Unfortunately, you can't use the "sign in via Google Account" option as we can't connect it to non-JetBrains emails, use the username/password option:

![Marketplace Sign In](marketplace_sign_in.png)

**(!!!) Make sure to change the password on the first sign in.**

2. Upload update of your plugin (if existing) or a new plugin (if new) to the Marketplace Demo instance, use a standard procedure using the update plugin page (for existing plugin) and upload plugin page (for a new plugin.)

Please note that in order to upload the plugin, you need to sign in to the application with your normal Hub (https://hub.jetbrains.com) account, the same as you use on the production instance.

All the plugins from Production instance of the Plugins Repository uploaded before Monday should be available at this instance.

![Marketplace Update Plugin](marketplace_update_plugin.png)

1. Reach out to JetBrains via [marketplace@jetbrains.com](mailto:marketplace@jetbrains.com) email asking us to approve the plugin / update at the demo instance (if necessary) and add it to the Marketplace available for sales.

In order to make your plugin available for sales, we need the following information:

- Customer billing period (Annual, Monthly, Both.)

- Licensing type (Subscription, Subscription with Fallback.)

- Individual customers price (Monthly), in USD, yearly price is calculated as monthly price multiplied by 10.

- Businesses and organizations price (Monthly), in USD, yearly price is calculated as monthly price multiplied by 10.

And the following information will be needed for the accountancy to set the things up:

- Full Legal Name (e.g. full legal name of the company or your own full legal name if you are operating as an individual.)

- Full Address incl. Street, House Number, Post Code, City, Country.

- VAT ID (if applicable.)

- Additional information e.g. company registration ID, etc.

- Main contact name.

- Main contact email.

- Main contact phone (we will call you only in case of urgent questions if not reachable via email.)

**(!!!)** Please attach the plugin update to the email so that we can re-upload it for you after the Marketplace Demo instance is cleaned. You can send us additional builds of the plugin at the same thread.

1. JetBrains will process your request (normally should happen within 1-2 business days most), and will send you the confirmation.

Now you can start testing the plugin!

1. (can be done while you are waiting for the confirmation from JetBrains)
Configure your IDE to work with the Marketplace Demo Instance (read below.)

## Preparing an IDE for Tests with a Demo Environment

**(!!!)** In order to route the IDE requests to the Marketplace Demo instance, you are modifying internal parameters of the IDE. Don't forget to remove custom VM Options and Properties after the testing, otherwise, your IDE experience might be disrupted at any time.

### Configuring the IDE to work with a test Sales System

Marketplace Demo works with a Sales Systems Marketplace Demo https://mp.jpf-demo.aws.intellij.net

The IDE has to be additionally configured to work with it instead of the production JetBrains Account / Sales System.

Use `Help | Edit Custom Properties...` to open the `idea.properties` file in the editor and add

```
jb.service.configuration.url=https://mp.jpf-demo.aws.intellij.net/testservices/JetBrainsAccount.xml
```
 
### Configuring the IDE to work with a test Plugins Repository

Marketplace Demo runs on the test server https://marketplace.demo.plugins.aws.intellij.net/.

The IDE has to be additionally configured to work with it instead of the production Plugins Repository.

`Use Help | Edit Custom VM Options...` to open the `Intellij IDEA 2018.2.app.vmoptions` file (or similar depends on your version) in the editor and add

```
-Didea.plugins.host=https://marketplace.demo.plugins.aws.intellij.net/
```

Alternatively, you can add plugins to the IDE from disk.

## Where to get started with your Paid Plugin?

As soon as your plugin is marked as Paid Plugin available for sale by JetBrains, you will see *Buy* button at the plugin page:

![Plugin Buy](plugin_buy.png)

![Plugin Buy Page](plugin_buy_page.png)

All the Marketplace-related information about the plugin is available on a service page `https://marketplace.demo.plugins.aws.intellij.net/marketplace/info?pluginId={ID}` (the link is available at the Plugin Page - Marketplace.)

![Plugin Information](plugin_info.png)

## How to buy a plugin license

*{ID} = PRODUCT CODE*

### Personal license

Use the direct link to the shop: https://mp.jpf-demo.aws.intellij.net/shop/buy?item=P:N:{ID}:Y / https://mp.jpf-demo.aws.intellij.net/shop/buy?item=P:N:{ID}:M

For quote: https://mp.jpf-demo.aws.intellij.net/shop/quote?item=P:N:{ID}:Y / https://mp.jpf-demo.aws.intellij.net/shop/quote?item=P:N:{ID}:M

Or go to buy page from plugin overview: https://marketplace.demo.plugins.aws.intellij.net/plugin/{PLUGINID}

### Commercial license

Use the direct link on the shop: https://mp.jpf-demo.aws.intellij.net/shop/buy?item=C:N:{ID}:Y / https://mp.jpf-demo.aws.intellij.net/shop/buy?item=C:N:{ID}:M

For quote: https://mp.jpf-demo.aws.intellij.net/shop/quote?item=C:N:{ID}:Y / https://mp.jpf-demo.aws.intellij.net/shop/quote?item=C:N:{ID}:M

Or go to buy page from plugin overview: https://marketplace.demo.plugins.aws.intellij.net/plugin/{PLUGINID}

### Payment information on the checkout

At the checkout form, you need to use special test cards / payment information provided to us by Adyen (our payment provider): https://docs.adyen.com/development-resources/test-cards/test-card-numbers/

**(!!!)* Please make sure NOT TO USE real data, always use Adyen-provided data.

## How to view emails sent by the Sales System?

Due to the sensitivity of the data produced during the testing (such as license keys, order information, etc), we are not sending out any emails from the Marketplace Demo Sales Systems.

All of the outgoing emails can be viewed at a special URL: https://mp.jpf-demo.aws.intellij.net/emails

![System Emails](system_emails.png)

![System Emails View](system_emails_view.png)

**(!!!)** Please note that outgoing emails sent by the demo sales stand are available to all testers.

Please use responsibly and don't use any confidential names / information there. Please note that information about the plugin you are testing might be exposed to other Beta program users, so please reach out to us if you can't allow that to happen - we'll arrange the private testing.

## Useful Links Related to the Marketplace Demo Instance

* https://marketplace.demo.plugins.aws.intellij.net - Marketplace Demo

* https://mp.jpf-demo.aws.intellij.net/login - JetBrains Account

* https://mp.jpf-demo.aws.intellij.net/shop/buy/****** - Shop (requires additional parameters)

* https://mp.jpf-demo.aws.intellij.net/emails - Emails Viewer

## Known Issues

1. Buy plugin in the IDE will not land you at the Marketplace Demo instance, it will always land you at https://plugins.jetbrains.com. Should be removed in one of the upcoming updates of IntelliJ IDEA-based IDEs.

1. Some texts in the sales system are not updated and don't cover plugins (e.g. refers to them as "JetBrains product".) In progress.

## What to test?

You can see a general workflow in [this video](marketplace-video-demo.md).

You might consider testing the following parts of the system:

1. Plugins Repository Part

* Adding a Marketplace plugin

* Updating a Marketplace plugin (incl. releasing another version)

* Getting sales/pricing information from Sales System

* Buy pages and links

* Purchase Terms

* etc

1. Sales Systems Part

* Purchasing plugin via Store

* Orders/Quotes/etc via Sales System

* Sales Statistics

* Licenses issue workflow

* Emails sent

* Different scenarios

* etc

1. Product Part

* Evaluating a plugin

* Licensing a plugin via JBA

* Revoking a license

* Multiple plugins licenses

* Licenses with the different licensee

* etc

We also can arrange the expedited testing for you when JetBrains employee would go through the testing process together with you. Please reach out to us via [marketplace@jetbrains.com](mailto:marketplace@jetbrains.com) if you would prefer this option or have any issues.

Happy Testing!
