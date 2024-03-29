
## Answers:

### 1. Stationarity matter in Time Series Analysis:
Stationarity refers to the fact that the statistical properties of a time series or the process generating it do not change over time. Stationarity is a prerequisite for mathematically representing a time series and be able to perform analysis and forecasting. It is important because many useful analytical tools and statistical tests and models rely on it by considering processes to be stationary. It is easier to analyze and model stationary processes. Some statistical properties such as law of large numbers, central limit theorem still hold for stationary random variables (non-independent variables). Stationarity is also important for model describing the data to have stable accuracy at different time points.


### 2. Autocorrelation Function (ACF) for a stationary series:
The autocorrelation function (ACF) is the correlation of a set of observations (or signal) with its delayed copy ( or a lag) as a function of the delay. In other words, ACF defines, on average, how data points in a time series are related to the preceding data points. For stationary time series, the values of autocorrelation tend to decrease to near zero very quickly as the delay increase. However, the autocorrelation pattern is constant (on a correlogram). Stationary time series do not have a trend (shorter lags with large positive correlations and slow decrease of correlations as the lags increase), and no seasonal pattern (larger autocorrelations for lags at multiples of the seasonal frequency than for other lags). The autocorrelation function Rk at lag k (k ≥ 0) of a stationary time series is defined as the autocovariance function Sk at lag k divided by the variance S0, Rk = Sk/S0. 

### 3. Non-Sequential Deep Learning Models Vs Sequential Models in Time-Series Forecasting:
Yes, Non-Sequential Deep Learning Models can outperform Sequential Models in Time-Series Forecasting. Many research works such as in Shaojie Bai et al. (https://arxiv.org/pdf/1803.01271.pdf) have found that temporal convolutional network (TCN), which is a non-sequential model, gives better results than recurrent neuro network (RNN) such as LSTMs and GRU. Sequential models have the ability to capture long history by learning lagged features. However, their infinite memory advantage is limited. RNN are not able to maintain a much longer effective history as TCN. Shaojie Bai et al. states that TCN have other advantages such as parallelism, stable gradients and low training memory footprint.

4### 4. Adjacent observations in time series data (excluding white noise) are IID:
B. False
Sets of observations are more likely to be correlated with the correlation getting higher as the time intervals between two observations become shorter. This property makes forecasting possible in time series since prediction rely on previous observations and not the currently observed data as it is for classification or regression.

### 5. Decision Tree model Vs Time series regression model for time series dataset
Model 1 (Decision Tree model) couldn’t map the linear relationship as good as Model 2 (Time series regression model).
Even though tree based models are efficient they will not perform better than regression models at finding and exploiting linear relationships, since in essence a time series model is similar to a regression model.

### 6.	Second differencing in time series can help to eliminate:
Quadratic Trend
A ﬁrst diﬀerence eliminates a linear trend, a second diﬀerence eliminates a quadratic trend, and so on. Differencing can be approximated to a derivative, where a second order derivative of a quadratic give a constant. Differencing can help eliminate (or reduce) trend and seasonality and hence stabilize the mean of a time series. When first differencing does not make data appear to be stationary, it may be necessary to difference the data a second time to obtain a stationary series. 

###7.	Correct statement, ARIMA parameters and components:
C, 2. If moving average component (q) in an ARIMA model is 1, it means that there is auto-correlation in the series with lag 1.
Moving average component (MA) is denoted by q. In ARIMA, q=1 means that it is an error term and there is auto-correlation with one lag.
When autoregressive parameter p=0, it means that there is no auto-correlation in the series.  When p=1, it means that the series auto-correlation is till one lag.
In ARIMA time series analysis, integrated component (the inverse of differencing) is denoted by d.  When d=0, it means the series is stationary and we do not need to take the difference of it. When d=1, it means that the series is not stationary and to make it stationary, we need to take the first difference.  When d=2, it means that the series has been differenced twice.  Usually, more than two time difference is not reliable.

###8.	Time series plot – comparison: ###
Both time series have a trend, they present diminishing values with time (in the long term). This is an indication that they are both non-stationary. The time series with red color (visibility) has small variance, while The series with black color(AERONET) has high variance.

### 9. Methods to check the stationarity of a time series:
Some methods include:
Visualization: plotting the data or functions of it can help in detecting stationarity and determining visually whether data present some known property of stationary (or non-stationary) data. The plot may show whether there is seasonality, trend or changing levels with time in the data.
Looking at Autocorrelation Function (ACF) plots for increasing lags (a correlogram), the values tend to degrade to zero quickly for stationary time series, while for non-stationary data the degradation will happen more slowly.

Parametric tests: use statistical tests developed to detect specific types of stationarity.
- The Dickey-Fuller test: test the null hypothesis that a unit root is present in an autoregressive model of a given time series and that the process is thus not stationary.
- The KPSS Test: tests for the presence of a unit root. The null hypothesis assumes stationarity around a mean or a linear trend, while the alternative is the presence of a unit root.
- The Zivot and Andrews Test: a unit root test in which the exact time of the break-point is assumed to be unknown.
- Variance Ratio Test: a semi-parametric unit root tests.
Non-parametric tests (ex: https://www.cireqmontreal.com/wp-content/uploads/2012/01/11-12kanaya.pdf)

### 10.	ARIMA process and parameters of an ARIMA model: 
An autoregressive integrated moving average model is a form of regression analysis that gauges the strength of one dependent variable relative to other changing variables. The model’s goal is to either better understand the data set or to predict future values based on past values.
ARIMA components are:
- Autoregression (AR): refers to a model that shows a changing variable that regresses on its own lagged, or prior, values. The variable of interest is forecast using a linear combination of past values of the variable.
- Integrated (I): represents the differencing of raw observations to allow for the time series to become stationary (i.e., data values are replaced by the difference between the data values and the previous values).
- Moving average (MA): incorporates the dependency between an observation and a residual error from a moving average model applied to lagged observations. In other words, a moving average model uses past forecast errors in a regression-like model.

ARIMA parameters:
- p: (AR parameter) the number of lag observations in the model; also known as the lag order.
- d: (Integrated component) the number of times that the raw observations are differenced; also known as the degree of differencing.
- q: (MA component) the size of the moving average window; also known as the order of the moving average.
Non-seasonal ARIMA are denoted as ARIMA(p,d,q).
There are also seasonal ARIMA models that are usually denoted ARIMA(P,D,Q)m, where m refers to the number of periods in each season.




## Analysis – Time series decomposition part.
The decomposition plot shows that there is a trend and seasonality in the data. The trend plot (second one) highlight a long-term increase of sales as time goes by. The seasonal component (third plot) reveals that there is a seasonal trend. The length of seasonality appears to be one year, or 12 months. The seasonality is also noticed on the ACF (autocorrelation) plot where there is increased values at intervals equaling to 12 lags compared to neighboring lags. The curve of the seasonal component has an increasing amplitude along the years. This may signal a slight increase in variance. The presence of seasonality and trend leads to the conclusion that the data is non-stationary.

### N.B.: More information are available in Jupyter notebooks 


