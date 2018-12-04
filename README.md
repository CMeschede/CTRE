
<!-- README.md is generated from README.Rmd. Please edit that file -->
CTRE
====

[![Travis-CI Build Status](https://api.travis-ci.org/UNSW-MATH/CTRE.svg?branch=master)](https://travis-ci.org/UNSW-MATH/CTRE) [![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/CTRE)](https://cran.r-project.org/package=CTRE) [![Downloads](http://cranlogs.r-pkg.org/badges/CTRE)](https://cran.r-project.org/package=CTRE) [![DL\_Total](http://cranlogs.r-pkg.org/badges/grand-total/CTRE?color=blue)](https://cran.r-project.org/package=CTRE)

The CTRE package fits a CTRE model ("Continuous Time Random Exceedances") to extremes of 'bursty' time series.

-   A [bursty](https://en.wikipedia.org/wiki/Burstiness) time series typically has heavy-tailed inter-arrival times.
-   Given a high threshold, the times between threshold crossings follow a [Mittag-Leffler](https://strakaps.github.io/MittagLeffleR/) distribution, whose scale parameter increases with the threshold.

The magnitudes of the extremes is modelled via the [POT](https://en.wikipedia.org/wiki/Extreme_value_theory#Data_analysis) ("Peaks-Over-Threshold") method, which is standard in Extreme Value Theory. It is the time between threshold crossings that is the focus of the CTRE model.

Installation
------------

### Stable release on CRAN

You can install `CTRE` from CRAN via

``` r
install.packages("CTRE")
library(CTRE)
```

### Development version on Github

Install the `devtools` package first, then

``` r
# install.packages("devtools")
devtools::install_github("strakaps/CTRE")
library("CTRE")
```

Usage
-----

-   Create a [`ctre`](/CTRE/reference/ctre.html) object from a time series, a data frame, or two vectors.
-   Plot it with [`plot`](/CTRE/reference/plot.ctre.html)
-   Discard the data below a threshold with [`thin`](/CTRE/reference/thin.html)
-   Extract data with [`interarrival`](/CTRE/reference/interarrival.html), [`time`](/CTRE/reference/time.html) and [`magnitudes`](/CTRE/reference/magnitudes.html)
-   Create stability plots with [`MLestimates`](/CTRE/reference/MLestimates.html)
-   Look at diagnostic plots ([`mlqqplot`](/CTRE/reference/mlqqplot.html), [`acf`](/CTRE/reference/acf.html), [`empcopula`](/CTRE/reference/empcopula.html))

Shiny App
---------

-   The package comes with two examples of bursty time series: solar flare magnitudes and bitcoin trading volumes.
-   For parameter estimates of the Mittag-Leffler distribution, see the tab "Exceedance Times".
-   For the POT model fit, see the tab "Exceedances"
-   CTRE model assumptions are checked via
-   a QQ plot of the Mittag-Leffler distribution
-   an empirical copula plot checking for dependence between inter-arrival times and magnitudes
-   a plot of the autocorrelation function for the two series (interarrival times and magnitudes).

To run the Shiny app from within RStudio:

``` r
runCTREshiny()
```

<iframe src="https://strakaps.shinyapps.io/ctre-app/" style="border: none; width: 800px; height: 900px">
</iframe>

The CTRE paper
--------------

"Peaks Over Threshold for Bursty Time Series", Katharina Hees, Smarak Nayak, Peter Straka (2018). <https://arxiv.org/abs/1802.05218>
