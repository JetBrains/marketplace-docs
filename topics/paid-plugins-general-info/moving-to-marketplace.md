[//]: # (title: Moving to the marketplace from other licensing/billing solutions)

## When to switch to the Marketplace?

We generally recommend switching to the Marketplace solution with the plugin version update, so that the following workflow can be followed:

1. Users are using a legacy licensing solution (e.g. until version 1.9.1.)

1. Plugin developer announces that they are going to switch to another licensing solution and provides migration paths. Please note that there might be contractual obligations you have to follow (based on your EULA or contract with customers.)

1. Version 2.0.0. is released with the Marketplace licensing, users migrate to it over time, version 1.9.1 and previous are still available with the old licensing solutions.

It might be technically possible to support both licensing mechanisms for some time in a single plugin, but it might complicate troubleshooting and licensing support, that's why we recommend switching to the Marketplace with the version update.

## Different users migration paths

In general, we have a rather simple migration process performed (on the technical side) via REST API or simple CSV upload on our side.

The migration process is greatly complicated by the privacy protection mechanisms we have to employ to protect the personal information of your customers.

You, and not JetBrains, have a right to access and process the personal data of your customers, that's why we can't simply accept a list of customers and issue the licenses to them as a part of the migration process. We need to make sure that the data is passed according to GDPR and other regulations covering personal data protection.

We have come up with three ways of migration:

### GDPR-compliant customers list passed from Plugin Developer to JetBrains

1. Plugin Developer reaches out to the customers and obtains explicit permission to transfer their personal data to JetBrains as a part of the migration process.

1. Plugin Developer signs a special data sharing agreement with JetBrains. The agreement describes the process of data transfer and following processing of the personal data.

1. Plugin Developer provides a list of customers with the required data (name, email, billing address, license term, etc - see below the data we require for different types of customers.)

1. JetBrains will generate licenses for those customers in a new format (so that you can switch them to the marketplace.)

1. JetBrains will send out license keys and other information to the customers so that they switch the license (as soon as your plugin is sold on the marketplace.)

### End-user submitting the information directly to JetBrains (verified by Plugin Developer)

1. JetBrains publishes a special Landing Page which has a form for personal data submission (everything required for a license to be issued.) The form also contains a disclaimer of data shared with JetBrains (and the following data sharing with the plugin developer is done as of the Marketplace Developer Agreement.)

1. Plugin Developer sends the link to the page to their customers (end-users of the plugin) asking them to submit the information.

1. End-users submit the information at the page, notification is sent to JetBrains and Plugin Developer.

1. Plugin Developer confirms the validity of the license for the end-user submitting the form.

1. JetBrains issues the license to the end-user.

### JetBrains generates special coupon codes to be provided at the check-out by end-user (distributed by Plugin Developer)

1. Plugin Developer informs JetBrains on the number of existing customers of various types (personal, commercial, and their validity of licenses.)

1. JetBrains generates special coupon codes and passes them to the Plugin Developer.

1. Plugin Developer distributes the coupon codes to the end-users (customers.)

1. Coupon codes are used by the plugin end-users (customers) to issue a license to their email.

Please note that these migration workflows can be combined.

## Required information

### What information do we need to issue licenses for individual customers

* First Name

* Last Name

* Email

* Country

* (optional) Phone

* Billing address

* * Address

* * City

* * ZIP Code

* License validity (date from YYYY-MM-DD ... to YYYY-MM-DD)

### What information will we need to issue licenses for commercial customers

* Company Name

* First Name

* Last Name

* Email

* Country

* (optional) Phone

* Billing address

* * Address

* * City

* * ZIP Code

* License validity (date from YYYY-MM-DD ... to YYYY-MM-DD)

* Number of licenses (for a bunch of licenses of different validity)

We won't add past orders with $$$ to our systems not to screw up the revenue statistics and commission calculation, but we can add such (or any other) information in the order / customer notes.
