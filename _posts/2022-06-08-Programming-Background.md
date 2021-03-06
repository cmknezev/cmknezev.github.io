Programming Background
================

## R v. Other Programming Languages

Coming into this course, I had previous programming experience with the
following programs/softwares: R, SAS, and SQL. I am also learning Python
at the same time as I am taking this course. Personally, R is my
favorite of these languages that I am familiar with. One of the main
reasons is that the RStudio interface is the best of any interface I’ve
used. It displays a ton of helpful information, but in such a way that
it is not overwhelming, and everything feels very well organized.
Additionally, I like that there are a myriad of packages available, most
of which are pretty easy to use. Finally, I think that the syntax of R
is simple once you get used to it. Something I miss about SAS is that I
found it to be easier to clean and manipulate data than in R. In
particular, I found it easier to detect problems in the dataset or
improper data points using SAS. Although as I become more experienced
with tidyverse/dplyr, I think I’ll come to find that both languages will
be about the same level of difficulty. I found R to be neither easy nor
difficult to learn. Firstly, the syntax is relatively simple, which
makes picking up the language easy to begin with. However, the
availability of so many packages can be a double-edged sword. On the one
hand, having so many packages at your disposal means there is most
likely a way to easily do what you’re trying to do. On the other hand,
it can be hard to sift through the different options and determine which
is the best for what you need (i.e., do I use base R or ggplot for this
graph?). As an aside, it was easier for me to motivate myself to learn R
due to the wide variety of baseball datasets that can be easily
implemented into R. As a big baseball fan it made experimenting with the
language more fun and interesting.

## R Markdown Output

``` r
# setup code chunk 
knitr::opts_chunk$set(fig.path = "../images/")
```

``` r
plot(iris)
```

![](../images/unnamed-chunk-4-1.png)<!-- -->

``` r
library(rmarkdown)

rmarkdown::render(input = "2022-06-08-Programming-Background.Rmd", 
                  output_format = "github_document", 
                  output_dir = "../_posts/",
                  output_options = list(html_preview = FALSE)
                  )
```
