BeeSearch ridge plots
================
Dr. Riley M. Anderson
November 19, 2024

  

- [Overview](#overview)
  - [Summary of Results](#summary-of-results)
- [Genus by time of year](#genus-by-time-of-year)
  - [Host-parasite ridges](#host-parasite-ridges)
  - [Parasite-host composite](#parasite-host-composite)
- [Species by time of year](#species-by-time-of-year)
  - [Session Information](#session-information)

## Overview

This analysis compares the abundance of genera and species throughout
the season. All analyses use the full data set. That is, counts of each
species at each time point are the cumulative sum of all sites and all
years.

### Summary of Results

18 genera had \>= 20 records and these genera are shown for the genus
level plot. Additional plots for parasite-host combinations are shown
without any record cut-off. Sample size is included in each plot.

# Genus by time of year

![](ridge_plots_files/figure-gfm/genus_ridgeplot-1.png)<!-- -->

### Host-parasite ridges

![](ridge_plots_files/figure-gfm/genus_parasite_host-1.png)<!-- -->

### Parasite-host composite

![](ridge_plots_files/figure-gfm/parasite_host_composite-1.png)<!-- -->

# Species by time of year

![](ridge_plots_files/figure-gfm/species_ridgeplot-1.png)<!-- -->

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
     [1] ggridges_0.5.6  knitr_1.47      cowplot_1.1.3   lubridate_1.9.3
     [5] forcats_1.0.0   stringr_1.5.1   dplyr_1.1.4     purrr_1.0.2    
     [9] readr_2.1.5     tidyr_1.3.1     tibble_3.2.1    ggplot2_3.5.1  
    [13] tidyverse_2.0.0

    loaded via a namespace (and not attached):
     [1] highr_0.11        pillar_1.9.0      compiler_4.2.3    tools_4.2.3      
     [5] digest_0.6.35     timechange_0.3.0  evaluate_0.24.0   lifecycle_1.0.4  
     [9] gtable_0.3.5      pkgconfig_2.0.3   rlang_1.1.4       cli_3.6.2        
    [13] rstudioapi_0.16.0 yaml_2.3.8        xfun_0.44         fastmap_1.2.0    
    [17] withr_3.0.0       generics_0.1.3    vctrs_0.6.5       hms_1.1.3        
    [21] rprojroot_2.0.4   grid_4.2.3        tidyselect_1.2.1  glue_1.7.0       
    [25] R6_2.5.1          fansi_1.0.6       rmarkdown_2.27    farver_2.1.2     
    [29] tzdb_0.4.0        magrittr_2.0.3    scales_1.3.0      htmltools_0.5.8.1
    [33] colorspace_2.1-0  labeling_0.4.3    utf8_1.2.4        stringi_1.8.4    
    [37] munsell_0.5.1    