Visualize Data
================

``` r
#mpg
```

## Your Turn 1

Run the code on the slide to make a graph. Pay strict attention to
spelling, capitalization, and parentheses\!

``` r
ggplot(data = mpg) +
  geom_point (mapping = aes(x = displ, y = hwy))
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

## Your Turn 2

Replace this scatterplot with one that draws boxplots. Use the
cheatsheet. Try your best guess.

``` r
ggplot(data = mpg) +
 geom_boxplot(mapping = aes(x = class, y = hwy))
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

## Your Turn 3

Make a histogram of the `hwy` variable from `mpg`. Hint: do not supply a
y variable.

``` r
ggplot(data=mpg) +
  geom_histogram(mapping = aes(hwy))
```

    `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

## Your Turn 4

Use the help page for `geom_histogram` to make the bins 2 units wide.

``` r
ggplot(data=mpg) +
  geom_histogram(mapping = aes(hwy), binwidth = 2)
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

## Your Turn 5

Add `color`, `size`, `alpha`, and `shape` aesthetics to your graph.
Experiment.

``` r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy, color = class))
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy, size = class))
```

    Warning: Using size for a discrete variable is not advised.

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

``` r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy, shape = class))
```

    Warning: The shape palette can deal with a maximum of 6 discrete values because
    more than 6 becomes difficult to discriminate; you have 7. Consider
    specifying shapes manually if you must have them.

    Warning: Removed 62 rows containing missing values (geom_point).

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

``` r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy, alpha = class))
```

    Warning: Using alpha for a discrete variable is not advised.

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->
\#\# Help Me

What do `facet_grid()` and `facet_wrap()` do? (run the code, interpret,
convince your group)

``` r
# Makes a plot that the commands below will modify
q <- ggplot(mpg) + geom_point(aes(x = displ, y = hwy))

q + facet_grid(. ~ cyl)
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

``` r
q + facet_grid(drv ~ .)
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-10-2.png)<!-- -->

``` r
q + facet_grid(drv ~ cyl)
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-10-3.png)<!-- -->

``` r
q + facet_wrap(~ class)
```

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-10-4.png)<!-- -->

## Your Turn 6

Make a bar chart `class` colored by `class`. Use the help page for
`geom_bar` to choose a “color” aesthetic for class.

## Quiz

What will this code do?

``` r
ggplot(mpg) + 
  geom_point(aes(displ, hwy)) +
  geom_smooth(aes(displ, hwy))
```

    `geom_smooth()` using method = 'loess' and formula 'y ~ x'

![](Week-4-Visualize-Exercises_files/figure-gfm/unnamed-chunk-12-1.png)<!-- -->

-----

# Take aways

You can use this code template to make thousands of graphs with
**ggplot2**.

``` r
ggplot(data = <DATA>) +
  <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))
```
