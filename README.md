# Implied Volatility Surface

- The main purpose of the project is to model volatility surface for a given stock ticker. Therefore, it first computes implied volatilities based on call options' prices and then plots the values in a static and an intereactive 3D plot. 
- Furthermore, several tools for analysis of options and volatility are provided. First, a tool for examination of historical and conditional GARCH(1,1) volatility is provided. Second, Greeks calculator may be used to calculate values of delta, gamma, theta, rho and vega.

- The project has been written using Python 3.13.1. List of dependencies may be found in requirements.txt file

## How to use the tools
### IVCalculator
- inputs: ticker, options type ("call","put"), Open Interest lower bound
- .compute_iv: executes all operations necessary to obtain implied volatilites from option prices based on above speficifactions, it needs to be run before proceed to plotting methods (otherwise Warning is called)
- .plot_iv_values: uses the implied volatility values from .compute_iv and plots them into 3D graph with strike values on x-axis, days to expiration on y-axis and iv values on z-axis.
- .plot_iv_values_inter: plots the implied volatility values in the same way as .plot_iv_values, however, into an interactive 3D plot
### OptionGreeksCalculator
- inputs: sigma(volatility), S(spot price), K(exercise price), r(interest rate), t(time in years to expiration (act/365)), type (option type -> "call" or "put")
- .delta: returns a value of delta
- .gamma: returns a value of gamma
- .theta: returns a value of theta
- .rho: returns a value of rho
- .vega: returns a value of vega
- .compute_all: returns ALL greeks in a data frame
### VolatilityCalculator
- input: ticker
- .garch_vol: inputs: training period (in days), graph window(purely graphical adjustment...how big interval we want displayed), forecast horizon(how many days forward forecast we want, based on our fitted GARCH(1,1) model), returns the latest computed conditional volatility value and a plot of conditional volatility together with the volatility forecast in red
- .hist_vol: inputs: historical volatility window (the value of how many periods backwards should be considered for the calculation of historical volatility), returns the latest historical volatility value and plots the graph of the last month's historical volatility values based on the specified window
