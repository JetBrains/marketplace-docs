[//]: # (title: Statistics: Product Versions in Use)

We are often asked by plugin developers which product versions should be supported by the plugin. It is logical not to release plugin updates for all the product versions released to the market, but rather focus on the latest / the most used versions of the product.

Previously, plugin developers would have to analyze their plugins downloads by the IDE version. For a more straightforward overview, we are publishing statistics that will help you decide which versions of products to support here.     

The statistics here has been gathered in August 2021, but looking into the older statistics, it doesn't change much over time.

| **Branch Number** | **IntelliJ Platform Version** | **Distribution** |
| -------- | -------- | -------- |
| 212 | 2021.2 | 35.37% |
| 211 | 2021.1 | 36.10% |
| 203 | 2020.3 | 13.38% |
| 202 | 2020.2 | 7.69% |
| 201 | 2020.1 | 4.88% |
| 193 | 2019.3 | 4.02% |
| 192 | 2019.2 | 2.36% |
| 191 | 2019.1 | 1.66% |
| 183 | 2018.3 | 1.26% |
| Pre-182 | Pre-2018.2 | 9.38% |

Please note, that the sum is more than 100%. It is because some users either used several IDE versions or updated their IDE during the current month.

In general, statistics show the following trends:

* It makes sense to support the latest major release, as well as at least two previous major releases (in this case, you are covering the majority of the users - on average, it's somewhat 80%.) This % doesn't change from product to product much.

* The latest version of the product is used by roughly 50% of the users (and it does take some time to upgrade to the newest version, especially in the companies, so it may be a bit lower at the moment).

* The latest major release minus three major versions have roughly 10% userbase.  

* The longer the product is on the market, the more significant is the portion of "Other versions" = versions older than "Latest major release -3" (which is logical, given that we used to have perpetual licenses and provide fallback licenses with our subscription offer).
