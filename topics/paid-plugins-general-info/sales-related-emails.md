[//]: # (title: Sales-related emails and in-product notifications to end users)

For plugins sold via Marketplace, we take care of sales-related communications like order request confirmations, renewal reminders, invoicing, and refunds.
The users of paid plugins on Marketplace receive the same automated email campaigns as JetBrains product users, which provides a consistent experience across platforms.

**We send the following emails to your evaluators and customers:**
* Quote request and quote expiration reminders.
* License certificates.
* License expiration messages (90, 45, and 14 days before license expiration for the Subscription Pack, as well as on the date of payment and 7 days after the subscription pack expires.

The Subscription Pack serves as a way to co-term subscriptions expiring at different times to the same expiration date. The notification includes information about all products a user is subscribed to, including paid plugins.

**Here are examples of the emails we send:**

<img src="email-example.png" alt="Example1" width="612"/>

<img src="email-example-2.png" alt="Example2" width="1066"/>

## In-product Notifications

Users receive notifications about new plugin versions and plugin license and trial expirations right inside their IDE. These messages prompt users to update plugins to the latest version, renew subscriptions, or buy and activate licenses.

<img src="email-in-product-notifications.png" alt="In-product Notifications" width="574"/>

## Plugin nurturing emails

These are campaigns developed specifically for users of plugins paid via Marketplace:
* **Welcome email**

This is delivered to users when they first activate a trial license of a plugin. 
This email contains a link to your plugin page, documentation, and bug tracker (if present on the plugin page). Please populate the dedicated fields in the plugin page admin settings with the links to these resources.

<img src="email-links.png" alt="Links" width="464"/>

* **Trial expiration reminder**

This email is sent at the end of the trial period and directs the user to the plugin pricing page.

* **Rate and review the plugin**

This email is sent to plugin users who purchased a plugin a month ago. It encourages them to rate and review the plugin.

Here’s how the emails look:

<img src="email-thanks.png" alt="Thank you" width="1192"/>

<img src="email-subscription.png" alt="Your Subscription" width="1048"/>

<img src="email-feedback.png" alt="Your Feedback" width="1221"/>

## How can I contact the users of my plugin directly?

According to the [JetBrains Plugin Marketplace Agreement](https://plugins.jetbrains.com/legal/terms-of-use), JetBrains can provide you with information about your plugin customers to enable communications related to plugin support,  sales-related information like pricing changes, and other necessary emails to keep customers using their plugins. JetBrains applies the data minimization principle in these handovers to make sure only relevant personal data is handed over for these purposes.

<warning><p>Please note, that JetBrains doesn't provide you direct access to customer information unless they have purchased the plugin.</p></warning>

In order to send product-related emails and marketing offers, you must explicitly get the user's consent. Consider adding a subscription form to your site, implementing an email collecting form in the product, or adding a link to your subscription center on the plugin page.

**You should also provide a link to your privacy policy. We recommend doing so as a custom link on your plugin page.**

<img src="email-privacy.png" alt="Privacy Policy" width="524"/>
