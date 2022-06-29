2022-06-29-Programming-in-R
================
Collin Knezevich

I think the coolest thing we have learned about so far is the
`tidyverse` set of packages, and the concepts about programming with
them. It’s cool that these packages are powerful enough to do a wide
variety of things (data manipulation, graphing, etc.), but are still
designed with similar syntax so that they can easily be used together. I
also like having the ability to pipe functions. It makes your code very
intuitive to write and a lot easier to read.

Here is an example of what you can do using `tidyverse`. We will take
the iris dataset from R, perform some data manipulation on it, and
create a graph.

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✔ ggplot2 3.3.6     ✔ purrr   0.3.4
    ## ✔ tibble  3.1.7     ✔ dplyr   1.0.9
    ## ✔ tidyr   1.2.0     ✔ stringr 1.4.0
    ## ✔ readr   2.1.2     ✔ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
# add new variable, sort by new variable
iris <- iris %>% mutate(Sepal.Area = Sepal.Length*Sepal.Width) %>% 
  arrange(Sepal.Area)
iris
```

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width    Species Sepal.Area
    ## 1            5.0         2.0          3.5         1.0 versicolor      10.00
    ## 2            4.5         2.3          1.3         0.3     setosa      10.35
    ## 3            5.0         2.3          3.3         1.0 versicolor      11.50
    ## 4            4.9         2.4          3.3         1.0 versicolor      11.76
    ## 5            4.9         2.5          4.5         1.7  virginica      12.25
    ## 6            5.5         2.3          4.0         1.3 versicolor      12.65
    ## 7            5.1         2.5          3.0         1.1 versicolor      12.75
    ## 8            4.4         2.9          1.4         0.2     setosa      12.76
    ## 9            4.3         3.0          1.1         0.1     setosa      12.90
    ## 10           5.5         2.4          3.8         1.1 versicolor      13.20
    ## 11           5.5         2.4          3.7         1.0 versicolor      13.20
    ## 12           4.4         3.0          1.3         0.2     setosa      13.20
    ## 13           6.0         2.2          4.0         1.0 versicolor      13.20
    ## 14           6.0         2.2          5.0         1.5  virginica      13.20
    ## 15           6.2         2.2          4.5         1.5 versicolor      13.64
    ## 16           5.5         2.5          4.0         1.3 versicolor      13.75
    ## 17           5.6         2.5          3.9         1.1 versicolor      14.00
    ## 18           5.2         2.7          3.9         1.4 versicolor      14.04
    ## 19           4.4         3.2          1.3         0.2     setosa      14.08
    ## 20           5.7         2.5          5.0         2.0  virginica      14.25
    ## 21           4.6         3.1          1.5         0.2     setosa      14.26
    ## 22           5.5         2.6          4.4         1.2 versicolor      14.30
    ## 23           4.8         3.0          1.4         0.1     setosa      14.40
    ## 24           4.8         3.0          1.4         0.3     setosa      14.40
    ## 25           6.3         2.3          4.4         1.3 versicolor      14.49
    ## 26           4.9         3.0          1.4         0.2     setosa      14.70
    ## 27           4.6         3.2          1.4         0.2     setosa      14.72
    ## 28           5.7         2.6          3.5         1.0 versicolor      14.82
    ## 29           4.8         3.1          1.6         0.2     setosa      14.88
    ## 30           5.0         3.0          1.6         0.2     setosa      15.00
    ## 31           4.7         3.2          1.3         0.2     setosa      15.04
    ## 32           4.7         3.2          1.6         0.2     setosa      15.04
    ## 33           5.8         2.6          4.0         1.2 versicolor      15.08
    ## 34           5.6         2.7          4.2         1.3 versicolor      15.12
    ## 35           4.9         3.1          1.5         0.1     setosa      15.19
    ## 36           4.9         3.1          1.5         0.2     setosa      15.19
    ## 37           4.6         3.4          1.4         0.3     setosa      15.64
    ## 38           5.8         2.7          4.1         1.0 versicolor      15.66
    ## 39           5.8         2.7          3.9         1.2 versicolor      15.66
    ## 40           5.8         2.7          5.1         1.9  virginica      15.66
    ## 41           5.8         2.7          5.1         1.9  virginica      15.66
    ## 42           5.6         2.8          4.9         2.0  virginica      15.68
    ## 43           6.3         2.5          4.9         1.5 versicolor      15.75
    ## 44           6.3         2.5          5.0         1.9  virginica      15.75
    ## 45           6.1         2.6          5.6         1.4  virginica      15.86
    ## 46           5.7         2.8          4.5         1.3 versicolor      15.96
    ## 47           5.7         2.8          4.1         1.3 versicolor      15.96
    ## 48           5.0         3.2          1.2         0.2     setosa      16.00
    ## 49           6.0         2.7          5.1         1.6 versicolor      16.20
    ## 50           5.4         3.0          4.5         1.5 versicolor      16.20
    ## 51           5.6         2.9          3.6         1.3 versicolor      16.24
    ## 52           5.8         2.8          5.1         2.4  virginica      16.24
    ## 53           4.8         3.4          1.6         0.2     setosa      16.32
    ## 54           4.8         3.4          1.9         0.2     setosa      16.32
    ## 55           5.0         3.3          1.4         0.2     setosa      16.50
    ## 56           5.7         2.9          4.2         1.3 versicolor      16.53
    ## 57           4.6         3.6          1.0         0.2     setosa      16.56
    ## 58           6.7         2.5          5.8         1.8  virginica      16.75
    ## 59           5.6         3.0          4.5         1.5 versicolor      16.80
    ## 60           5.6         3.0          4.1         1.3 versicolor      16.80
    ## 61           5.1         3.3          1.7         0.5     setosa      16.83
    ## 62           5.0         3.4          1.5         0.2     setosa      17.00
    ## 63           5.0         3.4          1.6         0.4     setosa      17.00
    ## 64           6.3         2.7          4.9         1.8  virginica      17.01
    ## 65           6.1         2.8          4.0         1.3 versicolor      17.08
    ## 66           6.1         2.8          4.7         1.2 versicolor      17.08
    ## 67           5.7         3.0          4.2         1.2 versicolor      17.10
    ## 68           6.4         2.7          5.3         1.9  virginica      17.28
    ## 69           5.1         3.4          1.5         0.2     setosa      17.34
    ## 70           6.2         2.8          4.8         1.8  virginica      17.36
    ## 71           6.0         2.9          4.5         1.5 versicolor      17.40
    ## 72           5.0         3.5          1.3         0.3     setosa      17.50
    ## 73           5.0         3.5          1.6         0.6     setosa      17.50
    ## 74           6.3         2.8          5.1         1.5  virginica      17.64
    ## 75           4.9         3.6          1.4         0.1     setosa      17.64
    ## 76           5.2         3.4          1.4         0.2     setosa      17.68
    ## 77           6.1         2.9          4.7         1.4 versicolor      17.69
    ## 78           5.9         3.0          4.2         1.5 versicolor      17.70
    ## 79           5.9         3.0          5.1         1.8  virginica      17.70
    ## 80           5.1         3.5          1.4         0.2     setosa      17.85
    ## 81           5.1         3.5          1.4         0.3     setosa      17.85
    ## 82           6.4         2.8          5.6         2.1  virginica      17.92
    ## 83           6.4         2.8          5.6         2.2  virginica      17.92
    ## 84           6.2         2.9          4.3         1.3 versicolor      17.98
    ## 85           5.0         3.6          1.4         0.2     setosa      18.00
    ## 86           6.0         3.0          4.8         1.8  virginica      18.00
    ## 87           5.2         3.5          1.5         0.2     setosa      18.20
    ## 88           6.5         2.8          4.6         1.5 versicolor      18.20
    ## 89           6.3         2.9          5.6         1.8  virginica      18.27
    ## 90           6.1         3.0          4.6         1.4 versicolor      18.30
    ## 91           6.1         3.0          4.9         1.8  virginica      18.30
    ## 92           5.4         3.4          1.7         0.2     setosa      18.36
    ## 93           5.4         3.4          1.5         0.4     setosa      18.36
    ## 94           6.4         2.9          4.3         1.3 versicolor      18.56
    ## 95           5.1         3.7          1.5         0.4     setosa      18.87
    ## 96           5.9         3.2          4.8         1.8 versicolor      18.88
    ## 97           6.8         2.8          4.8         1.4 versicolor      19.04
    ## 98           6.6         2.9          4.6         1.3 versicolor      19.14
    ## 99           5.5         3.5          1.3         0.2     setosa      19.25
    ## 100          5.1         3.8          1.5         0.3     setosa      19.38
    ## 101          5.1         3.8          1.9         0.4     setosa      19.38
    ## 102          5.1         3.8          1.6         0.2     setosa      19.38
    ## 103          6.5         3.0          5.8         2.2  virginica      19.50
    ## 104          6.5         3.0          5.5         1.8  virginica      19.50
    ## 105          6.5         3.0          5.2         2.0  virginica      19.50
    ## 106          5.3         3.7          1.5         0.2     setosa      19.61
    ## 107          6.6         3.0          4.4         1.4 versicolor      19.80
    ## 108          6.4         3.1          5.5         1.8  virginica      19.84
    ## 109          5.4         3.7          1.5         0.2     setosa      19.98
    ## 110          7.7         2.6          6.9         2.3  virginica      20.02
    ## 111          6.7         3.0          5.0         1.7 versicolor      20.10
    ## 112          6.7         3.0          5.2         2.3  virginica      20.10
    ## 113          6.0         3.4          4.5         1.6 versicolor      20.40
    ## 114          6.8         3.0          5.5         2.1  virginica      20.40
    ## 115          6.4         3.2          4.5         1.5 versicolor      20.48
    ## 116          6.4         3.2          5.3         2.3  virginica      20.48
    ## 117          7.4         2.8          6.1         1.9  virginica      20.72
    ## 118          6.7         3.1          4.4         1.4 versicolor      20.77
    ## 119          6.7         3.1          4.7         1.5 versicolor      20.77
    ## 120          6.7         3.1          5.6         2.4  virginica      20.77
    ## 121          6.3         3.3          4.7         1.6 versicolor      20.79
    ## 122          6.3         3.3          6.0         2.5  virginica      20.79
    ## 123          6.5         3.2          5.1         2.0  virginica      20.80
    ## 124          5.4         3.9          1.7         0.4     setosa      21.06
    ## 125          5.4         3.9          1.3         0.4     setosa      21.06
    ## 126          6.2         3.4          5.4         2.3  virginica      21.08
    ## 127          7.3         2.9          6.3         1.8  virginica      21.17
    ## 128          7.1         3.0          5.9         2.1  virginica      21.30
    ## 129          5.2         4.1          1.5         0.1     setosa      21.32
    ## 130          6.9         3.1          4.9         1.5 versicolor      21.39
    ## 131          6.9         3.1          5.4         2.1  virginica      21.39
    ## 132          6.9         3.1          5.1         2.3  virginica      21.39
    ## 133          6.3         3.4          5.6         2.4  virginica      21.42
    ## 134          7.7         2.8          6.7         2.0  virginica      21.56
    ## 135          7.2         3.0          5.8         1.6  virginica      21.60
    ## 136          5.7         3.8          1.7         0.3     setosa      21.66
    ## 137          6.8         3.2          5.9         2.3  virginica      21.76
    ## 138          6.9         3.2          5.7         2.3  virginica      22.08
    ## 139          6.7         3.3          5.7         2.1  virginica      22.11
    ## 140          6.7         3.3          5.7         2.5  virginica      22.11
    ## 141          7.0         3.2          4.7         1.4 versicolor      22.40
    ## 142          7.6         3.0          6.6         2.1  virginica      22.80
    ## 143          7.2         3.2          6.0         1.8  virginica      23.04
    ## 144          5.5         4.2          1.4         0.2     setosa      23.10
    ## 145          7.7         3.0          6.1         2.3  virginica      23.10
    ## 146          5.8         4.0          1.2         0.2     setosa      23.20
    ## 147          5.7         4.4          1.5         0.4     setosa      25.08
    ## 148          7.2         3.6          6.1         2.5  virginica      25.92
    ## 149          7.7         3.8          6.7         2.2  virginica      29.26
    ## 150          7.9         3.8          6.4         2.0  virginica      30.02

``` r
# create graph - density plots of new variable Sepal.Area, by species 
ggplot(data = iris, aes(x = Sepal.Area)) + 
  geom_density(aes(color = Species)) + 
  labs(x = "Sepal Area", title = "Density Plots of Sepal Area by Species")
```

![](2022-06-29-Programming-in-R_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->
