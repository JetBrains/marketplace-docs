[//]: # (title: Plugins Rating)

The rating displayed for each plugin in the plugin repository, as well as within the product, is a Bayesian rating. The precise formula we are using is:

```
bayesianRating = (sum(userRatings) + 2 * meanPluginRating) / (count(userRatings) + 2)
```

It may be a bit confusing that the plugin rating is not 5 while all votes are 5. However, the reason for using the Bayesian rating is to avoid the situation when the plugin with a few 5 star votes are rated higher than the plugins having many diverse votes (meaning that not all of them are 5 stars.)

