
<!-- README.md is generated from README.Rmd. Please edit that file -->

# urODK: A sing-along ruODK workshop <img src="man/figures/ruODK.png" align="right" alt="Are you ODK?" width="120" />

<!-- badges: start -->

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dbca-wa/urODK/master?urlpath=rstudio)
<!-- badges: end -->

urODK is the companion package to
[ruODK](\(https://dbca-wa.github.io/ruODK/\)), an R client for the ODK
Central API. urODK can be a starting point for new projects consuming
data from ODK Central, or be used in a hands-on workshop.

## Install

To run urODK in a hosted, disposable RStudio instance, hit the “binder”
button. To install urODK in your own environment:

``` r
if (!requireNamespace("remotes")) {install.packages("remotes")}
remotes::install_github("dbca-wa/urODK", dependencies = TRUE, upgrade = "ask")
```

## Configure

Get credentials (un, pw) for the given ODK Central instance and run:

``` r
ruODK::ru_setup(
  svc = "https://sandbox.central.opendatakit.org/v1/projects/14/forms/build_Flora-Quadrat-0-4_1564384341.svc", 
  un = "me@email.com", 
  pw = "..."
)
```

Or add to `.Renviron` via `usethis::edit_r_environ()` (with your own un
and pw):

``` r
ODKC_URL="https://sandbox.central.opendatakit.org"
ODKC_PID=14
ODKC_FID="build_Flora-Quadrat-0-4_1564384341"
ODKC_UN="xxx"
ODKC_PW="xxx"
```

## Get your hands dirty

Start with a colour-by-numbers workflow example: If using RStudio,
create a new RMarkdown workbook “from template” and select ruODK’s
template “odata”, or run with a filename of your choice:

``` r
rmarkdown::draft("my_example.Rmd", "odata", package="ruODK")
```

Follow the instructions in the workbook to explore the data.

Bonus: Create your own form at build.opendatakit.org, collect your own
data. More detail to come.
