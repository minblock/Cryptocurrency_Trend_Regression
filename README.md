Bitcoin / Cryptocurrency Market - Trend Regression
================

Simple trend regressions on bitcoin price data + total cryptocurrency market capitalization.

Bitcoin Price Data
==================

### Exponential Regression

``` r
source("config/Config.R")

Sys.setenv(tz="UTC")
btc.price <- FetchBTCInfo(param           = "market-price",   
                          data.identifier = "btc.close", 
                          date.start      = "2011-01-01")

par(mfrow=c(1, 1))
SimpleLogTrendRegression(data = btc.price, 
                         data.identifier = "BTC-price",
                         regression.type = "exponential",
                         nr.future=120, plot.2sd.log = TRUE, plot.2sd.levels = FALSE)
```

![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-1-1.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-1-2.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-1-3.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-1-4.png)

### Loess Regression

``` r
SimpleLogTrendRegression(data = btc.price, 
                         data.identifier = "BTC-price",
                         regression.type = "loess",
                         nr.future=120, plot.2sd.log = TRUE, plot.2sd.levels = TRUE)
```

![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-2-1.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-2-2.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-2-3.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-2-4.png)

### Logarithmic Regression (on log data)

``` r
SimpleLogTrendRegression(data            = btc.price,
                         data.identifier = "BTC-price",
                         regression.type = "logarithmic",
                         nr.future=120, plot.2sd.log = TRUE, plot.2sd.levels = TRUE)
```

![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-1.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-2.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-3.png)![](README_files/figure-markdown_github-ascii_identifiers/unnamed-chunk-3-4.png)

Cryptocurrency Market Capitalization
====================================

To be addded..

### Exponential Regression

### Loess Regression

### Logarithmic Regression (on log data)

Donations
---------

If you find this software useful and/or you would like to see additional extensions, feel free to donate some crypto:

-   BTC: 1QHtZLZ15Cmj4FPr5h5exDjYciBDhh7mzA
-   LTC: LhKf6MQ7LY1k8YMaAq9z3APz8kVyFX3L2M
-   ETH: 0x8E44D7C96896f2e0Cd5a6CC1A2e6a3716B85B479
-   DASH: Xvicgp3ga3sczHtLqt3ekt7fQ62G9KaKNB

Or preferably, donate some of my favorite coins :)

-   GAME: GMxcsDAaHCBkLnN42Fs9Dy1fpDiLNxSKX1
-   WAVES: 3PQ8KFdw2nWxQATsXQj8NJvSa1VhBcKePaf

Licensing
---------

Copyright 2017 Essential Data Science Consulting ltd. ([EssentialQuant.com](http://essentialquant.com "EssentialQuant") / <jellenvermeir@essentialquant.com>). This software is copyrighted under the MIT license: View added [LICENSE](./LICENSE) file.
