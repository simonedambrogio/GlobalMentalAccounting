## Analysis Plan - Statistical models

To test the replicability of the effects reported in the original papers we will run pooled and unpooled Bayesian analyses. For the pooled analyses, we will run a Bayesian meta-analysis. This approach will allow us to combine the information from all countries while respecting the hierarchical nature of the data. We will first calculate the effect size (theta) and the standard error (se_theta) of each scenario for each country separately. We will then use the R package brms (Bürkner, P., 2018)to fit a Bayesian meta-analysis, using the following formula

$$theta | se(se_{theta}) \sim 1 + (1|Country)$$

For the  unpooled  analyses,  we  will  compute  the  effect  size  for  each  scenario  and  country independently. We will then compare each of them with the effect sizes found inthe original papers. All analysis code and data will be made available on OSF. 

We will use Bayesian regression models described below to calculate the effect size for each scenario and country.

\vspace{12pt}

*"MrAB" scenarios*

To analyze the data from the first scenario we will use a Bayesian binomial regression model to estimate the probability of choosing the option "MrA" (as opposed to "MrB2"). We will contrast the two gain scenarios (scenario 1: gain-gain VS gain with scenario 3: gain-loss VS gain) and the two loss scenarios (scenario 2: loss-loss VS loss with scenario 4: loss-gain VS loss).  To  do  this,  we  will  run  two  separate  models  and  will  consider  only  the  subset  of participants who have selected either the "MrA" option or the "MrB" option.

$$\log \frac{p_{MrA}}{1 - p_{MrA}} = \beta_0 + \beta_1 \text{Scenarios Gain}$$

$$\log \frac{p_{MrA}}{1 - p_{MrA}} = \beta_0 + \beta_2 \text{Scenarios Loss}$$

Where Scenario  Gain and Scenario  Lossare  dummy  variables  indicating  (scenario  1  vs scenario3; scenario 2 vs scenario 4). The replication will be deemed successful if both $\beta_1$ and $\beta_2$ will be significantly bigger than 0.

\vspace{12pt}

*"Game" scenarios*

We will use a Bayesian binomial regression model to analyze the data from the second scenario. We will model the probability that the price participants are willing to ask is bigger or equal to the market value, as a function of the buyer.

$$\log \frac{p_{(\text{price} \geq \text{market value})}}{1 - p_{(\text{price} \geq \text{market value})}} = \beta_0 + \beta_1 \text{Buyer}$$

Where  Buyer  is  a  dummy  variable  (Friend  vs  Stranger).  The  replication  will  be  deemed successful if $\beta_1$ will be significantly bigger than 0.

\vspace{12pt}

*"Drink" scenarios*

To analyze the data from the third scenario we will use a Bayesian gamma regression model. We will estimate the mean willingness to pay difference between the "fancy resort hotel" and the "rundown grocery store" scenario.

$$log(\text{Price}) = \beta_0 + \beta_1 \text{Store}$$

Where $Store$ is  a  dummy  variable  (fancy  resort  hotel  vs  rundown  grocery  store).  The replication will be deemed successful if $beta_1$ will be significantly bigger than 0.

\vspace{12pt}

*"Jacket" scenarios*

We will use a Bayesian binomial regression model to analyze the data from the fourth scenario. We will model the probability to make the trip to the other store as a function of the price magnitude (high vs low).

$$\log \frac{p_{\text{Make Trip}}}{1 - p_{\text{Make Trip}}} = \beta_0 + \beta_1 \text{Price}$$

The replication will be deemed successful if $\beta_1$ will be significantly bigger than 0.

\vspace{12pt}

*"Play" scenarios*

We will use a Bayesian binomial regression model to analyze the data from the fifth scenario. We will model the probability to pay $40 for another pair of tickets as a function of the loss type (cash vs ticket).

$$\log \frac{p_{\text{pay } 40\$}}{1 - p_{\text{pay } 40\$}} = \beta_0 + \beta_1 \text{Loss Type}$$

The replication will be deemed successful if $\beta_1$ will be significantly bigger than 0.

\vspace{12pt}

*"Gym" scenarios*

We will use a Bayesian linear regression model to analyze the data from the sixth scenario. We will model participants' ratings about the feeling that they wasted $20 as a function of the frame (per session vs yearly)

$$Rating_{\text{wasted ~ \$20}} = \beta_0 + \beta_1 \text{Frame}$$

\vspace{12pt}

*"Plane" scenarios*

We will use a Bayesian linear regression model to analyze the data from the seventh scenario. We will model the probability that the most appropriate thing to do is to "Pay your friend \$35 for the coupon", as a function of the $coupon$ type (purchased vs free).

$$\log \frac{p_{\text{wasted } 20\$}}{1 - p_{\text{wasted } 20\$}} = \beta_0 + \beta_1 \text{Coupon}$$

The replication will be deemed successful if $\beta_1$ will be significantly bigger than 0.

For all $\beta$, the prior is assumed to be distributed as a normal distribution with mean 0 and standard deviation 5:

$\beta \sim Normal(0, 5)$

For a complete analysis plan please access the "Analysis Plan" section from the following link: [https://run.pavlovia.org/JDMLAB/mmar-supplementary](https://run.pavlovia.org/JDMLAB/mmar-supplementary)
