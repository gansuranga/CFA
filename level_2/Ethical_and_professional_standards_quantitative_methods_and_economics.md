
Ethical and professional standards quantitative methods and economics

----

# Ethical and Professional Standards

**The standard of professional conduct**
1. Professionalism

    + knowledge of the law: comply with the more strict law
    + independence and objectivity: must not offer, solicit or accept any gift, benefit and so on
    + misrepresentation(曲解误报): must not knowingly make any misrepresentations
    + misconduct: must not engage in any ptofessional conduct involving dishonesty...

2. Integrity(正直) of capital markets

    + material nonpublic information: must not act or cause others to act on the information
    + market manipulation

3. Duties to Clients

    + loyalty, prudence(审慎) and care: must act for the benefit of their clients and place their clients' interests before their employer's or their own interests
    + fair dealing
    + suitability
        - make a reasonabel inquiry prior to making any investment recommendation
        - determine that an investment is consistent with the clients' written objectives and constraints
        - judge the suitability of investments in the context of the client's total portfolio
    + preformance presentation
    + preservation of confidentiality: **MUST** keep information abount current, former and prospective clients confidential **unless**:
        - the information concerns illegal activities
        - disclosure is required by law, or
        - the client permits disclosure of the information

4. Duties to Employers

    + loyalty: in matters related to employment, must act for the benefit of their employer and not cause harm to them
    + additional compensation arrangements: must not accept benefits with or might reasonabley be expected to create a conflict of interest with emloyer's unless obtain written consent from all parties involved.
    + responsibilities of supervisors

5. Investment analysis, recommendations, and actions

    + diligence and reasonable basis
    + communication with clients and prospective clients
        - must disclose format and principles and promptly disclose any changes
        - disclose significant limitations and risks
        - identify important factors to their investment and include factors in communication with clients and prospective clients
        - distinguish between fact and opinion
    + record retention

6. Conflicts of interest

    + disclosure of conflicts: make sure the disclosure are prominent, are delivered in plain language
    + priority of transactions
    + referral fees(介绍费): must disclose to emloyers, clients and prospective clients any compensation received by, or paid to, others for the recommendation of products or service

7. Responsibilities as a CFA Institute Menber or CFA Candidate

    + conduct as participants in CFA Institute Programs: must not engage in any conduct that compromises the reputation of CFA
    + reference to CFA: must not misrepresent or exaggerate the meaning

# Ethical and Professional Standards: Application
# Quantitative Methods for Valuation

`significance level` like 5%

`confidence level` like 95%, i.e. (1 - significance level)
## correlation and regression
`sample covariance`
$$cov_{XY} = \frac{\sum_{i=1}^n(X_i-\bar{X})(Y_i-\bar{Y})}{n - 1}$$

`sample correlation coefficient`
$$r_{XY} = \frac{cov_{XY}}{(s_X)(s_Y)}$$

| correlation coefficient | Interpretation               |
| ----------------------- | ---------------------------- |
| $r= +1$                 | perfect positive correlation |
| $0 < r < +1$            | positive linear relationship |
| $r = 0$                 | no linear relationship       |
| $-1 < r < 0$            | negative linear relationship |
| $r= -1$                 | perfect negative correlation |

### test of hypothesis

To test whether the correlation between the population of two variable is equal to zero
$$H_0: \rho = 0 \ versus\ H_a:\rho \ne 0$$

we can use a t-test to determine wether the null hypothesis should be rejected with $df=n-2$ :

$$t = \frac{r\sqrt{n-2}}{\sqrt{1-r^2}}$$

Reject $H_0$ if $+t_{critical} < t$, or $t < - t_{critical}$

### simile linear regression model
The estimated slope coefficient for the regression line describes the change in Y for a one unit change in X. And it is calculated as:

$$\hat{b_1} = \frac{cov_{XY}}{\sigma^2_X}$$

the intercept term ($\hat{b_0}$) may be expressed as:

$$\hat{b_0} = \bar{Y} - \hat{b_1}\bar{X}$$

### standard error of estimate (SEE) and coefficient of determination ($R^2$)

The confidence interval for the regression coefficient, $b_1$ is calculated as:
$$\hat{b_1} \pm (t_c \times s_{\hat{b_1}})$$
Where, $t_c$ is the critical two-tailed t-value for the selected confidence level with the appropriate number of degrees of freedom, which is equal to the number of sample observation minus 2.

A t-test may also be used to test the hypothesis that the true slope coefficient $b_1$ is equal to some hypothesized value. Letting $\hat{b_1}$ be the point estimate for $b_1$, the appropriate test static with n-2 degrees of freedom is:

$$t_{b_1} = \frac{\hat{b_1} - b_1}{s_{\hat{b_1}}}$$

Reject $H_0$ if $t >  + t_{critical}$ or $t <  - t_{critical}$

### confidence intervals for predicted values

The equation for the confidence interval for a predicted value of Y is:

$$\hat{Y} \pm (t_c \times s_{f})$$
where:

$t_c$ = two-tailed critical t-value at the desired level of significant with df = n - 2

$s_f$ = standard error of the forecast

If you do need to calculate $s_f$, it can be done with the following formula:
$$s_f^2 = SEE^2(1+\frac{1}{n} + \frac{(X-\bar{X})^2}{(n-1)s_x^2})$$

### ANOVA
+ Total sum of squares (SST)
$$SST = \sum_{i=1}^n (Y_i - \bar{Y})^2$$
where $\bar{Y}$ is the mean value of $Y$
+ Regression sum of squares (RSS)
$$RSS = \sum_{i=1}^n (\hat{Y_i} - \bar{Y})^2$$
+ Sum of squared errors (SSE)
$$SSE = \sum_{i=1}^n (Y_i - \hat{Y_i})^2$$

Thus, total variation = explained variation + unexplained variation, or:

SST = RSS + SSE

| Source of variation    | Degrees fo Freedom | Sum of Squares | Mean Sum of Squares                         |
| ---------------------- | ------------------ | -------------- | ------------------------------------------- |
| Regression (explained) | 1                  | RSS            | $MSR = \frac{RSS}{k} = \frac{RSS}{1} = RSS$ |
| Error (unexplained)    | n - 2              | SSE            | $MSE = \frac{SSE}{n-2}$                     |
| Total                  | n - 1              | SST            |                                             |

k is the number of slope parameters estimated and n is the number of observation. In general, the regression $df = k$ and the error $df = (n-k-1)$. So in one independent variable linear regression, we use $k=1$ for regression and $n-1-1=n-2$ for the error.

### Calculating $R^2$ and SEE

$$R^2 = \frac{SST - SSE}{SST} = \frac{RSS}{SST}$$

The SEE is the standard deviation of the regression error terms and is equal to the square root of the mean squared error (MSE):

$$SEE = \sqrt{MSE} = \sqrt{\frac{SSE}{n-2}}$$

### The F-statistic

$$F = \frac{MSR}{MSE} = \frac{RSS/k}{SSE/(n-k-1)}$$
**IMPORTANT:** This is always a one-tailed test!

In fact, in simple linear regression we have $t^2 = F$, see [Relationship between F and t statistics](http://www-ist.massey.ac.nz/dstirlin/CAST/CAST/HsimpleAnova/simpleAnova3.html)

## Multiple regression and issues in regression analysis

### Hypothesis testing of regression coefficients
The t-statistic used to test the significance of the individual coefficients in a multiple regression is calculated using the same formula that is used with simple linear regression.
$$t = \frac{\hat{b_j} - b_j}{s_{\hat{b_j}}} = \frac{estimated\ regression\ coefficient - hypothesized\ value}{cofficient\ standard\ error\ of\ b_j}$$

### Interpreting p-Values
The `p-value` or probability value or asymptotic significance is the probability for a given statistical model that, when the null hypothesis is true, the statistical summary (such as the sample mean difference between two compared groups) would be **the same as or of greater** magnitude than the actual observed results.:

+ If the p-value is less than significance level, the null hypothesis can be rejected.
+ If the p-value is greater than the significance level, the null hypothesis cannot be

### F statistic

The *F-statistic*, whihc is always a one-tailed test, is calulated as:

$$F = \frac{MSR}{MSE} = \frac{RSS/k}{SSE/(n-k-1)}$$
where:

$RSS$ = regression sum of squares

$SSE$ = sum of squared errors

$MSR$ = mean regression sum of squares

$MSE$ = mean squared errors

### Coefficient of determination, $R^2$
$R^2$ is also calculated the same way as in simple linear regression.
$$R^2 = \frac{SST - SSE}{SST} = \frac{RSS}{SST}$$
#### Adjusted $R^2$
Unfortunately, $R^2$ by itself may not be a reliable measure of the explanatory pwoer of the multiple regression model. This is because $R^2$ **almost always increases as variables are added to the model**, even if the marginal contribution of the new variable is not statistically significant. The adjusted $R^2$ value is expressed as:
$$R_a^2 = 1 - [(\frac{n-1}{n-k-1})\times(1-R^2)]$$

### ANOVA Tables

| Source     | df (Degrees fo Freedom) | SS (Sum of Squares) | MS (Mean Sum of Squares)  |
| ---------- | ----------------------- | ------------------- | ------------------------- |
| Regression | k                       | RSS                 | $MSR = \frac{RSS}{k}$     |
| Error      | n - k - 1               | SSE                 | $MSE = \frac{SSE}{n-k-1}$ |
| Total      | n - 1                   | SST                 |                           |
### What is heteroskedasticity?
`Heteroskedasticity` occurs when the variance of the residual is not the same across all observations in the sample.

#### Effect of heteroskedasticity on regression analysis
There are four effects of heteroskedasticity you need to be aware of:
+ The stanard errors are usually unreliable estimates.
+ The coefficient estimates (the $\hat{b_j}$) aren't affected.
+ If the standard errors are too small, but the coefficient estimates themselves are not affected, the t-statistics will be too large and the null hypothesis of no statistical significance is rejected too often, The opposite will be true if the standard errors are too large.
+ The F-test is also reliable.

### Detecting heteroskedasticity
There are two methods to detect heteroskedasticity: examing scatter plots of the residuals and using the Breusch-Pagan chi-square ($\chi^2$) test.

The BP chi-square test, which has a chi-square ($\chi^2$) distribution, is calculated as:

BP chi-square test = $n \times R_{resid}^2$ with k degrees of freedom

where:

n = the number of observations

$R_{resid}^2$ = $R^2$ from a second regression of the squared residuals from the first regression on the independent variables

k = the number of the independent variables

### Correcting heteroskedasticity
The most common remedy and the one recommended in the CFA exam is to calculate *robust standard errors* (also called White-corrected standard errors or heteroskedasticity-consistent standard errors). The second is to correct for heteroskedasticity is the use of *generalized least squares*.

$$t = \frac{Coefficient}{White-corrected\ standard\ errors}$$

### Detecting Serial correlation
There are 2 methods used to detect the presence of serial correlation: residual plots and the Durbin-Watson statistic.

$$DW = \frac{\sum_{t=2}^T(\hat{\epsilon}_t - \hat{\epsilon}_{t-1})^2}{\sum_{t=1}^T\hat{\epsilon}_t^2}$$

where:

$\hat{\epsilon}_t$ = residual for period t

If the sample size is vary large:

$$DW \approx 2(1-r)$$
where:

r = correlation coefficient between residuals from one period and those from the previous period.

DW test statistic is approximately equal to 2 if the error terms are homoskedastic and not serially correlated(r=0). DW < 2 if the error terms are positively serially correlated (r>0), and DW > 2 if error terms are negatively serially correlated (r<0).

$H_0$: the regression has no positive serial correlation
+ if DW < $d_l$, the error terms are positively serially correlated (i.e. reject the null hypothesis of no positive serial correlation).
+ if $d_l$ < DW < $d_u$, the test is inconclusive.
+ if DW > $d_u$, there is no evidence that the error terms are positively correlated

### Effect of multicollinearity on regression analysis
Multicollinearity makes the slope coefficients tend to be unreliable, the standard errors of the slope coefficients are artificially inflated. Hence, there is *a greater probability that we will incorrectly conclude that a variable is not statistically significant*.

### Detecting multicollinearity
The most common way to detect multicollinearity is the situation where *t-test values are significantly different than zero*, while the *F-test is statistically significant* and the *$R^2$ is high*. If , in CFA exam, the absolute value of the sample correlation between any two independent variables in the regression is greater than **0.7**, multicollinearity is a potential problem.

### Model specification
There are three broud categories of *model misspecification*:
1. The function form can be misspecified.
    + important variables are omitted.
    + variables should be transformed.
    + data is improperly pooled.
2. Explanatory variables are correlated with the error term in time series models.
    + a lagged dependent variable is used as an independent variable.
    + a function of the dependent variable is used as an independent variable ("forecasting the past").
    + independent variables are measured with error.

## Time-series analysis
A `time series` is a set of observations for a variable over successive periods of time.

### Linear trend model

$$y_t = b_0 + b_1(t) + \epsilon_t$$

where:

$y_t$ = the value of the time series (the dependent variable) at time t

$b_0$ = intercept at the vertical axis

$b_1$ = slope coefficient

$\epsilon_t$ = error term

t = time (independent variable); t = 1, 2, 3...T

### Log=linear trend model
$$y_t = e^{b_0 + b_1(t)}$$
When a variable grows at a constant rate, a log-linear model is most appropriate. When the variable increases over time by a constant amount, a linear trend model is most appropriate.

### Autoregressive model
When the dependent variable is regressed against one or more lagged values of itself, the resultant model is called as an `autoregressive model`.

$$x_t = b_0 + b_1x_{t-1}+...+b_px_{t-p}+\epsilon_t$$

#### Autocorrelation & model fit
If the resisduals have significant autocorrelation, the AR model that produced the residuals is not the best model for the time series being analyzed. The procudure to test whether an AR time series model is correctly specified involves three steps:

1. **Estimate** the AR model being evaluated using linear regression: Start with a first-order AR model, i.e. AR(1)
2. **Calculate** the autocorrelations of the model's residuals (i.e., the level of correlation between the forecast errors from one period to the next).
3. **Test** whether the autocorrelations are significantly different from zero: If the model is correct specified, noen of the autocorrelations will be statistically significant. To test for significance, a *t-test* is used to test the hypothesis that the residuals are zero. The *t-statistic* is the estimated autocorrelation divided by the standard error (i.e., $1/\sqrt{T}$), so the test statistic for each autocorrelation is $t = \frac{\rho_{\epsilon_t,\epsilon_{t-k}}}{1/\sqrt{T}}$ with (T-2) degrees of freedom.

> t-test is difference of the test index divided by the standard error.

A time series must have a finite mean-reverting level (i.e., $\frac{b_0}{1-b_1}$) to be covariance stationary. Thus, a random walk, with or without a drift, is not covariance stationary, and exhibits what is known as a unit root ($b_1$=1).

### Unit Root testing for nonstationary
**Dick and Fuller** created a rather ingenius test for a unit root. Instead of testing whether the original coefficient is different ($b_1 - 1$) is different from zero using a modified *t-test*. If ($b_1 - 1$) is not significantly different from zero, they say that $b_1$ must be equal to 1.0 and, therefore, the series must have a unit root and is nonstationary (i.e., it is not covariance stationary).

### seasonality
To adjust for seasonality in an AR model, an additional lag of the dependent variable is added to the orignal model as another independent variable.

### using ARCH models
An ARCH model is used to test for autoregressive conditional heteroskedasticity. With in the ARCH framework, an ARCH(1) time series is one for which the variance of the residuals in one period is dependent on (i.e., a function of ) the variance of the residuals in the preceding period. To test whether a time series is ARCH(1), the squared residuals from an estimated time-series model, $\hat{\epsilon}_t^2$, are regressed on the first lag of the squared residuals $\hat{\epsilon}_{t-1}^2$. The ARCH(1) regression model is expressed as:
$$\hat{\epsilon}_t^2 = a_0 + a_1 \hat{\epsilon}_{t-1}^2+ \mu_t$$

### Cointegration
**Cointegration** means that two time series are economically linked (realted to the same macro varibales) or follow the same trend and that relationship is not expected to change.

### can linear regression be used to model the relationship between two time series?
<table>

<tr><th></th><th></th><th colspan=2>Independent variable time series</th></tr>
<tr><td></td><td></td><td>Is covariance stationary</td><td>Is NOT covariance stationary</td></tr>
<tr><td rowspan=2><strong>Depandent variable time series</strong></td><td>Is covariance stationary</td><td>Yes</td><td>No</td></tr>
<tr><td>Is NOT covariance stationary</td><td>No</td><td>Yes, IF the two time series are cointegrated</td></tr>
</table>

To determin what typr of model is best suited to meet your needs, follow these guidelines:
1. Determin your goal.
    + Are you attempting to model the relationship of a variable to other variables (e.g., cointegrated time series, cross-sectional multiple regression)?
    + Are you trying to model the variabel over time (e.g., trend model)
2. Plot the data to see the trend. A **structural change** is indicated by a significant *shift* in the plotted data at a point in time that seems to divide the data into two or more distinct patterns. You have to run different models for the structural change.
3. If there is no seasonality or structural shift, use a trand model.
    + If the data plot on a straight line with an upward or downward slope, use a linear trend model.
    + If the data plot in a curve, use a log-linear trend model.
4. Run the trend analysis, compute the residuals, and test for serial correlation using the Durbin Watson test.
    + If you detect no serial correlation, you *can use the model*.
    + If you detect serial correlation, you must use another model (e.g., AR)
5. If the data has serial correlation, reexamine the data for stationarity before running an AR model. If it is not stationary, treat the data for use in an AR model as follows:
    + If the data has linear trend, first-difference the data.
    + If the data has an exponential trend, first-difference the natural log of the data.
    + If there is a structural shift in the data, run two separate models as discussed above.
    + If the data has seasonal component, incorprate the seasonality in the AR model as discussed below.
6. After first-differencing in 5 above, if the series is covariance stationay, run an AR(1) model and test for serial corrlation and seasonality.
    + If there is no remaining serial correlation, you *can use the model*.
    + If you still detect serial correlation, incorporate lagged values of the variable (possibily including one for seasonality--e.g., for monthly data, add the 12th lag of the time series) into the AR model until you hvae removed any serial correlation.
7. Test for ARCH. Regress the square of the residuals on squares of lagged values of the residuals and test whether the resulting coefficient is significantly different from zero.
   + If the coefficient is not significantly different from zero, you *can use the model*.
   + If the coefficient is significantly different from zero, ARCH is present. Correct using generalized least squares.
8. If you have developed two statistically reliable models and want to determin which is better at forecasting, calculate their out-of-sample RMSE.

## Probabilistic approaches: scenario analysis, decision trees, and simulations

### simulation
#### Steps in simluation
1. Determin the probabilistic variables.
2. Define probability distributions for these variables.
   There are three approaches to specifying a distribution:
   + Historical data
   + croess-sectional data
   + Pick a distribution and estimate the parameters
3. Check for corrlations among variables
4. Run the simulation.
   The number of simulations needed for a good output is driven by:
   + The number of uncertain variables
   + The types of distributions
   + The range of outcomes. The wider, the more.
#### Advantages if simulations
There are two advantages of a carefully crafted simulation:
+ Better input quality.
+ Provides a distribution of expected value rather than a point estimate.
#### Constraints
There are threee types of constraints:
1. Book value constraints
   + regulatory capital requirements
   + negative equity
2. Earings and cash flow constraints
   + imposed internally ot meet the analyst expectation
3. Market value constraints

#### Limitation
There are several limitations of using simulations as a risk assessment tool:
1. Input quality.
2. Inappropriate statistical distributions.
3. Non-stationary distributions.
4. Dynamic correltions.

### compare scenario analysis, decision tree, and simulation.
- Scenario analysis and decision trees are used to analyze discrete risk while simulation are used to analyze continuous risk.
- Scenario analysis computes finite cases and the combined probability of the outcome is less than 1.
- Desicion trees is suitable for the condition when risk is both discrete and sequential.

| Appropriate method | Distribution of risk | Sequential?     | Accommodates correlated variables? |
| ------------------ | -------------------- | --------------- | ---------------------------------- |
| Simulations        | Continuous           | Does not matter | Yes                                |
| Senario analysis   | Discrete             | No              | Yes                                |
| Decision trees     | Discrete             | Yes             | No                                 |

# Economics for Valuation