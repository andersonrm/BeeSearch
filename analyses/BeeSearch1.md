BeeSearch initial
================
Dr. Riley M. Anderson
September 10, 2024

  

- [Overview](#overview)
  - [Summary of Results](#summary-of-results)
- [How many species do we have at each location? How much variability is
  there in
  richness?](#how-many-species-do-we-have-at-each-location-how-much-variability-is-there-in-richness)
- [Sex ratio in trap vs. netting collection
  method:](#sex-ratio-in-trap-vs-netting-collection-method)
- [Species accumulation curves](#species-accumulation-curves)
- [Chao indices](#chao-indices)
- [Does community composition change across seasons, sites, or
  years?](#does-community-composition-change-across-seasons-sites-or-years)
  - [Across seasons: (I don’t think we should include
    this)](#across-seasons-i-dont-think-we-should-include-this)
  - [Across sites](#across-sites)
    - [Site classification by species composition (Random
      Forest)](#site-classification-by-species-composition-random-forest)
    - [NMDS by Site figure (include
      this)](#nmds-by-site-figure-include-this)
  - [Across years (I don’t think we should include
    this)](#across-years-i-dont-think-we-should-include-this)
- [POS 2017 Changes over seasons (This is not
  interesting)](#pos-2017-changes-over-seasons-this-is-not-interesting)
- [What is the turnover of species within sub-sites within
  years?](#what-is-the-turnover-of-species-within-sub-sites-within-years)
  - [POS](#pos)
  - [SCL](#scl)
  - [BPF](#bpf)
- [Is there greater overall diversity at SCL vs POS vs
  PBF?](#is-there-greater-overall-diversity-at-scl-vs-pos-vs-pbf)
  - [Session Information](#session-information)

## Overview

What is this analysis about?

### Summary of Results

- 

# How many species do we have at each location? How much variability is there in richness?

![](BeeSearch1_files/figure-gfm/Q1-1.png)<!-- --> Raw species counts
(excluding incompatible year/stations with altered sampling efforts).
Males and females are included. Collection method includes both trap and
net.

# Sex ratio in trap vs. netting collection method:

- Ratios \> 1 represent male bias

- Ratios \< 1 represent female bias

- Overall:

| Collection.Method | Male | female | male | sex_ratio |
|:------------------|-----:|-------:|-----:|----------:|
| T                 |    2 |   5278 | 1281 |      0.24 |
| N                 |    0 |    676 |  401 |      0.59 |

- By site:

| Collection.Method | Site | Male | female | male | sex_ratio |
|:------------------|:-----|-----:|-------:|-----:|----------:|
| T                 | SCL  |    2 |    920 |  300 |      0.33 |
| N                 | BPF  |    0 |     61 |   92 |      1.51 |
| N                 | POS  |    0 |    563 |  252 |      0.45 |
| N                 | SCL  |    0 |     52 |   57 |      1.10 |
| T                 | BPF  |    0 |    745 |  274 |      0.37 |
| T                 | POS  |    0 |   3613 |  707 |      0.20 |

![](BeeSearch1_files/figure-gfm/sex_ratios_by_site-1.png)<!-- --> **Sex
ratios of bees by site and collection method.** Points above the dashed
line represent male bias, whereas point below represent female bias.

- By season:

| Collection.Method | ToY   | Male | female | male | sex_ratio |
|:------------------|:------|-----:|-------:|-----:|----------:|
| T                 | mid   |    2 |   2583 |  612 |      0.24 |
| N                 | early |    0 |    128 |   81 |      0.63 |
| N                 | late  |    0 |    191 |  196 |      1.03 |
| N                 | mid   |    0 |    357 |  124 |      0.35 |
| T                 | early |    0 |   1469 |  315 |      0.21 |
| T                 | late  |    0 |   1226 |  354 |      0.29 |

- By season and site:

| Collection.Method | ToY   | Site | Male | female | male | sex_ratio |
|:------------------|:------|:-----|-----:|-------:|-----:|----------:|
| T                 | mid   | SCL  |    2 |    382 |  113 |      0.30 |
| N                 | early | BPF  |    0 |     15 |   59 |      3.93 |
| N                 | early | POS  |    0 |    113 |   22 |      0.19 |
| N                 | late  | BPF  |    0 |     28 |   22 |      0.79 |
| N                 | late  | POS  |    0 |    163 |  172 |      1.06 |
| N                 | mid   | BPF  |    0 |     18 |   11 |      0.61 |
| N                 | mid   | POS  |    0 |    287 |   58 |      0.20 |
| N                 | mid   | SCL  |    0 |     52 |   55 |      1.06 |
| T                 | early | BPF  |    0 |    146 |   31 |      0.21 |
| T                 | early | POS  |    0 |    997 |  144 |      0.14 |
| T                 | early | SCL  |    0 |    326 |  140 |      0.43 |
| T                 | late  | BPF  |    0 |    190 |  108 |      0.57 |
| T                 | late  | POS  |    0 |    824 |  199 |      0.24 |
| T                 | late  | SCL  |    0 |    212 |   47 |      0.22 |
| T                 | mid   | BPF  |    0 |    409 |  135 |      0.33 |
| T                 | mid   | POS  |    0 |   1792 |  364 |      0.20 |
| N                 | late  | SCL  |    0 |      0 |    2 |       Inf |

![](BeeSearch1_files/figure-gfm/sex_ratios_by_season_and_site-1.png)<!-- -->
**Sex ratios of bees collected by either net or trap across the sampling
season.** Points above the dashed line represent male bias, whereas
point below represent female bias. Early season (late March - mid May),
mid season (mid May to mid July), and late season (mid July - late
September) time windows in the sampling effort are shown. Large solid
points are sex ratios calculated at the season level. Small open points
are sex ratios calculated at the sub-site level within each season.
Small points are spread horizontally for visual clarity.

# Species accumulation curves

![](BeeSearch1_files/figure-gfm/SAC_figure-1.png)<!-- -->

# Chao indices

From Anne Chao 1989:

Chao1 minimum species richness is defined non-parametrically as:

![S\_{est} = S\_{obs} + f\_{1}^{2}/(2f\_{2})](https://latex.codecogs.com/png.latex?S_%7Best%7D%20%3D%20S_%7Bobs%7D%20%2B%20f_%7B1%7D%5E%7B2%7D%2F%282f_%7B2%7D%29 "S_{est} = S_{obs} + f_{1}^{2}/(2f_{2})")

- Chao indices by site

|  chao1 | Site |
|-------:|:-----|
|  92.79 | BPF  |
| 108.46 | POS  |
| 104.35 | SCL  |

- Chao indices by site and season

|  chao1 | Site | Season |
|-------:|:-----|:-------|
|  44.08 | BPF  | early  |
|  87.00 | BPF  | late   |
|  78.22 | BPF  | mid    |
|  78.29 | POS  | early  |
| 105.50 | POS  | late   |
|  89.00 | POS  | mid    |
|  97.79 | SCL  | early  |
|  56.12 | SCL  | late   |
|  84.33 | SCL  | mid    |

![](BeeSearch1_files/figure-gfm/chao_site_season-1.png)<!-- -->

**Overall Chao1 minimum species richness across the sampling season.**
Estimated species richness in early (late March - mid May), mid (mid May
to mid July), and late (mid July - late September) time windows in the
sampling effort. Richness across sites converge in the mid-summer.

- Chao indices by station

| chao1 | Station |
|------:|:--------|
| 37.33 | BPF1    |
| 62.17 | BPF2    |
| 32.08 | BPF3    |
| 86.25 | BPF4    |
| 49.00 | BPF5    |
| 43.10 | BPF6    |
| 39.56 | BPF7    |
| 28.17 | BPF8    |
| 78.57 | POS1    |
| 18.67 | POS10   |
| 37.50 | POS11   |
| 53.12 | POS12   |
| 36.17 | POS13   |
| 96.00 | POS2    |
| 48.08 | POS20   |
| 51.80 | POS21   |
| 51.12 | POS22   |
| 51.17 | POS23   |
| 44.67 | POS24   |
| 51.90 | POS25   |
| 73.14 | POS3    |
| 50.29 | POS4    |
| 77.00 | POS5    |
| 41.08 | POS6    |
| 33.33 | POS7    |
| 75.40 | POS8    |
| 51.12 | POS9    |
| 87.79 | SCL1    |
| 84.12 | SCL2    |
| 58.12 | SCL3    |
| 74.56 | SCL4    |
| 35.50 | SCL5    |

- Chao indices by station and year

|  chao1 | Station | Year |
|-------:|:--------|:-----|
|  53.25 | BPF1    | 2018 |
|  56.17 | BPF1    | 2019 |
|  41.12 | BPF2    | 2018 |
|  41.67 | BPF2    | 2019 |
|  32.00 | BPF3    | 2018 |
|  34.50 | BPF3    | 2019 |
|  25.33 | BPF4    | 2018 |
|  44.12 | BPF4    | 2019 |
|  30.10 | BPF5    | 2018 |
|  48.90 | BPF5    | 2019 |
|  23.90 | BPF6    | 2018 |
|  68.25 | BPF6    | 2019 |
|  39.56 | BPF7    | 2019 |
|  28.17 | BPF8    | 2019 |
|  18.67 | POS10   | 2017 |
|  37.50 | POS11   | 2017 |
|  30.17 | POS12   | 2017 |
|  44.50 | POS12   | 2019 |
|  36.17 | POS13   | 2018 |
|  40.00 | POS1    | 2015 |
|  44.00 | POS1    | 2016 |
|  55.60 | POS1    | 2019 |
|  48.08 | POS20   | 2018 |
|  51.80 | POS21   | 2019 |
|  51.12 | POS22   | 2018 |
|  51.17 | POS23   | 2018 |
|  44.67 | POS24   | 2018 |
|  51.90 | POS25   | 2019 |
|  46.08 | POS2    | 2015 |
|  86.17 | POS2    | 2016 |
|  36.79 | POS2    | 2019 |
|  45.67 | POS3    | 2015 |
|  45.40 | POS3    | 2016 |
|  52.00 | POS3    | 2018 |
|  45.25 | POS4    | 2016 |
|  40.14 | POS4    | 2018 |
|  72.25 | POS5    | 2017 |
|  49.25 | POS5    | 2019 |
|  50.00 | POS6    | 2017 |
|  35.60 | POS6    | 2019 |
|  33.33 | POS7    | 2017 |
|  41.12 | POS8    | 2017 |
|  62.12 | POS8    | 2019 |
|  56.25 | POS9    | 2017 |
|  43.50 | POS9    | 2018 |
|  32.00 | SCL1    | 2014 |
|  59.90 | SCL1    | 2015 |
|  96.50 | SCL1    | 2016 |
|  43.00 | SCL2    | 2014 |
|  61.00 | SCL2    | 2015 |
|  40.10 | SCL2    | 2016 |
|  14.50 | SCL3    | 2014 |
|  51.00 | SCL3    | 2015 |
|  50.00 | SCL3    | 2016 |
|  22.90 | SCL4    | 2014 |
| 111.00 | SCL4    | 2015 |
|  39.50 | SCL4    | 2016 |
|  35.50 | SCL5    | 2016 |

![](BeeSearch1_files/figure-gfm/chao_station_year-1.png)<!-- -->

**Species richness across sites and sampling years** Points are mean
Chao1 estimated species richness, triangles are raw species counts at
each substation within each site. Chao richness estimates are lifted by
an additive parameter that accounts for rare species likely missed in
the sampling. The data exclude some morphospecies (see methods), and all
net caught records.

# Does community composition change across seasons, sites, or years?

## Across seasons: (I don’t think we should include this)

![](BeeSearch1_files/figure-gfm/ndms_fig_seasons-1.png)<!-- -->
**Community composition across time of season.** Strong overlap of
composition across the early, mid, and late season sampling (PERMANOVA:
F = 0.71, 0.8). Data include all compatible stations across all years.

## Across sites

    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df   Sum Sq   Mean Sq      F N.Perm Pr(>F)  
    ## Groups     5 0.092738 0.0185477 3.2641    999  0.014 *
    ## Residuals 52 0.295478 0.0056823                       
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df   Sum Sq   Mean Sq      F N.Perm Pr(>F)
    ## Groups     2 0.007355 0.0036775 0.6595    999  0.511
    ## Residuals 55 0.306670 0.0055758

### Site classification by species composition (Random Forest)

    ## Random Forest 
    ## 
    ##  58 samples
    ## 135 predictors
    ##   3 classes: 'BPF', 'POS', 'SCL' 
    ## 
    ## No pre-processing
    ## Resampling: Bootstrapped (25 reps) 
    ## Summary of sample sizes: 58, 58, 58, 58, 58, 58, ... 
    ## Resampling results across tuning parameters:
    ## 
    ##   mtry  Accuracy   Kappa    
    ##     2   0.7080346  0.4521823
    ##    68   0.7944142  0.6475608
    ##   135   0.7528614  0.5808422
    ## 
    ## Accuracy was used to select the optimal model using the largest value.
    ## The final value used for the model was mtry = 68.
    ## 
    ## Call:
    ##  randomForest(x = select(rf_matrix, -Year, -Station, -StationYear,      -Site), y = rf_matrix$Site, mtry = 68, importance = T, nPerm = 999,      proximity = T) 
    ##                Type of random forest: classification
    ##                      Number of trees: 500
    ## No. of variables tried at each split: 68
    ## 
    ##         OOB estimate of  error rate: 17.24%
    ## Confusion matrix:
    ##     BPF POS SCL class.error
    ## BPF  14   0   0  0.00000000
    ## POS   0  28   3  0.09677419
    ## SCL   0   7   6  0.53846154

|                          |    BPF |    POS |    SCL | MeanDecreaseAccuracy | MeanDecreaseGini |
|:-------------------------|-------:|-------:|-------:|---------------------:|-----------------:|
| Halictus tripartitus     |  8.362 |  9.695 |  0.988 |               10.294 |            2.452 |
| Agapostemon texanus      | 10.509 |  9.212 | -1.232 |               10.833 |            2.446 |
| Osmia albolateralis      |  7.043 |  8.378 |  3.458 |                9.589 |            2.384 |
| Bombus flavifrons        |  7.183 |  2.384 |  9.025 |                8.806 |            2.022 |
| Bombus fervidus          |  9.693 |  4.204 |  0.519 |                8.250 |            1.940 |
| Apis mellifera           |  8.265 |  3.486 | -0.401 |                7.720 |            1.369 |
| Bombus melanopygus       |  7.651 |  5.063 |  4.805 |                8.210 |            1.350 |
| Halictus confusus        |  7.552 | -1.029 |  4.186 |                6.801 |            1.191 |
| Megachile melanophaea    |  4.461 |  3.472 |  1.687 |                4.956 |            0.892 |
| Melissodes rivalis       |  0.636 |  3.683 |  0.971 |                3.265 |            0.879 |
| Bombus vosnesenskii      |  3.613 |  1.362 |  2.388 |                4.202 |            0.766 |
| Ceratina acantha         |  4.597 | -0.001 |  0.348 |                3.542 |            0.742 |
| Melissodes microsticta   |  1.804 |  1.125 | -1.510 |                0.681 |            0.739 |
| Lasioglossum incompletum |  5.689 |  0.859 | -1.321 |                3.933 |            0.693 |

![](BeeSearch1_files/figure-gfm/random_forest_sites-1.png)<!-- -->

**Random Forest classification of site by species composition.** The
model was tuned without pre-processing. Bootstrapped resampling used 25
replicates. Overall model accuracy was 82%. The model clearly delineated
the BPF sites with 0.0 class error. Similarly, POS sites were near
perfect with 0.032 class error. However, the SCL sites were less
accurately classified (0.385 class error), with (5/13) identified as
POS. This lends further support to the NMDS figure below, species
composition is very similar across SCL and POS, but BPF sites have
different community composition compared to the other two sites.

The table above shows the species most representative of the community
differences used to make the above classifications. These species are
the top 10th percentile of ranked variable importance (mean decrease in
Gini score).

### NMDS by Site figure (include this)

![](BeeSearch1_files/figure-gfm/nmds_all_sites_year-1.png)<!-- -->
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

## Across years (I don’t think we should include this)

![](BeeSearch1_files/figure-gfm/nmds_all_year-1.png)<!-- --> **Community
composition across years.** Most years have strong overlap of
composition but the *year* term is highly significant (PERMANOVA: F =
1.74, *P* = 0.001). However, the only site in 2014 is SCL and the 2018
and 2019 years are heavily influenced by the BPF data. Essentially, the
information in *years* is not sufficiently distinct from the information
in *sites* and including *year* in the model is not informative. This is
also the likely cause of the violation of homogeneity of multivariate
dispersions for the *year* term but not the *site* term.

# POS 2017 Changes over seasons (This is not interesting)

    ## Permutation test for adonis under reduced model
    ## Terms added sequentially (first to last)
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## adonis2(formula = nmds2017dist ~ meta2017$ToY, method = "bray")
    ##              Df SumOfSqs      R2     F Pr(>F)  
    ## meta2017$ToY  2   0.7636 0.12119 1.448  0.047 *
    ## Residual     21   5.5371 0.87881               
    ## Total        23   6.3007 1.00000               
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Permutation test for homogeneity of multivariate dispersions
    ## Permutation: free
    ## Number of permutations: 999
    ## 
    ## Response: Distances
    ##           Df   Sum Sq   Mean Sq      F N.Perm Pr(>F)  
    ## Groups     2 0.016515 0.0082573 3.3301    999  0.054 .
    ## Residuals 21 0.052071 0.0024796                       
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Within the Port of Seattle sites in 2017 and only 2017, species
composition changes significantly throughout the season with distinct
groups of species in early, mid, and late season sampling. **However,
this model violates homogeneity of multivariate dispersions.**

![](BeeSearch1_files/figure-gfm/nmds2017_plot-1.png)<!-- -->
**Non-metric multidimensional scaling of bee species in Port of Seattle
in 2017.** Points are sub-sites within the port of Seattle in 2017. They
are separated by time of season with the 8 sub sites at the early season
in red, the same 8 sub sites at the middle season in blue, and the same
8 sub sites at the end of the season in green. The NMDS space represents
total bee species composition and the labels are specific bee species
and their position in NMDS space. Large points are the centroids (means)
of the points in NMDS space. Ellipses are 95% confidence intervals
around the centroids.

# What is the turnover of species within sub-sites within years?

### POS

![](BeeSearch1_files/figure-gfm/POS_beta_div_across_sites_within_years-1.png)<!-- -->

### SCL

![](BeeSearch1_files/figure-gfm/SCL_beta_div_across_sites_within_years-1.png)<!-- -->

### BPF

![](BeeSearch1_files/figure-gfm/BPF_beta_div_across_sites_within_years-1.png)<!-- -->

# Is there greater overall diversity at SCL vs POS vs PBF?

| Site | Shannon | Simpson | InvSimpson | UnbiasedSimpson | FisherAlpha |
|:-----|--------:|--------:|-----------:|----------------:|------------:|
| POS  |    3.57 |    0.95 |      22.14 |            0.95 |       26.49 |
| BPF  |    3.51 |    0.96 |      22.35 |            0.96 |       19.71 |
| SCL  |    3.48 |    0.95 |      20.40 |            0.95 |       22.73 |

Diversity is similar across all 3 sites.

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
     [1] caret_6.0-94         randomForest_4.7-1.1 geosphere_1.5-18    
     [4] fossil_0.4.0         shapefiles_0.7.2     foreign_0.8-84      
     [7] maps_3.4.2           sp_2.1-4             knitr_1.47          
    [10] adespatial_0.3-23    vegan_2.6-6.1        lattice_0.20-45     
    [13] permute_0.9-7        cowplot_1.1.3        lubridate_1.9.3     
    [16] forcats_1.0.0        stringr_1.5.1        dplyr_1.1.4         
    [19] purrr_1.0.2          readr_2.1.5          tidyr_1.3.1         
    [22] tibble_3.2.1         ggplot2_3.5.1        tidyverse_2.0.0     

    loaded via a namespace (and not attached):
      [1] colorspace_2.1-0     seqinr_4.2-36        deldir_2.0-4        
      [4] class_7.3-21         rprojroot_2.0.4      rstudioapi_0.16.0   
      [7] proxy_0.4-27         farver_2.1.2         listenv_0.9.1       
     [10] ggrepel_0.9.5        prodlim_2023.08.28   fansi_1.0.6         
     [13] xml2_1.3.6           codetools_0.2-19     splines_4.2.3       
     [16] ade4_1.7-22          pROC_1.18.5          phylobase_0.8.12    
     [19] cluster_2.1.4        png_0.1-8            shiny_1.8.1.1       
     [22] compiler_4.2.3       httr_1.4.7           adegraphics_1.0-21  
     [25] Matrix_1.5-3         fastmap_1.2.0        cli_3.6.2           
     [28] later_1.3.2          s2_1.1.6             htmltools_0.5.8.1   
     [31] prettyunits_1.2.0    tools_4.2.3          igraph_2.0.3        
     [34] gtable_0.3.5         glue_1.7.0           reshape2_1.4.4      
     [37] wk_0.9.1             Rcpp_1.0.12          vctrs_0.6.5         
     [40] spdep_1.3-5          ape_5.8              nlme_3.1-162        
     [43] iterators_1.0.14     timeDate_4032.109    gower_1.0.1         
     [46] xfun_0.44            globals_0.16.3       adephylo_1.1-16     
     [49] timechange_0.3.0     mime_0.12            lifecycle_1.0.4     
     [52] XML_3.99-0.16.1      future_1.33.2        MASS_7.3-58.2       
     [55] scales_1.3.0         ipred_0.9-14         hms_1.1.3           
     [58] promises_1.3.0       parallel_4.2.3       RColorBrewer_1.1-3  
     [61] yaml_2.3.8           rpart_4.1.23         latticeExtra_0.6-30 
     [64] stringi_1.8.4        highr_0.11           foreach_1.5.2       
     [67] e1071_1.7-14         hardhat_1.4.0        boot_1.3-28.1       
     [70] lava_1.8.0           spData_2.3.1         rlang_1.1.4         
     [73] pkgconfig_2.0.3      rncl_0.8.7           evaluate_0.24.0     
     [76] sf_1.0-16            labeling_0.4.3       recipes_1.0.10      
     [79] tidyselect_1.2.1     parallelly_1.37.1    plyr_1.8.9          
     [82] magrittr_2.0.3       R6_2.5.1             generics_0.1.3      
     [85] DBI_1.2.3            pillar_1.9.0         withr_3.0.0         
     [88] mgcv_1.8-42          units_0.8-5          nnet_7.3-18         
     [91] survival_3.5-3       future.apply_1.11.2  crayon_1.5.2        
     [94] uuid_1.2-0           interp_1.1-6         KernSmooth_2.23-20  
     [97] utf8_1.2.4           tzdb_0.4.0           rmarkdown_2.27      
    [100] jpeg_0.1-10          progress_1.2.3       RNeXML_2.4.11       
    [103] adegenet_2.1.10      grid_4.2.3           data.table_1.15.4   
    [106] ModelMetrics_1.2.2.2 digest_0.6.35        classInt_0.4-10     
    [109] xtable_1.8-4         httpuv_1.6.15        stats4_4.2.3        
    [112] munsell_0.5.1       
