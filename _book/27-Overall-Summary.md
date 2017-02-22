# (PART) Overall Summary {-}

# Exam 7 2016 Overall Summary

## Section A

### A1 Least Square

Loss Development Using Credibility - Brosius

Least square methods

* Need to know how to calculate $b$

Theoretical Bayesian method and also estimating the Bayesian credibility with 2 methods for getting $Z$

* Can do $Z = \dfrac{b}{c}$ or the VHM EVPV formula
* Under certain relationships between $X$ and $Y$ supports different methods
* Some formulas to remember if we do the theoretical Bayes

Discussion on the caseload effect where the development and ultimate is not independent

### A2 Benktander

Credible Claims Reserve: The Benktander Method - T. Mack (2000)

Benktander Method

### A3 Credible Claims Reserve

Credible Claims Reserve: Benktander, Neuhaus and Mack - W. Hurlimann

Method that is based on the incremental loss ratio triangles

Weight between the analogous development and BF method

$R_i^c = Z_iR_i^{ind} + (1-Z_i)R_i^{coll}$

| $Z_i$ | Method |
| --- | --- | --- |
| 1     | Chainladder; Individual LR|
| 0     | BF; Collective LR|
| $p_i$ | Benktander |
| $p_i \times ELR$ | Neuhaus |
| $Z = \dfrac{p_i}{p_i + \sqrt{p_i}}$ | Optimal |

### A4 High Deductible

A Model for Reserving Workers Compensation High Deductibles - J. Siewert

Covers 6 methods for dealing with deductibles each with their own pros and cons

1) Loss Ratio Method:  
Apply occurence and aggregate charges

2) Implied Development:  
Calculate as the difference between unlimited and limited

3) Direct Development:  
$XSLDF_t^{L} = \dfrac{Ult_{XS}}{S_t^{XS}} = \dfrac{Ult \cdot \chi}{\frac{Ult}{LDF_t} - \frac{Ult\cdot(1-\chi)}{LDF_t^L}}$
    
4) Credibility Weight Method:  
Weight between direct development and expected loss ratio method

5) Development Method

    * Severity needs to be trended
    * Claim counts are developed separately ground up
    * Severity LDF formulas, know them well to manipulate and know what formula requires what
    
        * $LDF_t^L = LDF_t \dfrac{R^L}{R_t^L}$
    
        * $XSLDF_t^L = LDF_t \dfrac{(1-R^L)}{(1-R_t^L)}$
    
        * $LDF_t = R^L_t \cdot LDF^L_t + (1 - R^L_t) \cdot XSLDF^L_t$
    
        * $\dfrac{ILDF^L_t}{ILDF_t} = \Delta R^L_t = \dfrac{R^L_{t+1}}{R^L_t}$

        * $\dfrac{IXSLDF^L_t}{IXSLDF_t} = \Delta (1 - R^L_t) = \dfrac{1 - R^L_{t+1}}{1 - R^L_t}$

6) Distribution Method

### A5 Developement by Layer

Claims Development by Layer - R. Sahasrabuddhe

Know the process for setting up [base](#a5-1) triangle and then [convert](#a5-2) the base LDFs to any layer

Main formulas to memorize:

* For loss capping:  
$LEV(X; \Phi \sim Exp(\theta)) = \theta \: \left[ 1 - \operatorname{exp}\left\{-\left(\dfrac{x}{\theta}\right)\right\} \right]$

* For conversion:  
$\begin{align}
  F_{ij}^X = F_{nj}^B \times \frac{LEV(X;\Phi_{i\infty})\div LEV(B;\Phi_{n\infty})}{LEV(X;\Phi_{ij}) \div LEV(B;\Phi_{nj})}
 \end{align}$

We can do this for an XS layer as well

If we don’t have the severity distribution by age, we can work with the severity at ultimate

* $\begin{align}
  F_{ij}^X = F_{nj}^B \times \frac{LEV(X;\Phi_{i\infty})\div LEV(B;\Phi_{ {\color{red}i} \infty})}{R_j{(X,B)}}
 \end{align}$

### A6 Variability in CL Method

Measuring the Variability of Chain Ladder Reserve Estimate - T. Mack (1994)

Focus on cummulative losses

Chain ladder **assumptions**:

1) $\operatorname{E}\left [c_{i,k+1} \mid c_{i,1} \cdots c_{i,k}\right ] = c_{i,k} \: f_k$
    
2) $\left \{c_{i,1} \cdots c_{i,I} \right \} \: {\perp\!\!\!\perp} \: \left \{c_{j,1} \cdots c_{j,I} \right \}$ for $i \neq\ j$
    
3) $\operatorname{Var}\left (c_{i,k+1} \mid c_{i,1} \cdots c_{i,k}\right ) = \alpha_k^2 \: c_{i,k}$

LDF weight and **variance** assumptions:

$\begin{align}
  \hat{f_k} = \frac{\sum_j \overbrace{\frac{c_{j,k+1}}{c_{j,k}}}^{LDF_j} \: w_{j,k}}{\sum_j w_{j,k}}
  \end{align}$

| Weight $w_{j,k}$ | Description | Variance | Residual |
| ---------------- | ----------- | -------- | -------- |
| 1                | Simple Average | $\alpha_k^2 \times \mathbf{c_{j,k}^2}$ | $\varepsilon = \dfrac{c_{j,k+1} - c_{j,k} \: \hat{f_k}}{\sqrt{\mathbf{c_{j,k}^2}}}$ |
| $c_{j,k}$        | Weighted Average | $\alpha_k^2 \times \mathbf{c_{j,k}}$ | $\varepsilon = \dfrac{c_{j,k+1} - c_{j,k} \: \hat{f_k}}{\sqrt{\mathbf{c_{j,k}}}}$ |
| $c_{j,k}^2$      | Least Square | $\alpha_k^2 \times \mathbf{1}$ | $\varepsilon = \dfrac{c_{j,k+1} - c_{j,k} \: \hat{f_k}}{\sqrt{\mathbf{1}}}$ |

**Mean squared error**

$\begin{align}
  MSE(\hat{c}_{i,I}) = \hat{c}_{i,I}^2 \Bigg \{ \sum_{k = I + 1 - i}^{I-1} \frac{\hat{\alpha}_k^2}{\hat{f_k}^2} \Bigg ( \frac{1}{\hat{c}_{i,k}} + \underbrace{\frac{1}{\sum_{j=1}^{I-k}c_{j,k}}}_{\text{Column x latest}}\Bigg ) \Bigg \}
\end{align}$

$\begin{align}
  \hat{\alpha}_k^2 = \frac{1}{I - k - 1} \sum_{j=1}^{I-k} c_{j,k} \Big ( \underbrace{\frac{c_{j,k+1}}{c_{j,k}}-\hat{f_k}}_{\text{AY LDFs - Selected}} \Big )^2
\end{align}$

For the last one $\alpha^2_{I-1}$:

* If the 3rd last one is lower, take that
* Else, you take the 2nd last times the ratio of the 2nd last to 3rd last

**Confidence Interval**

Normal: $\hat{R}_i \pm Z_\alpha \: s.e.(\hat{R}_i)$

LogNormal: $R_i \operatorname{exp}\left \{ -\dfrac{\sigma_i^2}{2} \pm \: Z_\alpha \sigma_i \right \}$

* $\sigma_i^2 = \operatorname{ln} \left [ 1 + \left ( \dfrac{s.e.(\hat{R}_i)}{\hat{R}_i} \right)^2 \right]$
* $\mu_i = \operatorname{ln}(\hat{R}_i) - \dfrac{\sigma_i^2}{2}$

**Assumptions test**

* Intercepts plot
* Residuals plot
* [CY Test](#a6-1)
* [Correlation on adjacent LDFs](#a6-2)

### A7 ATA Assumptions Tests

Testing the Assumptions of Age-to-Age Factors - G. Venter

Standards used in this paper

* The $n$ for this paper excludes the first column

* Coefficient $> 2 \sigma$ is significant

[Error measures](#a7-1) used are Adjusted SSE, AIC and BIC

Testable implications from assumptions

1) Statistical significance of $f(d)$
2) Is there a better estimate for $q$ than $f \times c$

| $\mathbf{q(w,d)}$ | Parameters | Comments |
| ------ | ---------- | --- |
| $f(d) c(w,d) + g(d)$ | $2m - 2$ | e.g. Least Squares |
| Chainladder | $m - 1$ | | 
| $f(d)h(w)$ | $2m-2$ | e.g. BF |
| $f(d)h$ | $m-1$ | e.g. Cape Cod |

| Method | $\mathbf{\operatorname{Var}(q)}$ | $\mathbf{f(d)}$: Col Parameters | $\mathbf{h(w)}$: Row Parameters |
| ------------------ | ------------------ | ------------------ | ------------------ |
| BF (Constant Var, Least Square) | $a(d); p=q=0$ | $f(d) = \dfrac{\sum_w h^2 \frac{q}{h}}{\sum_w h^2}$ | $h(w) = \dfrac{\sum_d f^2 \frac{q}{f}}{\sum_d f^2}$ |
| Cape Cod | $a(d); p=q=0$ | $f(d) = \dfrac{\sum_w h^2 \frac{q}{h}}{\sum_w h^2}$ | $h = \dfrac{\sum_\Delta f^2 \frac{q}{f}}{\sum_\Delta f^2}$ |
| BF (Var $\propto$ $fh$)| $a(d) \cdot f \cdot h; p=q=1$ | $f^2(d) = \dfrac{\sum_w h (\frac{q}{h})^2}{\sum_w h}$ | $h^2(w) = \dfrac{\sum_d f (\frac{q}{f})^2}{\sum_d f}$ |

* Here we have to do the calculation recursively starting with either the row or column parameters

3) Check residuals against $c(w,d)$
4) Stability of $f(d)$ down the column
5) No [correlation](#a7-2) among columns
6) No particularly high or low diagonals

### A8 Curve-Fitting

LDF Curve-Fitting and Stochastic Reserving: A Maximum Likelihood Approach - D. Clark

$x =$ average age of AY

% paid to date growth function: $G(x \mid \omega, \theta)$

Loglogistic:  
$G(x \mid \omega, \theta) = \dfrac{x^{\omega}}{x^{\omega} + \theta^{\omega}}$

Weibull:  
$G(x \mid \omega, \theta) = 1- \operatorname{exp}\left\{ { - \left( \dfrac{x}{ \theta } \right)^{\omega}} \right \}$

Expected Ultimate Loss

* Method 1: Cape Cod  
$Premium_{AY} \times ELR$

* Method 2: LDF  
$ULT_{AY}$

Estimate Future Emergence

* Method 1: Cape Cod  
$[G(y \mid \omega, \theta) - G(x \mid \omega, \theta)] \times [Premium_{AY} \times ELR]$

* Method 2: LDF  
$[G(y \mid \omega, \theta) - G(x \mid \omega, \theta)] \times ULT_{AY}$

Truncation

* Method 1: Cape Cod  
Truncated @ age $x_t$  
Reserve = On-level Premium $\times ELR \times [(G(x_t) - G(x)]$

* Method 2: LDF  
Truncated @ age $x_t$  
$G'(x) = \dfrac{G(x)}{G(x_t)}$

Variance of reserve

* Process Variance of $R$:  
$\sigma^2 \sum_i \mu_i$

* Parameter Variance of $R$:  
$\operatorname{Var}(\operatorname{E}[R]) = (\partial R)'\Sigma (\partial R)$

$\dfrac{Variance}{Mean} = \sigma^2 = \dfrac{1}{n-p}\sum\limits_{i \in \Delta}^n\dfrac{(c_i - \mu_i)^2}{\mu_i}$

* $n =$ # of data points in triangle

* $p =$ # of parameters

    * Cape Cod $p=3$ ($\omega, \theta, ELR$)
    * LDF $p=2 +$ # of AYs ($\omega, \theta,$ row parameters)

* $c_i =$ actual incremental loss emergence

* $\mu_i =$ expected incremental loss emergence

### A9 Risk Margin

A Framework for Assessing Risk Margins - K. Marshall et al

Need framework because quantitative is not enough, need both quantitative and qualitative measures to examine the uncertainty

* Quantitative analysis requires lots of data

* Only captures historical risk

* Does not capture risk that did not have an episode (of systemic risk) in the experience period

**Independent**

Parameter and process variance model with stochastic model

**Internal Systemic**

Know the [3 components](#a9-2)

Score against best practice and calibrate to CoV

* Know how to score given actual examples as in past exam
* Hindsight analysis

**Extnernal Systemic**

Know the different [risk categories](#a9-3)

* And what lines they impact most

Use benchmark similar to internal but select CoV directly

**Correlation**

Risk sources are independent of each other

Independent: assume independence across lines, weight by liabilities

Internal: base on correlation matrix $\Sigma$, again weighted by liabilities

External: correlation between each valuation group and risk categories $\Rightarrow$ then roll up to the risk categories and assume they are independent of each other

**Risk Margin**

$\text{Risk Margin} = \underbrace{\mu}_{\text{Expected Loss}} \times \underbrace{\phi }_{\text{CoV}} \times \underbrace{Z_{\alpha}}_{0.67\text{ for the }75^{th}\text{ percentile}}$

Additional analysis

* Sensitivity, scenario testing

* [Internal benchmarking](#a9-1), important to know the relationships and consistency, been heavily tested in the past

* External benchmarking

* Hindsight and mechanical hindsight

Regularity of review

### A10 Bootstrap

Bootstrap Modeling: Beyond the Basics - Shapland Leong

Works with incremental triangles

$m_{wd} = \operatorname{exp} \left [\alpha_w + \sum_j \beta_j \right]$

$\operatorname{Var}[q(w,d)] = \phi m_{wd}^z$ with $z=1$ for ODP

* 3 methods for [dispersion](#a10-1) factor

First use either [GLM](#a10-4) or [simplified GLM](#a10-5) to get the mean and variance for each cell of the triangle and then do the [bootstrap](#a10-3) procedure

Practical Issues

* Negative incremental values (fit and simulate)
    * 3 potential methods for adjustment when doing model fit
    * Simulate with $Gamma(-m_{wd}, -\phi m_{wd}) + 2m_{wd}$
* Non-zero sum of residuals
* N-year wtd average
* Missing values
* Outliers
* Heteroskedasticity: [Hetero adjustment](#a10-2) 
* Partial latest year exposure or partial diagonal
* Expsoure adjustment
* Parametric bootstrap

Diagnostics

* Residual graph, normality test, outlier, parameter adj
* Review results: s.e. and CoV should make sense

Other

* Multiple models: 2 methods for simulation
* Model outputs
* Correlations: location mapping or re-sort

### A11 Expert Opinions

Obtaining Predictive Distributions for Reserves Which Incorporate Expert Opinions - R. Verrall

Works with incremental data

Model is defined with losses following ODP and stochastic row parameters that follows gamma as prior

Bayesian BF calculation and assumptions

* $\operatorname{E}[c_{ij}] = Z_{ij} \overbrace{[(\lambda_j - 1) \underbrace{D_{ij-1}}_{\text{Actual up to }j-1}]}^{\text{CL Results}} + (1- Z_{ij}) \overbrace{[(\lambda_j - 1) \underbrace{M_i p_{j-1}}_{\text{Expected up to }j-1}]}^{\text{BF Results}}$

* $Z_{ij} = \dfrac{p_{j-1}}{\beta_i \varphi + p_{j-1}}$

* $c_{ij} \sim ODP(x_i \cdot y_j, \varphi)$

* $x_i \sim \Gamma(\alpha_i, \beta_i)$

* $\operatorname{E}[x_i] = \dfrac{\alpha_i}{\beta_i} = M_i$
    
* $\operatorname{Var}[x_i] = \dfrac{\alpha_i}{\beta_i^2}$

Stochastic column parameters calculation

* $\operatorname{E}[c_{ij}] = (\gamma_i - 1) \sum \limits_{m=1}^{i-1} c_{m,j}$

* [Calculate](#a11-1) $\gamma$ pictorially

Using vauge or strong priors for model specification

### A12 Reinsurance Reserving

Reinsurance Loss Reserving - Patrik

Problems of reinsurance reserving:

1. Longer report lag of claims
2. Persistent Upward Development of Most Claim Reserves
3. Reporting Pattern Differ Greatly
4. Industry Statistics Not Useful
5. Reports Received Lack Important Information
6. Data Coding and IT System Problems
7. Reserve to Surplus Ratio is Higher for Reinsurer

6 Components of reinsurance reserve

1. Case reserve reported by cedent
2. Additional case reserve from reinsurer
3. IBNER
4. Pure IBNR
5. Discount for future investment income
6. Risk Load

Reinsurance reservering procedure:

* Partition $\Rightarrow$ Development Patterns $\Rightarrow$ Estimate $\Rightarrow$ Monitor and AvE

* Partition priority

* Considerations for short vs medium vs long tail lines

* AvE

Stanard Buhlmann

* Must on-level the historical premium and adjust to be pure premium

    * Remove commissions and brokerage and internal expenses (but might not worth the effort)

    * Remove any suspected rate level differences

* $ELR = \dfrac{\sum C_k}{\sum E_k p_k}$

    * $C_k$: reported to date; $E_k$: Adj Prem; $p_k$: expected % reported to date

* Estimate ELR using actual incurred loss

* Sensitive to the accurary of the onlevel EP
    
Credibility IBNR Estimates

* Weight the CL method with SB or BF

* $R_k = Z \cdot R_{CL} + (1-Z) \cdot R_{SB}$

* $Z_k = p_k \cdot CF$, $CF \in [0,1]$

* $CF$ is the credibility factor, Benktander = 1, BF = 0\

### A13 Premium Asset

Estimating the Premium Asset on Retrospectively Rate Policies - M. Teng and M. Perkins

Retro formula

$\underbrace{P}_{\text{Premium}} = [\underbrace{BP}_{\text{Basic Premium}} + (\underbrace{CL}_{\text{Capped Losses}} \cdot \underbrace{LCF}_{\text{Loss Conversion Factor}})] \cdot \underbrace{TM}_{\text{Tax Multiplier}}$

Use PDLD to get the premium development based on the loss developement

Know what each term means like basic premium factor or charge

Formula approach for PDLD

$\begin{align}
  PDLD_1 =\underbrace{\left(\frac{BP}{SP} \right)}_{\text{Basic Prem Factor}} \frac{TM}{ELR \cdot \%Loss_1} + \underbrace{\left( \frac{CL_1}{L_1}\right)}_{\text{Loss Capping Ratio}} \cdot LCF \cdot TM
\end{align}$

* To adjust for being too responsive: $\begin{align}
  P_1 = \underbrace{\left( \frac{BP}{SP} \right) \frac{TM}{ELR \cdot \%Loss_1}}_{\text{Not }\propto\text{ Loss}_1} \times \operatorname{E}[L_1] + \underbrace{\left( \frac{CL_1}{L_1} \right) \cdot LCF \cdot TM}_{\propto \text{ Loss}_1} \times L_1
\end{align}$

* Subsequent PDLD: $\begin{array}{cccl}
  PDLD_n &= &\dfrac{CL_n - CL_{n-1}}{L_n - L_{n-1}}&LCF \cdot TM \:\:\:\:\text{For }n>1\\
  &= &\dfrac{\Delta CL}{\Delta L}&LCF \cdot TM\\
\end{array}$

Empirical approach for PDLD

* Assume premium lags
* Ratio selection
* Cumulate PDLD based on a weighted average with expected % future report for each future periods
* Know the practical application
    * First adjustment period might cover more than one policy period

Know the Teng Perkins improvements and assumptions

### A14 Bayesian MCMC

Stochastic Loss Reserving Using Bayesian MCMC Models - G. Meyer

Know how they selected the underlying data set to avoid insurer with change in operations or ones that best suit the model

The 3 main test used through out:

1. [KS test](#a14-1)
2. [p-p plot](#a14-2)
3. [Freq vs percentile](#a14-3)

![](figures/Exam-7-Notes-9.png)

LCL:  
$e^{\mu_{wd}} = e^{\alpha_w}e^{\beta_d}$

* Same variance parameter ($\sigma_d$) for each column of *cumulative* loss

CCL:  
$\mu_{wd} = \alpha_w + \beta_p + \rho \cdot \left[ \operatorname{ln}\left(C_{w-1, d}\right) - \mu_{w-1,d} \right]$

CSR:  
$\mu_{wd} = \alpha_w + \left[ \beta_d \cdot (1-\gamma)^{w-1}\right]$

* $\gamma >0$ reflects increase in payment speed as $(1-\gamma)^{w-1} < 1$
* $\gamma$ has less impact further out in the tail as there are less payments happening out there

CIT:

1) Uncorrelated log mean of each cell with CY trend  
$\mu_{wd} = \alpha_w + \beta_d + \tau \cdot(w+d-1)$

2) Draw $Z_{wd} \sim Lognormal(\mu_{wd},\sigma_d)$

    * $\sigma_1 > \sigma_2 > \cdots > \sigma_{10}$
    
    * Smaller less volatile claims should be settled early

3) $\tilde{I}_{wd} \sim Normal(Z_{wd},\delta)$

4) Add correlation between AYs for rows after the first  
$\tilde{I}_{wd} \sim Normal(Z_{wd} + \rho \cdot (\tilde{I}_{w-1,d} - Z_{w-1,d})\cdot e^{\tau},\delta)$

LIT: same as CIT but with $\rho = 0$

[Skewed](#a14-4) distributions

## Section B

### B1 Valuation Methods

B1 P&C Insurance Company Valuation - R. Goldfarb

The key methods are DDM, FCFE, and AE

* $V_0 = \dfrac{\mathrm{E}[Div_1]}{k - g}$
* $FCFE = NI + (Non \:Cash\:Charges) - \Delta Working \:Capital - \Delta Capital + \Delta Debt$
* $\begin{align} V_0 = BV_0 + \sum_{t=1} \frac{(ROE_t - k)BV_{t-1}}{(1+k)^t}\end{align}$

You can also look the P:Earning or P:Book multipes which have formulas that's based on the DDM and AE method

* Watch out for some nuance on forward and trailing P:Earning

Another important bit is to determine the growth rate, if it's not given in a questions then you have to calculate $g$ over a couple years and select

## Section C

## Formula Appendix

<a name="a6-1"></a> **Calendar Year Test**

Step 1) Rank the LDFs in each column

Step 2) Label them S and L and the median is discarded

Step 3) For each diagonal with at least 2 elements, $z = \operatorname{min}(\text{# of S}, \text{# of L})$

Step 4) Calculate $\operatorname{E}[z_n]$ and $\operatorname{Var}(z_n)$

* $\operatorname{E}[z_n] = \dfrac{n}{2} - c_n$

    * $n =$ # of elements in each diagonal **excluding** the throw away value
    
    * $c_n = {n - 1 \choose m}\frac{n}{2^n}$
    
    * $m = \operatorname{floor}\left[ \dfrac{n-1}{2} \right]$

* $\operatorname{Var}(z_n) = \dfrac{n(n-1)}{4} - c_n (n-1) + \operatorname{E}[Z_n] - \operatorname{E}[z_n]^2$

* $z \sim$ Normal

Step 5) See if $Z$ is in the CI based on the the above

* $Z = \sum_{diagonal} z$

* Since $Z \sim$ Normal, can sum the mean and variance by assuming independence

* Test 95% CI: $\operatorname{E}[Z] \pm 2 \times \sigma$

***

<a name="a6-2"></a> **Correlation of Adjacent LDFs**

Use a relatively low threshold of 50%

Step 1) Calculate Spearman's correlation for each pair of adjacent LDFs

* $S = \sum \limits_{\in rows} \Big \{ [Rank \: Col \: i \: LDF] - [Rank \: Col \: j \: LDF] \Big \}^2$

* Rank from low to high (i.e. lowest is 1)

* $T_k = 1 - \dfrac{S}{n(n^2-1)/6}$

    * $n =$ # of rows
    
    * For a 10 x 10 triangle, $k$ is at most 7 because there's only 9 LDFs so 8 pairs. And down to 7 because we don't use the pair with only 1 row
    
Step 2) Calculate $T$ for the whole triangle

* $T = \dfrac{\sum T_k (n_k - 1)}{\sum (n_k-1)} = \dfrac{\sum_k (I - k -1)T_k}{\sum_k I - k -1}$

    * $I =$ size of triangle
    
    * $k$ starts at 2
    
    * Formula gives more weight to $T_k$ with more data
    
    * Weight goes down to 1 for the last one, the bottom is just the sum of all the weights
    
Step 3) Compare $T$ with CI based on distribution

* $\operatorname{E}[T] = 0$

* $\operatorname{Var}[T] = \dfrac{1}{(I-2)(I-3)/2}$

* $\operatorname{E}[T] \pm Z \sqrt{\operatorname{Var}(T)}$

* Use $Z = 0.67$ for range of [25%, 75%]

* Do not reject the $H_0$ of uncorrelated LDFs if the $T$ is in the CI

***

<a name="a7-1"></a> **Error Measures**

Adjusted SSE = $\dfrac{SSE}{(n-p^2)}$

$AIC \approx SSE \times e^{2p/n}$

$BIC \approx SSE \times n^{p/n}$

* $n =$ # of predicted data points **EXCLUDING 1st column**

* $p =$ # of parameters

* $SSE = \sum (A - E)^2$

    * Here you exclude the first column when calculating the difference
    
***

<a name="a7-2"></a> **Pearson Correlation**

Correlation $r = \dfrac{\sum \tilde{x} \tilde{y}}{\sqrt{\sum \tilde{x}^2\sum \tilde{y}^2}}$

* $\tilde{x} = x - \bar{x}$

* $\tilde{y} = y - \bar{y}$

For the adjacent LDFs, we need to subtract 1 out first

Test statistics: $T = r \sqrt{ \dfrac{n-2}{1-r^2} }$

* $T \sim t_{n-2}$

* Look up the t-value from table for 90%

* If the absolute value of $T <$ table value $\Rightarrow$ Not correlated

***

<a name="a10-1"></a> **Dispersion Factor**

Pearson residual:  
$\begin{array}{cccl}
  r_{wd} & = & \dfrac{A - E}{\sqrt{\operatorname{Var}(A)}} & \\
  & = & \dfrac{q(w,d) - m_{wd}}{\sqrt{\phi m_{wd}}} & \text{Mean & Var Assumptions Above}\\
  & \propto & \dfrac{q(w,d) - m_{wd}}{\sqrt{m_{wd}}} & \text{Since }\phi \text{ is constant for all}\\
\end{array}$

Standard:  
$\phi = \dfrac{\sum r_{wd}^2}{n-p}$

* $n =$ # of data points (including first column)

* $p =$ # of parameters

    * $2m-1$: one for each row, one for each column minus first column

England & Verrall:  
$\phi^{EV} = \dfrac{\sum \left(r^{EV}_{wd}\right)^2}{n-p}$

* $\begin{array}{llllc}
    r_{wd}^{EV} & = & r_{wd} &\times &f \\
    & = & r_{wd} &\times &\sqrt{\dfrac{n}{n-p}}\\
  \end{array}$

Standarized Residuals:  
$\phi^H = \dfrac{\sum \left(r_{wd}^H \right)^2}{n}$

* $\begin{array}{lllc}
    r_{wd}^H &= r_{wd} &\times &f_{wd}^H \\
    &= r_{wd} &\times &\sqrt{\dfrac{1}{1-H_{ii}}} \\
  \end{array}$

* $H_{ii}$ is the diagonal of the Hat Matrix Adjustment Factor: $H = X (X^TWX)^{-1}X^TW$

    * The diagonal is labelled by going down the column of the triangle from left to right
    
    * The denominator might actually be $n-2$ but for the purpose of exam just use $n$ as stated in the paper

***

<a name="a10-2"></a> **Hetero-Adjustment**

Group the residuals then calculate the $\sigma$ of the residuals in each group and scale up

Hetero-adjustment factor: $h^i$ = the largest $\sigma$ $\div$ each group's $\sigma$

$r_{wd}^{i,H} = r_{wd} \times f_{wd}^H \times h^i$

* Residual $\times$ Hat Matrix Factor $\times$ Hetero Factor

Need to divide the sampled residual by $h^i$ to reflect the variability of group $i$

* $q^{i*}(w,d) = m_{wd} + \dfrac{r^{i*}}{h^i}\sqrt{m_{wd}}$

***

<a name="a10-3"></a> **Bootstrap Procedure**

Once we have the mean and residuals in each cell, repeat below:

1) Create a sampled $triangle^*$ from the residuals and the means

    * Sample from residuals since data needs to be $iid$ for bootstrap
    
    * Use pearson residuals
    
    * Simulated loss: $q^*(w,d) = m_{wd} + r_p \sqrt{m_{wd}^z}$
    
        * Simulate by sampling residuals with replacement
    
    * Estimate $\phi$ for step 4: $\phi = \dfrac{\sum r^2}{n-p}$
        
2) Determine parameters from $triangle^*$: $(\alpha_i, \beta_j)$

    * Use either GLM or Simplified GLM to project ultimate loss

3) Calculate mean and variance: $(m_{wd}, \phi m_{wd})$

    * For GLM use $m_{wd} = \operatorname{exp} \left [\alpha_w + \sum_j \beta_j \right]$
    
    * For Simplified GLm, back out the $c^*(w,d)$ by $\dfrac{Ult_w}{CDF_d}$ then get the $m_{wd}$
    
    * For variance $\phi m_{wd}^z$

4) Add process variance: draw losses from $Gamma(m_{wd}^*,\phi m_{wd}^*)$

    * Randomly draw from the distribution for each cell

5) Calculate simulated unpaid: sum of bottom half of triangle

***

<a name="a10-4"></a> **GLM**

For a $3\times 3$ triangle:

Log Actual incremental losses

$Y = \begin{bmatrix}
    ln[q(1,1)] \\
    ln[q(2,1)] \\
    ln[q(3,1)] \\
    ln[q(1,2)] \\
    ln[q(2,2)] \\
    ln[q(1,3)] \\
\end{bmatrix}$

Solution Matrix $W$

$\begin{array}{ccccc}
  W & = & X &\times & A \\
  & & \alpha_1 \:\:\: \alpha_2 \:\:\: \alpha_3 \:\:\: \beta_2 \:\:\: \beta_3 & &\\
  \begin{bmatrix}
    ln[m_{11}] \\
    ln[m_{21}] \\
    ln[m_{31}] \\
    ln[m_{12}] \\
    ln[m_{22}] \\
    ln[m_{13}] \\
  \end{bmatrix}
    & =
      &
      \begin{bmatrix}
        1 & - & - & - & - \\
        - & 1 & - & - & - \\
        - & - & 1 & - & - \\
        1 & - & - & 1 & - \\
        - & 1 & - & 1 & - \\
        1 & - & - & 1 & 1 \\
      \end{bmatrix}
        & \times
          &
          \begin{bmatrix}
            \alpha_1 \\
            \alpha_2 \\
            \alpha_3 \\
            \beta_2 \\
            \beta_3 \\
          \end{bmatrix}
\end{array}$

* $W =$ Solution Matrix

* $X =$ Design Matrix

    * Defines the parameters used to estimate the losses

* $A =$ parameters

    * Solve for $A$ by minimizing the difference^2^ (SSE) between $W$ and $Y$
    
    * Use recursive Newton-Raphson method to find the best fit parameters
    
***

<a name="a10-5"></a> **Simplified GLM**

GLM model = Chainladder w/ volume-weighted averages when:

* Variance $\propto$ Mean
* $\varepsilon \sim$ Poisson; Poisson error
* Parameter for each row and column (x 1^st^ column)

***

<a name="a14-1"></a> **KS Test**

$H_0$: Distribution of $p_i$ is uniform

$D = \operatorname{max} \limits_i \mid p_i - e_i \mid$

* Maximum difference between the predicted and expected percentiles

Reject $H_0$ if $D > \dfrac{136}{\sqrt{n}}\%$ @5% confidence level

* e.g. for $n = 50$: 19.2%; $n=200$: 9.6%

***

<a name="a14-2"></a> **p-p plot**

![](figures/Exam-7-Notes-10.png)

* Model is too light tailed: Shallow slope near corner and steep in the middle
* Model is too heavy tailed: Steep slope near corner and shallow in the middle
* Model is biased upwards: Bow down

***

<a name="a14-3"></a> **Freq Percentile Plot**

![](figures/Exam-7-Notes-12.png)

* Blue line is based on the uniform $e_i$ set at $\frac{n}{10}$ for the 10 deciles

***

<a name="a14-4"></a> **Skewed Normal**

Skewed Normal:  
$X = \mu + (\omega \cdot Z) \cdot \delta + (\omega \cdot \varepsilon) \cdot \sqrt{1 - \delta^2}$

* $\varepsilon \sim Normal(0,1)$

* $Z \sim Truncated \: Normal_{[0,\infty]} (0,1)$

* $\delta$ is the weight between $\varepsilon$ and $Z$

* $\omega$ is the standard deviation

Mixed Lognormal-Normal:  
$X \sim Normal(Z,\delta)$

* $Z \sim Lognormal(\mu,\sigma)$

* Mixed $ln - n$ Distribution

***

<a name="a5-1"></a> **Base Triangle**

Step 1:  
Setup the trend triangle: Trend = AY Trend $\times$ CY Trend

* The 1.000 typically starts at the top left corner but it doesn't have to

Step 2:  
Determine *unlimited* mean for each cell in triangle (Avg sev paid to date)

i) Based on mean for the latest AY (bottom row)

    * $\operatorname{E}[C_{nj}] = \theta_j$

    * $C_{nj} \sim \Phi_{nj} = Exp(\theta_j)$
    
ii) Detrend back up from the bottom row to fill the whole square

    * Usually just need four points per the LDF conversion formula

Step 3:  
Calculate LEV for each cell in triangle $L$ and the last row for $B$

* $LEV(X; \Phi \sim Exp(\theta)) = \theta \: \left[ 1 - \operatorname{exp}\left\{-\left(\dfrac{x}{\theta}\right)\right\} \right]$

* Use the "square" of mean $\theta$ calculated from Step 2

Step 4:  
Calculate the adjusted triangle

* Convert triangle of actual losses by dividing it's LEV at layer $L$ then times it's LEV at layer $B$

* $C_{ij}' = \underbrace{C_{ij}^L}_{\text{Cum paid @ L}} \times \underbrace{\dfrac{LEV(B;\Phi_{nj})}{LEV(L;\Phi_{ij})}}_{\text{ILF w/ on-level to }n}$

Step 5:  
Select base layer LDFs

***

<a name="a5-2"></a> **Convert LDFs**

$\begin{align}
  F_{ij}^X = F_{nj}^B \times \frac{LEV(X;\Phi_{i\infty})\div LEV(B;\Phi_{n\infty})}{LEV(X;\Phi_{ij}) \div LEV(B;\Phi_{nj})}
 \end{align}$

![](figures/Exam-7-Notes-13.png)

***

<a name="a11-1"></a> **$\gamma$ Calculation**

$\gamma_1 = 1.000$ always

First calculate LDFs and calculate % unpaid and a-priori for each AY

* $U_i$ = a-priori ultimate based on LDF for AY $i$

* $q_i$ = % unpaid for AY $i$

![](figures/Exam-7-Notes-3.png)

Note that in step 4 above if you don't need the individual cells you can just take the $U_3 q_3$

***

<a name="a9-1"></a> **Internal Benchmarking**: Compare CoVs within between OCL and PL and also with other valuation groups

*Independent risk*: 

* Large liability will have smaller CoV due to law of large numbers
    
* Short tail line will have a small CoV as well due to less volatility
    
Therefore:    
    
* Outstanding Claims Liability: $\phi_{short \: tail} < \phi_{long \: tail} < \phi_{long \: tail, \: small \: book}$

* Premium Liability - Long Tail: OCL > PL $\Rightarrow$ $\phi_{OCL} < \phi_{PL}$

    * Because there are many AYs of claims in the reserves
    
* Premium Liability - Short Tail: OCL < PL $\Rightarrow$ $\phi_{OCL} > \phi_{PL}$

    * Because OCL is small
    
    * LoB with significant event risk will have different risk profiles for the PL and OCL
    
*Internal Systemic*: 

* If the methods to estimate liabilities is similar across valuation groups, we would expect the CoV to be similar for classes that have similar claim payment patterns

*External Systemic*:

* Main sources are higher for long tail lines; Event risk is higher for property; Liability for HO can also be significant

***

<a name="a9-2"></a> 3 components of **internal systemic** risk:

1) Specification Error:  
From not perfectly modeling the insurance process because it's too complicated or just don't have the data

2) Parameter Selection Error:  
Trend is particularly difficult to measure

3) Data Error:  
Lack of data, lack of knowledge of the underlying pricing, u/w, and claim management process, inadequate knowledge of portfolio

***

<a name="a9-3"></a>

**Risk categories** for external

* Economic and Social Risks:  
Inflation, social trends 

* Legislative, Political Risks, Claims Inflation Risks:  
Change in law, frequency of settlement vs suits to completion, loss trend (Long tail lines)

* Claim Management Process Change Risk:  
Change in process of managing claims e.g. case reserve practice

* Expense Risk:  
Cost of managing a run-off book

* Event Risk:  
natural or man-made CAT (Premium liabilities for property)

* Latent Claim Risk:  
Claim from source not currently considered to be covered

* Recovery Risk:  
Recoveries from reinsurers or non-reinsurers