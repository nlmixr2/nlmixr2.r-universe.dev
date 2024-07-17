
  - [R universe](#r-universe)

# R universe

This generates the R universe json file for the `nlmixr2` domain.

``` r
df <- data.frame(
  package = c("nlmixr2targets ", "nlmixr2data",
              "PreciseSums", "nlmixr2rpt ", "nlmixr2lib",
              "dparser-R",
              "nlmixr2data", "lotri", "rxode2ll",
              "rxode2", "nlmixr2est",
              "nonmem2rx", "monolix2rx",
              "nlmixr2extra", "nlmixr2plot", "nlmixr2",
              "xpose.nlmixr2", "nlmixr2targets", "nlmixr2rpt",
              "babelmixr2"))

df$url <- paste0("https://github.com/nlmixr2/", df$package)
df$subdir <- NA_character_
df$package <- gsub("dparser-R", "dparser", df$package)

jsonlite::write_json(df, 'packages.json', pretty = TRUE)
```
