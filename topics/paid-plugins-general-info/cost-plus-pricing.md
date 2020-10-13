[//]: # (title: Cost-Plus Pricing)

Cost-Plus pricing is a pricing method in which the selling price is set by evaluating all variable costs a company / developer incurs, and then adding a markup percentage to establish the price.

| **Pros** | **Cons** |
| -------- | -------- |
| Simple, easy to use | You won’t necessarily know all your costs |
| You will cover your costs | As you grow, your costs will increase |
| | Costs fluctuate over time but you cannot change the price too frequently |
| | The cost-plus price does not consider the demand or competition factors |

To calculate a cost-plus price of a software product, it is necessary to take into consideration the following metrics: Cost of Goods Sold (CoGS), Customer Acquisition Cost (CAC), and Desired Margin.

```
Cost-Plus Price = CAC per customer + CoGS per customer + Desired Margin
```

For plugin developers that do not have any CAC, the formula will look like:

```
Cost-Plus Price = CoGS per customer + Desired Margin
```

### Cost of Goods Sold (CoGS)

Software developers might have CoGS such as product development and design, SaaS providers’ fees, cloud infrastructure, customer support, and the costs of the development team. If your business requires physical products, hardware, or custom development, the CoGS will likely be higher.

**For plugin developers** the CoGS may mostly include the amount of development time multiplied by hourly / daily wage and the costs of software used for development.

CoGS is usually calculated per customer. For simpler calculations, we may accept that one customer purchases one plugin license. Thus, it is necessary to project the number of plugins sold (in other words, how many people will buy a plugin) per some period of time. This is the trickiest part.

To forecast CoGS, it is helpful to **answer the following questions:**
* Who is my target audience?
* What is the size of my target audience?
* How many people from my target audience will probably buy my plugin?
* What is the average customer lifespan (approximate number of months / years that a customer will use my plugin)? Sometimes a **12-month period** is used as a rule of thumb.

You can find updated statistics from the [JetBrains Development Ecosystem](https://www.jetbrains.com/lp/devecosystem-2019/) survey and [StackOverflow](https://insights.stackoverflow.com/survey/2019#geography) to answer some of these questions. For instance, there you can check how many software developers are in different countries, what tools they use, and so on.

### Customer Acquisition Cost (CAC)

Customer Acquisition Cost is the average amount of money you have to spend to gain a new paying customer. It is one of the most critical metrics because it is usually higher than CoGS. However, for plugin developers, CAC can be zero if they do not spend money on the plugin promotion. For instance, this may apply if a marketplace takes over all promotional costs.

To calculate CAC:
* Determine your target months to recover: the period of time that you’d like to recoup your CAC. For this period, you can consider the average customer lifespan of 12 months.
* Sum your total sales and marketing expenses during that period, including your staff (marketing and sales team), advertising expenses, and overhead.
* Divide that number by the number of customers you acquired during that time period.

![Cost-plus-pricing](cost-plus-pricing.png)

*Source: [Getcheddar](https://www.getcheddar.com/blog/cost-plus-pricing-for-saas/)*

### Desired Margin

Unfortunately, there is no rule of thumb to estimate the net profit margin (residual earnings left after all expenses have been deducted from revenues). It varies depending on the company / business size, region, product features, and so on.

For example, the SaaS industry is known to have quite a high net profit margin of up to 80%, thanks to low CoGS in comparison with other business models. However, if we look at these [statistics](https://medium.com/datadriveninvestor/saas-margins-are-terrible-29ededa27e55) from 75 publicly traded SaaS companies, we can see that in reality their margins range from -62% up to 36%.

To decide on the desired net margin, take into consideration the following metrics:
* Your desired net profit: the amount of income that remains after accounting for all expenses.
* Projected number of plugins sold.
* The average customer lifespan.
* Competitor-based price.
* Value-based price.

**NOTE:** It is not recommended to estimate the plugin price via only cost-based analysis. The time a developer spends on creating a plugin can vary depending on many factors. Therefore, it is also important to pay attention to competitor-based and value-based pricing.