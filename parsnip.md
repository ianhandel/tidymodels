Tidymodels
================
Ian Handel
23/04/2020

``` r
mpg <- mpg %>% 
  mutate(drive_f = factor(drv == "f"))
```

``` r
lr_mod <- 
  logistic_reg() %>% 
  set_engine("glm")
```

``` r
lr_fit <-
  lr_mod %>% 
fit(drive_f ~ displ + cyl, data = mpg)
```

``` r
lr_fit %>% 
  tidy()
```

    ## # A tibble: 3 x 5
    ##   term        estimate std.error statistic       p.value
    ##   <chr>          <dbl>     <dbl>     <dbl>         <dbl>
    ## 1 (Intercept)     3.82     0.742      5.16 0.000000250  
    ## 2 displ          -3.07     0.525     -5.86 0.00000000469
    ## 3 cyl             1.06     0.328      3.22 0.00127
