BeeSearch Multivariate Analyses
================
Dr. Riley M. Anderson
December 09, 2024

  

- [Overview](#overview)
  - [Summary of Results](#summary-of-results)
- [Across sites](#across-sites)
  - [Site classification by species composition (Random
    Forest)](#site-classification-by-species-composition-random-forest)
  - [NMDS by Site figure (include
    this)](#nmds-by-site-figure-include-this)
- [Session Information](#session-information)

## Overview

What is this analysis about?

### Summary of Results

- 

## Across sites

    ## Permutation test for adonis under reduced model
    ## Terms added sequentially (first to last)
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## adonis2(formula = site_matrix ~ Site * Year, data = site_meta, method = "bray")
    ##           Df SumOfSqs      R2      F Pr(>F)   
    ## Site       2   1.0050 0.05314 2.1105  0.006 **
    ## Year       1   0.4331 0.02290 1.8188  0.075 . 
    ## Site:Year  2   0.3298 0.01744 0.6926  0.809   
    ## Residual  72  17.1432 0.90652                 
    ## Total     77  18.9111 1.00000                 
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df  Sum Sq  Mean Sq      F N.Perm Pr(>F)
    ## Groups     6 0.13306 0.022176 1.5361    999  0.171
    ## Residuals 71 1.02498 0.014436
    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df  Sum Sq  Mean Sq      F N.Perm Pr(>F)   
    ## Groups     2 0.18685 0.093426 6.8005    999  0.004 **
    ## Residuals 75 1.03036 0.013738                        
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

### Site classification by species composition (Random Forest)

    ## Random Forest 
    ## 
    ##  78 samples
    ## 108 predictors
    ##   3 classes: 'BPF', 'POS', 'SCL' 
    ## 
    ## No pre-processing
    ## Resampling: Bootstrapped (25 reps) 
    ## Summary of sample sizes: 78, 78, 78, 78, 78, 78, ... 
    ## Resampling results across tuning parameters:
    ## 
    ##   mtry  Accuracy   Kappa    
    ##     2   0.7229644  0.2671388
    ##    55   0.8275113  0.6340112
    ##   108   0.7948119  0.5768530
    ## 
    ## Accuracy was used to select the optimal model using the largest value.
    ## The final value used for the model was mtry = 55.
    ## 
    ## Call:
    ##  randomForest(x = select(rf_matrix, -Year, -Station, -StationYear,      -Site), y = rf_matrix$Site, mtry = 55, importance = T, nPerm = 999,      proximity = T) 
    ##                Type of random forest: classification
    ##                      Number of trees: 500
    ## No. of variables tried at each split: 55
    ## 
    ##         OOB estimate of  error rate: 15.38%
    ## Confusion matrix:
    ##     BPF POS SCL class.error
    ## BPF  13   1   0  0.07142857
    ## POS   2  48   1  0.05882353
    ## SCL   0   8   5  0.61538462

|                          |    BPF |    POS |    SCL | MeanDecreaseAccuracy | MeanDecreaseGini |
|:-------------------------|-------:|-------:|-------:|---------------------:|-----------------:|
| Halictus tripartitus     |  8.534 | 12.413 |  3.964 |               13.345 |            3.562 |
| Agapostemon texanus      | 10.107 |  8.470 | -0.027 |               10.786 |            2.603 |
| Melissodes rivalis       |  1.665 |  7.682 |  1.279 |                7.984 |            1.886 |
| Bombus melanopygus       |  8.665 |  2.562 |  2.745 |                8.081 |            1.827 |
| Osmia albolateralis      |  5.614 |  6.701 |  3.748 |                8.405 |            1.689 |
| Bombus flavifrons        |  6.294 |  6.559 |  6.689 |                9.181 |            1.664 |
| Bombus fervidus          |  7.950 |  6.433 |  0.092 |                8.418 |            1.616 |
| Halictus confusus        |  8.295 |  1.645 |  4.043 |                7.319 |            1.437 |
| Apis mellifera           |  7.814 |  2.289 |  4.892 |                7.847 |            1.397 |
| Bombus vosnesenskii      |  3.362 |  6.426 |  0.687 |                6.755 |            1.161 |
| Lasioglossum incompletum |  4.464 |  1.163 |  1.531 |                4.138 |            0.834 |

    ## # A tibble: 3 × 2
    ##   Site   mean
    ##   <fct> <dbl>
    ## 1 BPF     2  
    ## 2 POS    44.5
    ## 3 SCL    21.2

![](composition_analyses_files/figure-gfm/random_forest_sites-1.png)<!-- -->

**Random Forest classification of site by species composition.** The
model was tuned without pre-processing. Bootstrapped resampling used 25
replicates. The model was built with 500 trees and model tuning
maximized accuracy at 55 variables/split. Overall model accuracy was
82%. Out of bag estimate of error rate was 16.7%. This lends further
support to the NMDS figure below, species composition is very similar
across SCL and POS, but BPF sites have different community composition
compared to the other two sites.

The table above shows the species most representative of the community
differences used to make the above classifications. These species are
the top 10th percentile of ranked variable importance (mean decrease in
Gini score, a measure of the total decrease in node impurities from
splitting on the variable, averaged over all trees).

### NMDS by Site figure (include this)

![](composition_analyses_files/figure-gfm/nmds_all_sites_year-1.png)<!-- -->
**Variation in community composition across sites.** Bee species are
plotted on the first two axes of a three-dimensional non-metric
multidimensional scaling ordination of the 58 combinations of station
(subsite) and year, across the three sites. Small points are the
individual station/year combinations. Large points are the centroids of
the three sites. Ellipses are 95% confidence intervals around the site
centroids. Bees species shown are the most representative (top 10th
percentile of a random forest analysis) of the compositional differences
among sites. Text size of the labels is proportional to variable
importance score (mean decrease in Gini score).

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
     [1] knitr_1.47           caret_6.0-94         randomForest_4.7-1.1
     [4] vegan_2.6-6.1        lattice_0.20-45      permute_0.9-7       
     [7] cowplot_1.1.3        lubridate_1.9.3      forcats_1.0.0       
    [10] stringr_1.5.1        dplyr_1.1.4          purrr_1.0.2         
    [13] readr_2.1.5          tidyr_1.3.1          tibble_3.2.1        
    [16] ggplot2_3.5.1        tidyverse_2.0.0     

    loaded via a namespace (and not attached):
     [1] splines_4.2.3        foreach_1.5.2        prodlim_2023.08.28  
     [4] highr_0.11           stats4_4.2.3         ggrepel_0.9.5       
     [7] yaml_2.3.8           globals_0.16.3       ipred_0.9-14        
    [10] pillar_1.9.0         glue_1.7.0           pROC_1.18.5         
    [13] digest_0.6.35        RColorBrewer_1.1-3   hardhat_1.4.0       
    [16] colorspace_2.1-0     recipes_1.0.10       htmltools_0.5.8.1   
    [19] Matrix_1.5-3         plyr_1.8.9           timeDate_4032.109   
    [22] pkgconfig_2.0.3      listenv_0.9.1        scales_1.3.0        
    [25] gower_1.0.1          lava_1.8.0           tzdb_0.4.0          
    [28] proxy_0.4-27         timechange_0.3.0     mgcv_1.8-42         
    [31] farver_2.1.2         generics_0.1.3       withr_3.0.0         
    [34] nnet_7.3-18          cli_3.6.2            survival_3.5-3      
    [37] magrittr_2.0.3       evaluate_0.24.0      fansi_1.0.6         
    [40] future_1.33.2        parallelly_1.37.1    nlme_3.1-162        
    [43] MASS_7.3-58.2        class_7.3-21         tools_4.2.3         
    [46] data.table_1.15.4    hms_1.1.3            lifecycle_1.0.4     
    [49] munsell_0.5.1        cluster_2.1.4        e1071_1.7-14        
    [52] compiler_4.2.3       rlang_1.1.4          grid_4.2.3          
    [55] iterators_1.0.14     rstudioapi_0.16.0    labeling_0.4.3      
    [58] rmarkdown_2.27       gtable_0.3.5         ModelMetrics_1.2.2.2
    [61] codetools_0.2-19     reshape2_1.4.4       R6_2.5.1            
    [64] fastmap_1.2.0        future.apply_1.11.2  utf8_1.2.4          
    [67] rprojroot_2.0.4      stringi_1.8.4        parallel_4.2.3      
    [70] Rcpp_1.0.12          vctrs_0.6.5          rpart_4.1.23        
    [73] tidyselect_1.2.1     xfun_0.44           
