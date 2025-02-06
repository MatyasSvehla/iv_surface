# Implied Volatility Surface

- The main purpose of the project is to model volatility surface for a given stock ticker. Therefore, it first computes implied volatilities based on call options' prices and then plots the values in a static and an intereactive 3D plot. 
- Furthermore, several tools for analysis of options and volatility are provided. First, a tool for examination of historical and conditional GARCH(1,1) volatility is provided. Second, Greeks calculator may be used to calculate values of delta, gamma, theta, rho and vega.

- The project has been written using Python 3.13.1. List of dependencies may be found in requirements.txt file

## How to use the tools
### IVCalculator
- inputs: ticker, options type ("call","put"), Open Interest lower bound
- .compute_iv: executes all operations necessary to obtain implied volatilites from option prices based on above speficifactions, it needs to be run before proceed to plotting methods (otherwise Warning is called)
- . plot_it_values: uses the implied volatility values from .compute_iv and plots them into 3D graph with strike values on x-axis, days to expiration on y-axis and iv values on z-axis.
- .plot_iv_values_inter: plots the implied volatility values in the same way as .plot_iv_values, however, into an interactive 3D plot
