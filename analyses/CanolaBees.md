Canola Bee Analysis
================
Dr. Riley M. Anderson, Olivia Shaffer, & Salena Helmreich
October 30, 2024

  

- [Overview](#overview)
  - [Summary of Results](#summary-of-results)
- [Bee community composition](#bee-community-composition)
  - [Site classification by species composition (Random
    Forest)](#site-classification-by-species-composition-random-forest)
  - [Bee composition by habitat type](#bee-composition-by-habitat-type)
  - [Bee composition by habitat type and bloom
    period](#bee-composition-by-habitat-type-and-bloom-period)
- [Session Information](#session-information)

## Overview

This analysis explores Salena and Olivia’s canola experiment.

### Summary of Results

- No difference in bee community composition across habitat types
  (natural or semi-natural), or habitat types and bloom period.

## Bee community composition

    ## Permutation test for adonis under reduced model
    ## Terms added sequentially (first to last)
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## adonis2(formula = habitat_matrix ~ land_type, data = habitat_meta, method = "bray")
    ##           Df SumOfSqs      R2      F Pr(>F)
    ## land_type  1   0.2837 0.03403 0.9863  0.468
    ## Residual  28   8.0535 0.96597              
    ## Total     29   8.3372 1.00000
    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df  Sum Sq   Mean Sq      F N.Perm Pr(>F)
    ## Groups     1 0.00197 0.0019684 0.1395    999  0.726
    ## Residuals 28 0.39496 0.0141059
    ## Permutation test for adonis under reduced model
    ## Terms added sequentially (first to last)
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## adonis2(formula = habitat_matrix ~ period, data = habitat_meta, method = "bray")
    ##          Df SumOfSqs      R2      F Pr(>F)
    ## period    2   0.5423 0.06505 0.9392  0.559
    ## Residual 27   7.7949 0.93495              
    ## Total    29   8.3372 1.00000
    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df   Sum Sq  Mean Sq      F N.Perm Pr(>F)
    ## Groups     2 0.026775 0.013388 1.2897    999  0.294
    ## Residuals 27 0.280276 0.010381
    ## Permutation test for adonis under reduced model
    ## Terms added sequentially (first to last)
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## adonis2(formula = habitat_matrix ~ site, data = habitat_meta, method = "bray")
    ##          Df SumOfSqs      R2      F Pr(>F)
    ## site      9   2.7920 0.33488 1.1189  0.227
    ## Residual 20   5.5452 0.66512              
    ## Total    29   8.3372 1.00000
    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df  Sum Sq  Mean Sq      F N.Perm Pr(>F)
    ## Groups     9 0.16911 0.018791 0.6796    999  0.726
    ## Residuals 20 0.55301 0.027650

### Site classification by species composition (Random Forest)

    ## Random Forest 
    ## 
    ## 30 samples
    ## 27 predictors
    ##  2 classes: 'natural', 'semi' 
    ## 
    ## No pre-processing
    ## Resampling: Bootstrapped (25 reps) 
    ## Summary of sample sizes: 30, 30, 30, 30, 30, 30, ... 
    ## Resampling results across tuning parameters:
    ## 
    ##   mtry  Accuracy   Kappa   
    ##    2    0.7271692  0.420075
    ##   14    1.0000000  1.000000
    ##   27    1.0000000  1.000000
    ## 
    ## Accuracy was used to select the optimal model using the largest value.
    ## The final value used for the model was mtry = 14.
    ## 
    ## Call:
    ##  randomForest(x = select(rf_matrix, -period, -site, -period_site_land),      y = rf_matrix$land_type, mtry = 2, importance = T, nPerm = 999,      proximity = T) 
    ##                Type of random forest: classification
    ##                      Number of trees: 500
    ## No. of variables tried at each split: 2
    ## 
    ##         OOB estimate of  error rate: 10%
    ## Confusion matrix:
    ##         natural semi class.error
    ## natural      17    1  0.05555556
    ## semi          2   10  0.16666667
    ##                  natural       semi MeanDecreaseAccuracy MeanDecreaseGini
    ## land_type    21.18790786 21.9966570           24.1855669       6.32626353
    ## Agapostemon  -1.55615058 -0.6871270           -1.0810774       0.06355599
    ## Andrena      -1.72813968 -1.2372234           -1.6572448       0.67066678
    ## Anthidium    -0.30681487  1.0010015            0.4078739       0.07747130
    ## Anthophora    0.00000000  0.0000000            0.0000000       0.05594915
    ## Apis         -1.78959241 -0.7699222           -1.8370620       0.17257545
    ## Bombus       -1.57099249 -0.1808250           -1.5344281       0.30029351
    ## Ceratina      5.29131507  5.6296743            7.4108625       1.58064589
    ## Colletes     -1.38942504 -1.0010015           -1.7360614       0.04510748
    ## Diadasia      0.00000000  0.0000000            0.0000000       0.02270397
    ## Dufourea     -1.00100150  1.7200523            0.9208256       0.07173164
    ## Epoleus       0.00000000  0.0000000            0.0000000       0.02277216
    ## Halictus     -1.92118443 -1.8724892           -2.1274674       0.55917587
    ## Heriades      0.00000000  0.0000000            0.0000000       0.02348263
    ## Hoplitis      0.00000000  0.0000000            0.0000000       0.05398612
    ## Hylaeus      -0.81877047  0.5578407           -0.4602527       0.16253444
    ## Lasioglossum  0.04624097 -1.7661357           -0.5613434       0.94861036
    ## Megachile     3.12017130 -0.3387059            2.0558658       0.29562769
    ## Melissodes   -0.29831233  0.4725986            0.3215256       0.18905735
    ## Nomada       -2.05877225 -3.0448975           -3.2479400       0.44057224
    ## Nomia         0.00000000  0.0000000            0.0000000       0.01116724
    ## Osmia         1.58114740  0.9607080            1.2700882       0.63165417
    ## Panurginus   -1.00100150  0.0000000           -1.0010015       0.06525045
    ## Peponapis     0.00000000  0.0000000            0.0000000       0.08848862
    ## Perdita       1.34406228  1.2669398            2.0008436       0.20096079
    ## Protandrena  -0.15339661 -1.0010015           -0.3221117       0.08116881
    ## Sphecodes     0.28006849 -2.0240647           -1.3281100       0.42264849

|              | natural |   semi | MeanDecreaseAccuracy | MeanDecreaseGini |
|:-------------|--------:|-------:|---------------------:|-----------------:|
| land_type    |  21.188 | 21.997 |               24.186 |            6.326 |
| Ceratina     |   5.291 |  5.630 |                7.411 |            1.581 |
| Lasioglossum |   0.046 | -1.766 |               -0.561 |            0.949 |
| Andrena      |  -1.728 | -1.237 |               -1.657 |            0.671 |
| Osmia        |   1.581 |  0.961 |                1.270 |            0.632 |
| Halictus     |  -1.921 | -1.872 |               -2.127 |            0.559 |

**Random Forest classification of habitat type by species composition.**
The model was tuned without pre-processing. Overall model accuracy was
81%. The model can delineate the habitat types with an overall *out of
bag error* of 3.33% using bee community composition as the predictor
matrix.

### Bee composition by habitat type

![](CanolaBees_files/figure-gfm/nmds_habitat_fig-1.png)<!-- -->
**Variation in community composition across habitat types.** Bee species
are plotted on a two-dimensional non-metric multidimensional scaling
ordination of the 30 combinations of site, period, and habitat type.
Small points are the individual site/period/habitat combinations. Large
points are the centroids of the two habitat types with natural habitat
in orange, semi-natural habitat in blue. Ellipses are 95% confidence
intervals around the habitat centroids. Bees species shown are the most
representative (top 20th percentile of a random forest analysis) of the
compositional differences among sites. Text size of the labels is
proportional to variable importance score (mean decrease in Gini score).

### Bee composition by habitat type and bloom period

![](CanolaBees_files/figure-gfm/nmds_period_habitat_fig-1.png)<!-- -->

Note that there is considerable overlap in community composition at all
comparisons (PERMANOVA **habitat;** *P* = 0.44, *F* = 0.99, **site;**
*P* = 0.27, *F* = 1.12, **period**; *P* = 0.54, *F* = 0.94). From this
analysis, we can conclude that community bee community composition does
not vary across natural/semi-natural habitat types, sites, or bloom
period.

## Session Information

    R version 4.2.3 (2023-03-15 ucrt)
    Platform: x86_64-w64-mingw32/x64 (64-bit)
    Running under: Windows 10 x64 (build 19045)

    Matrix products: default

    locale:
    [1] LC_COLLATE=English_United States.utf8 
    [2] LC_CTYPE=English_United States.utf8   
    [3] LC_MONETARY=English_United States.utf8
    [4] LC_NUMERIC=C                          
    [5] LC_TIME=English_United States.utf8    

    attached base packages:
    [1] stats     graphics  grDevices utils     datasets  methods   base     

    other attached packages:
     [1] caret_6.0-94         randomForest_4.7-1.1 vegan_2.6-6.1       
     [4] lattice_0.20-45      permute_0.9-7        emmeans_1.10.2      
     [7] knitr_1.47           car_3.1-2            carData_3.0-5       
    [10] sjPlot_2.8.16        lme4_1.1-35.3        Matrix_1.5-3        
    [13] glmmTMB_1.1.9        cowplot_1.1.3        lubridate_1.9.3     
    [16] forcats_1.0.0        stringr_1.5.1        dplyr_1.1.4         
    [19] purrr_1.0.2          readr_2.1.5          tidyr_1.3.1         
    [22] tibble_3.2.1         ggplot2_3.5.1        tidyverse_2.0.0     

    loaded via a namespace (and not attached):
     [1] TH.data_1.1-2        minqa_1.2.7          colorspace_2.1-0    
     [4] class_7.3-21         sjlabelled_1.2.0     rprojroot_2.0.4     
     [7] estimability_1.5.1   proxy_0.4-27         rstudioapi_0.16.0   
    [10] farver_2.1.2         listenv_0.9.1        ggrepel_0.9.5       
    [13] prodlim_2023.08.28   fansi_1.0.6          mvtnorm_1.2-5       
    [16] codetools_0.2-19     splines_4.2.3        sjmisc_2.8.10       
    [19] nloptr_2.0.3         pROC_1.18.5          ggeffects_1.6.0     
    [22] cluster_2.1.4        compiler_4.2.3       sjstats_0.19.0      
    [25] fastmap_1.2.0        cli_3.6.2            htmltools_0.5.8.1   
    [28] tools_4.2.3          coda_0.19-4.1        gtable_0.3.5        
    [31] glue_1.7.0           reshape2_1.4.4       Rcpp_1.0.12         
    [34] vctrs_0.6.5          nlme_3.1-162         iterators_1.0.14    
    [37] insight_0.20.1       timeDate_4032.109    gower_1.0.1         
    [40] xfun_0.44            globals_0.16.3       timechange_0.3.0    
    [43] lifecycle_1.0.4      future_1.33.2        MASS_7.3-58.2       
    [46] zoo_1.8-12           scales_1.3.0         ipred_0.9-14        
    [49] hms_1.1.3            parallel_4.2.3       sandwich_3.1-0      
    [52] RColorBrewer_1.1-3   TMB_1.9.11           yaml_2.3.8          
    [55] rpart_4.1.23         stringi_1.8.4        highr_0.11          
    [58] foreach_1.5.2        e1071_1.7-14         hardhat_1.4.0       
    [61] boot_1.3-28.1        lava_1.8.0           rlang_1.1.4         
    [64] pkgconfig_2.0.3      evaluate_0.24.0      labeling_0.4.3      
    [67] recipes_1.0.10       tidyselect_1.2.1     parallelly_1.37.1   
    [70] plyr_1.8.9           magrittr_2.0.3       R6_2.5.1            
    [73] generics_0.1.3       multcomp_1.4-25      pillar_1.9.0        
    [76] withr_3.0.0          mgcv_1.8-42          survival_3.5-3      
    [79] datawizard_0.11.0    abind_1.4-5          nnet_7.3-18         
    [82] future.apply_1.11.2  performance_0.12.0   utf8_1.2.4          
    [85] tzdb_0.4.0           rmarkdown_2.27       grid_4.2.3          
    [88] data.table_1.15.4    ModelMetrics_1.2.2.2 digest_0.6.35       
    [91] xtable_1.8-4         numDeriv_2016.8-1.1  stats4_4.2.3        
    [94] munsell_0.5.1       
