[//]: # (title: Plugins Rating)

We are using a *Bayesian Rating* to calculate the rating displayed for each plugin in the plugin repository, as well as within the product. The precise formula we are using is:

```
bayesianRating = (sum(userRatings) + 2 * meanPluginRating) / (count(userRatings) + 2)
```

It may be a bit confusing that the plugin rating is not 5 while all votes are 5 stars. However, the reason for using the Bayesian rating is to avoid the situation when the plugin with a few 5-star votes is rated higher than the plugins having many diverse votes (and not all of them are 5 stars.)
