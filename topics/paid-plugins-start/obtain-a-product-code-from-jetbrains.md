[//]: # (title: 2. Obtain a Product Code from JetBrains)

Similar to JetBrains products, every plugin sold via JetBrains Marketplace has to obtain a **Product Code** from JetBrains. A Product Code is registered in the JetBrains Sales Systems and serves as a unique ID for all plugin-related sales operations. It also connects the Marketplace releases of the plugin to the Sales System.

Product Code for a plugin will be assigned to you by JetBrains based on the public name of your plugin.

Requirements:

* Should start with **P**.

* Should be **4** characters or longer.

* Should be **15** characters or shorter.

* Should **NOT** contain any numbers or special symbols.

* Should be in **CAPITAL LETTERS**.

Feel free to recommend us a product code of your choice during the initial communication - we'll gladly accept reasonable suggestions. We can't use *XMLID* as it doesn't conform to the Product Code format constraints and we didn't want to employ the same restrictions to *XMLID*.

Please note that changing a product code later is a very non-trivial process as we'll have to merge a lot of financial information and transactions, and additionally, we will have to maintain legacy product code in our systems for reference and backwards compatibility.

End-users will see a Product Code on the invoices, on the check-out page, and in the [JetBrains Account](https://account.jetbrains.com/).

JetBrains will be using extended Product Code attributing it with a type of subscription and subscription modifications, e.g. for *PhpStorm* the product code is *PS*, and a full table of extended Product Codes (or as we call them SKUs = Stock Keeping Unit) associated with this product would be:

<table>
<tr><td>SKU</td><td>Description</td></tr>
<tr><td>P-S.PS-Y</td><td>PhpStorm - Personal annual subscription</td></tr>
<tr><td>P-S.PS-Y-20C</td><td>PhpStorm - Personal annual subscription with 20% continuity discount</td></tr>
<tr><td>P-S.PS-Y-40C</td><td>PhpStorm - Personal annual subscription with 40% continuity discount</td></tr>
<tr><td>C-S.PS-Y</td><td>PhpStorm - Commercial annual subscription</td></tr>
<tr><td>C-S.PS-Y-20C</td><td>PhpStorm - Commercial annual subscription with 20% continuity discount</td></tr>
<tr><td>C-S.PS-Y-40C</td><td>PhpStorm - Commercial annual subscription with 40% continuity discount</td></tr>
<tr><td>P-S.PS-M</td><td>PhpStorm - Personal monthly subscription</td></tr>
<tr><td>P-S.PS-M-20C</td><td>PhpStorm - Personal monthly subscription with 20% continuity discount</td></tr>
<tr><td>P-S.PS-M-40C</td><td>PhpStorm - Personal monthly subscription with 40% continuity discount</td></tr>
<tr><td>C-S.PS-M</td><td>PhpStorm - Commercial monthly subscription</td></tr>
<tr><td>C-S.PS-M-20C</td><td>PhpStorm - Commercial monthly subscription with 20% continuity discount</td></tr>
<tr><td>C-S.PS-M-40C</td><td>PhpStorm - Commercial monthly subscription with 40% continuity discount</td></tr>
</table>
(PhpStorm is sold on annual and monthly subscription with 20%/40% continuity discount based on subscription length.)

SKUs for plugins will be a bit modified to include the type of the product in the product code, so all plugin product codes must have **P** as the first character.