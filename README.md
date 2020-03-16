
<!-- README.md is generated from README.Rmd. Please edit that file -->

# linearspectestr

<!-- badges: start -->

[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/FedericoGarza/linearspectestr/commit-activity)
[![MIT
license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)

<!-- badges: end -->

The goal of `linearspectestr` is to contrast the linear hypothesis of a
model:

![formula](man/figures/CodeCogsEqn.gif)

Using the Domínguez-Lobato test which relies on wild-bootstrap.

## Installation

You can install (soon) the released version of `linearspectestr` from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("linearspectestr")
```

And the development version from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("FedericoGarza/linearspectestr")
```

## Example

``` r
library(linearspectestr)

x <- 1:100
y <- 1:100

lm_model <- lm(y~x)

dl_test <- dominguez_lobato_test(lm_model)
```

``` r
dplyr::glimpse(dl_test$test)
#> Observations: 1
#> Variables: 7
#> $ name_distribution <chr> "rnorm"
#> $ name_statistic    <chr> "cvm_value"
#> $ statistic         <dbl> 7.562182e-29
#> $ p_value           <dbl> 0.4166667
#> $ quantile_90       <dbl> 2.58979e-28
#> $ quantile_95       <dbl> 3.36778e-28
#> $ quantile_99       <dbl> 5.764217e-28
```

Also `linearspectestr` can plot the results

``` r
plot_dl_test(dl_test)
```

<img src="man/figures/README-plot-1.png" width="70%" />

## References

  - Manuel A. Domínguez and Ignacio N. Lobato (2019). [Specification
    testing with estimated
    variables.](\(https://www.tandfonline.com/doi/citedby/10.1080/07474938.2019.1687116?scroll=top&needAccess=true\))
    Econometric Reviews.
