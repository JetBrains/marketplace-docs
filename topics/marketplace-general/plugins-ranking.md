[//]: # (title: Plugins Ranking)

JetBrains wants to create a fair and transparent marketplace for all – Developers (vendors and customers coming to the JetBrains’ Marketplace). To do so, we hereby outline how Plugins on our Marketplace are ranked when you either merely visit or search within the Marketplace.

When you are searching for a particular Plugin, we take the following 5 steps to provide you with a search result:

1. Firstly, we determine whether the Plugin's text fields inputted by the vendor match the customer’s request. We account for declensions, conjugations, articles, different ways of spelling, etc. The result of this step is a ranked list of Plugins — for every matching Plugin, we compute a numerical initial score that shows how relevant this Plugin is to a Customer’s search query. This initial score depends on the search engine settings (e.g. matches in different fields are scored differently). Only text fields (Pugin’s ID, name, description, tags, developer’s, or organization name) and Customer’s query are taken into account securing fair and equal treatment for all Plugins.
2. If the list of Plugins from step 1 contains featured Plugins, then we add to their initial score a coefficient to boost featured Plugins in the search results.
3. Subsequently, we take into account the popularity of each Plugin as we multiply the score from step 2 by the coefficient that is derived from the Plugin’s downloads. The coefficient is calculated as `log10(1 + 5 * downloads_count))`.
4. To also take into account the Plugin’s quality, we multiply the score from step 3 by the coefficient that depends on the Plugin’s rating. The coefficient is calculated as `sqrt(rating)` (square root of the Plugin’s rating) and the rating formula is outlined [here](https://plugins.jetbrains.com/docs/marketplace/plugins-rating.html).
5. Finally, we are applying Customer sorting. If the Relevance sorting is selected, then we show results ranked by the score from step 4, from highest to lowest. If some other sorting is selected (by name, downloads, update date, rating), then we rank results by this field and then by the score.

When you merely visit our Plugin Marketplace, you see several preselected Plugin categories for your easier navigation. The respective Groups contain Plugins based on the below principles:

* “Featured” Plugins are preselected by JetBrains’s product team based on current trends and preferences of the users. Featured Plugins are product specific and unique for each product line (IDEs, .NET, Team Tools).
* “New and Updated” Plugins are ranked by the date when the last Plugin update was uploaded to JetBrains servers, starting from the most recent date on top of the list.
* “Top Downloads” Plugins are ranked by the number of downloads per each Plugin, starting from the Plugin with the greatest number of downloads on top of the list.
* “Top Rated” Plugins are ranked by the Plugins’ rating, starting from the Plugin with the highest rating on top of the list.

Note: ‘New and Updated’, ‘Top Downloads’, and ‘Top Rated’ categories display top search results for empty Customer queries and sorting (by update date, downloads, and rating respectively). Thereby we rank Plugins by this field and then by the score (see step 5 in the above algorithm for search queries).

All of the above work the same for IDE Plugins, .NET Plugins, Team Tools Plugins, etc.
