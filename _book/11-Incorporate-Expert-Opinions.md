# A11 Obtaining Predictive Distributions for Reserves Which Incorporate Expert Opinions - R. Verrall

## Cliff's Summary

Know how the model is defined with ODP and stochastic row parameters

Know the Bayesian BF calculation and assumptions

* $\operatorname{E}[c_{ij}] = Z_{ij} \overbrace{[(\lambda_j - 1) \underbrace{D_{ij-1}}_{\text{Actual up to }j-1}]}^{\text{CL Results}} + (1- Z_{ij}) \overbrace{[(\lambda_j - 1) \underbrace{M_i p_{j-1}}_{\text{Expected up to }j-1}]}^{\text{BF Results}}$

* $Z_{ij} = \dfrac{p_{j-1}}{\beta_i \varphi + p_{j-1}}$

Know the Stochastic column parameters calculation

### Types of Exam Questions

<span style="color:red">Haven't done TIA practice questions</span>

**Concepts**

* 2012 #8: Explain model as trade off between standard CL and BF
* 2013 #9: Model specification stuff on variance of the prior, BF bayesian
    * Bayesian vs Bootstrap: Provide expert opinion while maintaining the integrity of the variance estimates
    * Bayesian vs Mack: Provides full distribution of unpaid losses and not just the first 2 moments
* 2014 #10: Expert opinions in LDFs or row parameters; $\beta$ impact on the bayesian model

**Full Calculation**

* $\star$ [2012 #8](#2012-8): Bayesian model for BF method

## Introduction

Uses Bayesian techniques to allow incorporation of expert opinion and also maintain the integrity of the prediction error

* Take into account prior knowledge in setting reserves

* Calculating prediction error using prior knowledge

### Notation

**Claims**

$c_{ij}$ Incremental claims for AY $i$ and age $j$

$D_{ij}$ Cumulative claims = $\sum_{k=1}^j c_{ij}$

**Row Parameters**

$x_i$ Expected ultimate losses for AY $i$

**Column Parameters**

$y_j$ Expected % reported in each period; $\sum y_i = 1$

$p_j$ Expected reported to date $\sum_{k=1}^j y_k$

$\lambda_j$ Expected development from $D_{ij-1}$ to $D_{ij}$ ($= \dfrac{p_j}{p_{j-1}}$?)

$\hat{\lambda}_j$ Weighted average LDFs $= \dfrac{\sum_i D_{ij}}{\sum_i D_{ij-1}}$

### Incremental loss distribution

$c_{ij} \sim ODP(x_i \cdot y_j, \varphi)$
    
* $\mu = x_i \cdot y_i$
    
* $\sigma^2 = \varphi \cdot x_i \cdot y_i$

$c_{ij} \sim NB(\lambda_j D_{i, \: j-1}, \varphi \lambda_j (\lambda_j -1)D_{i, \: j-1})$

* NB has the exact same results as the ODP so we can use them interchangeably

Recall Mack method:

* $\operatorname{E}[D_{ij}] = \lambda_i D_{ij-1}$

* $\operatorname{Var}[D_{ij}] = \sigma^2 D_{ij-1}$

## Model Specification

Steps:

1) Assign prior dist^n^ to the column parameters

2) Incremental Loss $\sim NB$ (or ODP)

3) If vague priors (large variances) $\Rightarrow$ Bayesian chainladder

    * Prediction error will be similar to CL or slightly larger
4) If strong priors (small variances) $\Rightarrow$ We believe the prior means are appropriate

    * Prediction error will decrease
    
### Chain Ladder Intervention

Adjust LDFs for a development period for the recent years only

**Vauge Priors**

Large variance $\Rightarrow$ Parameter based on data

* Based on recent years average

**Strong Priors**

Small variance $\Rightarrow$ Prior mean has greater influence

### Last 3 Diagonals for LDFs

Use the last 3 diagonals for forecasting to account for CY effects or inflation etc

Pick large variance so data drive the parameter selection

### BF Intervention

Intervention on the level of each row $x_i$ (a-priori)

**Vauge Priors**

Large variance, less strong prior information $\Rightarrow$ Results between BF and CL

Lowers the prediction error but not as much

**Strong Priors**

Small variances, approximate the BF method

Prediction error comes down due to low variance in the prior

## Bayesian Model for BF Method

**Assumptions**:

$c_{ij} \sim ODP(x_i \cdot y_j, \varphi)$

$x_i \sim \Gamma(\alpha_i, \beta_i)$

* $\operatorname{E}[x_i] = \dfrac{\alpha_i}{\beta_i} = M_i$
    
* $\operatorname{Var}[x_i] = \dfrac{\alpha_i}{\beta_i^2}$

* Gamma because the numerical procedures work well (LogNormal is good too)

Mean and variance of $x_i$ is selected from outside the model and back out the parameters

* $\beta_i = \dfrac{\operatorname{E}[x_i]}{\operatorname{Var}[x_i]}$

* $\alpha_i = \dfrac{(\operatorname{E}[x_i])^2}{\operatorname{Var}[x_i]}$

**Model Results**:

<span style="color:red;background:yellow">Memorize Formula</span>

$\operatorname{E}[c_{ij}] = Z_{ij} \overbrace{[(\lambda_j - 1) \underbrace{D_{ij-1}}_{\text{Actual up to }j-1}]}^{\text{CL Results}} + (1- Z_{ij}) \overbrace{[(\lambda_j - 1) \underbrace{M_i p_{j-1}}_{\text{Expected up to }j-1}]}^{\text{BF Results}}$

$Z_{ij} = \dfrac{p_{j-1}}{\beta_i \varphi + p_{j-1}}$

* Large $\beta$ means small variance for the prior $\Rightarrow$ smaller $Z_{ij}$ $\Rightarrow$ less credibility on the actual loss

* $\varphi$, which represents process variance also has impact on the credibility

* Larger $p_{j-1}$ means more developed losses $\Rightarrow$ more credibility to actual losses

Notes:

* Benktander with different weights

* This is applied to *incremental* loss in the triangle

* $\varphi$ will be given

## Stochastic Column Parameters

BF above uses stochastic row parameters and deterministic column parameters

We can use stochastic process for both by first estimating the column parameters then the row parameters

For columns, prior dist^n^ is gamma with wide variance

$\operatorname{E}[c_{ij}] = (\gamma_i - 1) \sum \limits_{m=1}^{i-1} c_{m,j}$

* $\sum \downarrow$

* $\gamma_i$ is the new row parameters

    * This tells you the level of losses in the row relative to the rows above

* Similar to LDFs but just looking at it at the different angle

![](figures/Exam-7-Notes-2.png)

### Calculate Gamma

Know how to calculate this pictorially

Need to first use CL method to get ultimate loss and % unpaid by AY

$\gamma_1 = 1.000$ always

First calculate LDFs and calculate % unpaid and a-priori for each AY

* $U_i$ = a-priori ultimate based on LDF for AY $i$

* $q_i$ = % unpaid for AY $i$

![](figures/Exam-7-Notes-3.png)

Note that in step 4 above if you don't need the individual cells you can just take the $U_3 q_3$

## Past Exam Questions

<a name="2012-8"></a>
![](questions/2012-8Q1.png)
![](questions/2012-8Q2.png)
![](questions/2012-8A.png)