ST 558 Project 2
================
Hannah Park
10/15/2020

# Introduction

You should have an introduction section that briefly describes the data
and the variables you have to work with (no need to discuss all of them,
just the ones you want to use). **If you are analyzing the bike share
data, do not use the casual and registered variables to do any
modeling\!**

You should also mention the purpose of your analysis and the methods
you’ll use (no need to detail them here) for analysis.

# Data

``` r
# Read in data
url <- "https://archive.ics.uci.edu/ml/machine-learning-databases/00275/Bike-Sharing-Dataset.zip"
download.file(url, "Bike-Sharing-Dataset.zip")

unzip("Bike-Sharing-Dataset.zip", exdir = "./Data")
df.bike <- read_csv("/Data/day.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

``` r
df.bike.day <- df.bike %>%
  select(-casual, -registered) %>%
  filter(weekday == 1)

# Randomply sample from the data 
# Form training and test sets
train <- sample(1:nrow(df.bike.day), size = nrow(df.bike.day)*0.7)
test <- dplyr::setdiff(1:nrow(df.bike.day), train)
df.train <- df.bike.day[train, ]
df.test <- df.bike.day[test, ]
```

# Summarizations

``` r
ggplot(df.train, aes(x = dteday, y = cnt)) +
  geom_point(aes(colour = factor(season)))
```

![](MondayAnalysis_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

``` r
df.train %>%
  gather(temp, atemp, hum, windspeed, key = "var", value = "value") %>%
  ggplot(aes(x = value, y = cnt, color = factor(yr), shape = factor(season))) +
  geom_point() +
  geom_smooth(aes(group = factor(yr))) +
  facet_wrap(~var, scales = "free") 
```

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

![](MondayAnalysis_files/figure-gfm/unnamed-chunk-2-2.png)<!-- -->