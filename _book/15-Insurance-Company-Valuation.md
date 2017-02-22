# (PART) Insurance Company Valuation {-}

# B1 P&C Insurance Company Valuation - R. Goldfarb

## Cliff's Summary

Know how to get the discount rate and [growth rate](#growth-rate) for each of the 3 method

DDM:

* $V_0 = \dfrac{\mathrm{E}[Div_1]}{k - g}$

* Knows how this can transform to the P:E formula

* Remembers the terminal value formula uses CF at 1 but get you to time 0

FCFE:

* $FCFE = NI + (Non \:Cash\:Charges) - \Delta Working \:Capital - \Delta Capital + \Delta Debt$

* Discount all the FCFE for $V_0$
    
* [Advantages](#fcfe-adv)

* [FCFE vs FCFF](#FCFE-v-FCFF)

AE:

* $\begin{align} V_0 = BV_0 + \sum_{t=1} \frac{\overbrace{(ROE_t - k)BV_{t-1}}^{AE_t}}{(1+k)^t}\end{align}$

* Remember to add the $BV_0$

* [Advantages](#ae-adv)

* [Considerations](#ae-considerations)

Relative multiples:

* $\dfrac{P_0}{E_1} = \dfrac{1 - \rho}{k - \rho \times ROE}$; Based on DDM

* $\dfrac{P_0}{BV_0} = 1 + \dfrac{ROE - k}{k - g}$; Based on AE

### Types of Exam Questions

<span style="color:red">Haven't done TIA practice questions</span>

**Concepts**

* $\star$ 2011 - #12 a: higher $g$ should be matched with higher $\beta$ for being more risky
* 2011 - #12 c: relationship between $g$ and $k$
* 2015 #17 b-c: $\beta$ discussion

**DDM**

* [2008 #43](#2008-43): DDM calc and convert to P:E
* $\star$ 2008 #44: DDM calc and interpretation
* 2008 #45: Comparison on P:E
* 2009 #34
* 2011 - #12 b: DDM calc (Get $r_f$ as t-bond less liquidity premium)
* $\star$ [2012 #12](#2012-12): Full calc with DDM
* 2014 #16: DDM calc
* 2015 #17 a: DDM calc 

**FCFE**

* $\star$ [2009 #35](#2009-35): Full FCFE calc
* $\star$ [2013 #11](#2013-11): Full FCFE calc with discussion
    * [FCFE vs FCFF](#FCFE-v-FCFF)
* 2014 #17: FCFE Calc; <span style="color:red">Not sure bout the reserve increase impact on required capital</span>
* $\star$ 2015 #16: Discussion on DCF

**AE**

* $\star$ [2010 #31](#2010-31): Full AE calc
* [2011 - #13](#2011-13): Price to Book value calc + discussion on assumption
* 2013 #12: Full AE Calc + discussion
* 2015 #15: AE Calc + discussion

**Relative Valuation**

* $\star$ 2014 #15: Price to Book calc using all the ratios given by LoB

## Assumptions

Key assumptions are **cost of captial** $k$ and **growth rate** $g$

### Risk Adjusted Discount Rate

Recognize the risky cashflow by discounting them at a rate higher than the risk-free rate based on CAPM

$k = r_f + \beta \left [ \mathrm{E}(r_m) - r_f \right ]$


* Risk of an investment depends on the rest of an investor's portfolio. We focus instead on equilibrium rates of return

* Different BU has different risk profile $\Rightarrow$ Different discount rates

* Discount rates can vary by period if business mix change

* Not all cash flow have the same risk profile (premium, investment income, paid losses)

* Simplification is to use average discount rate for the portfolio

One alternative way to account for the risky cash flow is to convert the cash flow to *certainty equivalent cash flows* and discount with risk free instead of the cost of capital

* Reflect the risk in the cashflow directly

**Risk free Rate: $r_f$**

* 90 days t-bill
* Maturity matched t-notes
* T-bonds less liquidity & term premium (~1.2%)

**Market Risk Premium: $\mathrm{E}(r_m) - r_f$**

* 6-8% historically

* $r_f$ here should be consistent

* Need to sensitivity test

**Systematic Market Risk: $\beta$**

* Based on regression on stock return vs market return

* Can use industry $\beta$

    * Mix of business needs to be similar to industry
    
    * Industry $\beta$ should be adjusted for differences in the industry leverage and company leverage

* $\beta$ will be higher for firms with more leverage, riskier business units

    * Alternative is to use *all equity* $\beta$ to remove bias from leverage
    
    * Higher growth should have higher $\beta$

* Insurance company has additional leverage from policyholder liabilities

* Can assume total leverage of insurance companies is similar

### Growth Rate

Used for the period after the forecast horizon

<a name="growth-rate"></a>

| Method | Growth Rate: $g$  |
| ------ | ----------------- |
| DDM    | $ROE \times \rho$ |
| FCFE   | $ROE \times$ [Reinvestment Rate] |
| AE     | At most the growth in book value |

**Return on Equity: $ROE$**

$\dfrac{NI}{BE} = \dfrac{\text{Net Income after Tax}}{\text{Beginning Equity}}$

**Plowback Ratio: $\rho$**

% of $NI$ that is reinvested in the firm

* Company that have high growth should retain more earnings

**Reinvestment Rate**

$\dfrac{\Delta Capital}{NI}$

## Dividend Discount Model (DDM)

$V_0 = \dfrac{\mathrm{E}[Div_1]}{k - g}$

* $Div_1$ is paid at the end of year 1

* Constant growth assumption

* $\mathrm{E}[Div_1] = (1 - \rho) NI$

Typically forecast a few years and use the above formula for the terminal value

Need to use $NI$ after tax

When calculating $g$, calculate $ROE$ and $g$ for all years and make selection

Firm with high expected growth tend to be riskier $\Rightarrow$ Higher discount rate

* Forecast is more susceptible to being wrong, so should be discount more?

**DDM Assumptions**

* Expected dividends
* Dividend growth rate
* Risk-adjusted discount rate (From CAPM)

## Free Cash Flow to Equity (FCFE)

Free cash flow available to pay shareholders:  
$FCFE = NI + (Non \:Cash\:Charges) - \Delta Working \:Capital - \Delta Capital + \Delta Debt$ <span style="color:red;background-color:yellow">Memorize Formula</span>

* $\Delta$ loss reserve reflected in $NI$ only; it gets netted out as non-cash charges and capital expenditures

* $NI$ is net of interest payments to shareholders, after tax

* $g = ROE \times$ [Reinvestment Rate] $= ROE \times \dfrac{\Delta Capital}{NI}$

    * Assume portion of FCF not paid out is invested at $k$

**Free Cash Flow**

* Cash flow available to pay out to the firm's source of capital (for FCFE this is only to equity) net of amounts required to be reinvested to the firm for growth

* Weakness: require forecasting financial statements, use adjusted accounting measure, large terminal value

Similar to DDM, calculate the $ROE$ and reinvestment rate for all years and make a pick

<a name="FCFE-v-FCFF"></a>**FCFE vs FCFF**

* We don't use the free cash flow to **firm** because there's additional leverage for p/h liabilities from reserves held
* Not clear how to calculate cost of capital due to leverage from 2 different source and it complicates the calculation
* Using FCFE removes the source of leverage

<a name="fcfe-adv"></a>**Advantages over DDM**

* Dividend are discretionary
* Firms also return funds via stock buybacks
* Focus on free cash flow

## Abnormal Earnings (AE)

Works with **accounting measures** of income

* Need to remove distortions

* More accurate some say

Clean surplus assumption

* Requires all changes to book value (on the b/s) flow through the I/S

* Flow through as earnings, dividends or capital contributions

$V_0 = BV_0 + \begin{align}\sum_{t=1} \frac{AE_t}{(1+k)^t}\end{align}$

$AE_t = NI_t - k \cdot BV_{t-1} = (ROE_t - k)BV_{t-1}$ <span style="color:red;background-color:yellow">Important Formula</span>

* Earnings (net income) XS of cost of capital

* Assume AE will trend to zero overtime since it's difficult to maintain

* AE is difficult to maintain as competitors will see the AE and move into the market

<a name="ae-considerations"></a>**Parameters Considerations**

$BV_0$

* Reported book value

* Focus on **tangible book value** (e.g. take out goodwill)

* Remove any systematic bias such as over or understated reserve

$NI$ is **net of interest payments** to shareholders, **after tax**; Same as DCF model

* Make complement of the book value adjustments here  
e.g. any direct adjustment to the B/S that doesn't flow from the I/S you have to adjust here

* If reserve is discounted in the $BV_0$, need to change (lower) the $ROE$ as the income will be generated from a larger capital base

$g$

* Should be negative as AE tend to 0

* Does not require additional capital as the growth from that extra capital will not accrue to today's shareholders

<a name="ae-adv"></a>**Advantages**

* Focus on value creation

    * Earnings above the required return on capital
    
    * Dividends and CF are just consequence of value creation

* Small terminal value as it focus on any added value so less leverage

* Directly using accounting measures so does not need to adjust into a cash flow measure

## Relative Multiples {.tabset}

We don't compare to sales because of leverage from p/h's liability

Stock price can fluctuate so use an average price

Multiples can vary significantly even over short periods of time

**Assumptions**

Constant $ROE$, $\rho$, and $k$

### Price to Earnings

Based on DDM

$\dfrac{P_0}{E_1} = \dfrac{1 - \rho}{k - \underbrace{\rho \times ROE}_{g}}$ <span style="color:red;background-color:yellow">Memorize Formula</span>

* If $ROE > k$ $\Rightarrow$ Keep a high $\rho$

P:E Ratio

* Forward or leading P/E = consensus forecast earnings for next year

* Trailing P/E = last year's actual; Can be distorted by unusual events

* Price = value of the firm derived from any of the methods

* Earnings = $NI$; Either forward or trailing

* By default, apply the ratio to next year's earnings per formula

Alternative use of P/E

* **Validating assumptions**: reasonability check on the forecast

* **Shortcut to valuation**: if you think company will grow similar to the industry

* **Terminal value**: use the other method for the forecast horizon then P/E for the terminal value

### Price to Book

Based on AE method

$\dfrac{P_0}{BV_0} = 1 + \dfrac{ROE - k}{k - g}$ <span style="color:red;background-color:yellow">Memorize Formula</span>

* $BV_0 =$ equity @ t = 0

* Useful for firms with substantial holdings in marketable securities

### Transaction Multiples

Can use multiples from transaction, however caveat:

* Companies tend to overpay

    * Control premium, and other reason M&A overpay

* IPO's are under priced

* Financials used to value the transaction could be different from the information being used now (forecast is different)

* Economic conditions @ transaction $\neq$ economic conditions now

### Relative Valuation for Multi-line firms

Use multiples from pure play peers (monoline firms) to estimate by division

Or compare multiples from diversified insurers

* Choose firms with similar business, $ROE$, claims paying rating, $\beta$

## Past Exam Questions

<a name="2008-43"></a>2008 #43
![](questions/2008-43Q.png)
![](questions/2008-43A.png)

<a name="2009-35"></a>2009 #35
![](questions/2009-35Q.png)
![](questions/2009-35A.1.png)
![](questions/2009-35A.2.png)

<a name="2010-31"></a>2010 #31
![](questions/2010-31Q.png)
![](questions/2010-31A.png)

<a name="2011-13"></a>2011 #13
![](questions/2011-13Q.png)
![](questions/2011-13A.png)

<a name="2012-12"></a>2012 #12
![](questions/2012-12Q.png)
![](questions/2012-12A.png)

<a name="2013-11"></a>2013 #11
![](questions/2013-11Q.png)
![](questions/2013-11A.png)