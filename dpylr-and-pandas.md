---
title: "dplyr and pandas"
author: by Nicolas Lange Machado

output:
    html_document:
        keep_md: true
        toc: true

---
## Data


Model                 mpg   cyl   disp    hp   drat      wt    qsec   vs   am   gear   carb
------------------  -----  ----  -----  ----  -----  ------  ------  ---  ---  -----  -----
Mazda RX4            21.0     6    160   110   3.90   2.620   16.46    0    1      4      4
Mazda RX4 Wag        21.0     6    160   110   3.90   2.875   17.02    0    1      4      4
Datsun 710           22.8     4    108    93   3.85   2.320   18.61    1    1      4      1
Hornet 4 Drive       21.4     6    258   110   3.08   3.215   19.44    1    0      3      1
Hornet Sportabout    18.7     8    360   175   3.15   3.440   17.02    0    0      3      2


## Select {.tabset}
### R

```r
df %>% select(mpg,cyl,disp,hp,drat,wt)
# or alternatively
df %>% select(-qsec, -vs, -am, -gear, -carb)
```

### Python

```r
df[['mpg','cyl','disp','hp','drat','wt']]
# or alternatively
df.drop(['qsec', 'vs', 'am', 'gear', 'carb'], axis = 1)
```
### Output

  mpg   cyl   disp    hp   drat      wt
-----  ----  -----  ----  -----  ------
 21.0     6    160   110   3.90   2.620
 21.0     6    160   110   3.90   2.875
 22.8     4    108    93   3.85   2.320
 21.4     6    258   110   3.08   3.215
 18.7     8    360   175   3.15   3.440


## Filter {.tabset}
### R

```r
df %>% filter(hp >= 110 & carb <= 3)
```

### Python

```r
df[['mpg','cyl','disp','hp','drat','wt']]
# or alternatively
df.drop(['qsec', 'vs', 'am', 'gear', 'carb'], axis = 1)
```
### Output

Model                 mpg   cyl   disp    hp   drat      wt    qsec   vs   am   gear   carb
------------------  -----  ----  -----  ----  -----  ------  ------  ---  ---  -----  -----
Hornet 4 Drive       21.4     6    258   110   3.08   3.215   19.44    1    0      3      1
Hornet Sportabout    18.7     8    360   175   3.15   3.440   17.02    0    0      3      2
