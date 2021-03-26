
# loggerr

<!-- badges: start -->
[![Lifecycle: experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)
[![CRAN status](https://www.r-pkg.org/badges/version/loggerr)](https://CRAN.R-project.org/package=loggerr)
[![Codecov test coverage](https://codecov.io/gh/jesse-smith/loggerr/branch/master/graph/badge.svg)](https://codecov.io/gh/jesse-smith/loggerr?branch=master)
[![R-CMD-check](https://github.com/jesse-smith/loggerr/workflows/R-CMD-check/badge.svg)](https://github.com/jesse-smith/loggerr/actions)
<!-- badges: end -->

loggerr is a dependency-free logging package designed to log output to the
`std_err` stream (i.e. messages, warnings, and errors).
This makes it *very* simple to use in existing scripts; just add `log_start()`
to the top and `log_end()` to the bottom; loggerr records all messages,
warnings, and errors in between.

Although loggerr does not *require* any dependencies, it does use a few for
enhanced functionality:

* The withr package allows `log_start()` to be self-closing
  (meaning `log_end()` isn't needed)
* The blastula package enables email notifications on any system
* On Windows, Outlook can be used for email instead

## Installation

You can install the development version of loggerr with:

``` r
# install.packages("remotes")
remotes::install_github("jesse-smith/loggerr")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
library(loggerr)
log_file <- tempfile()
log_start(log_file)

message("This is a message")
warning("This is a warning")
stop("This is an error")

log_end()
```

## Code of Conduct
  
Please note that the loggerr project is released with a [Contributor Code of Conduct](https://contributor-covenant.org/version/2/0/CODE_OF_CONDUCT.html).
By contributing to this project, you agree to abide by its terms.
