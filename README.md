# ZachMeadway.github.io
## OCLC vs Goodreads
How do popular ratings compare to this top500 list? Do either of the ratings 
(OCLC and Goodreads) have a gender bais. First, let's see if there is a correlation between the OCLC rank and Goodreads rating!


### Does the average goodreads rating correlate to a higher OCLC ranking?


```{r results='hide', echo=FALSE, message=FALSE, warning=FALSE}
library(ggplot2)
library(tidyverse)
```

```{r, echo=FALSE, message=FALSE, warning=FALSE}
top500 <- read.csv("library_top_500.csv")
top500[419, "author_gender"] <- "male"
grRating_G <- ggplot(top500, aes(y=gr_avg_rating, x =top_500_rank))
grRating_G + geom_point() + geom_smooth(method = 'lm')
```
