R cheatsheet
================

definitions
-----------

**R** - software environment/language

**RStudio** - integrated development environment (IDE), requires R to run. Available as desktop or server. Often, R and RStudio are referred to interchangeably.

**RStudio Desktop** - version of RStudio installed on your local machine

**RStudio Server** - browser based interface to a version of RStudio running remotely: <https://rstudio.nhsnss.scot.nhs.uk/auth-sign-in>

**script** - text file containing R code, similar to SPSS syntax, ends in `.R`

**project** - file that keeps all files (e.g. data, scripts, output etc) associated with an analysis all together - ends in `.Rproj`. Using projects also sets your working directory to the location of the project file.

**variable** - an object that stores data - appears in `environment`

**function** - commands to perform a task e.g. read in data, save a file, add a new column, summarize data. R has many functions built in - often referred to as base R. More functions can be added by loading `packages`. You can also write your own functions. The structure of a function is always: `function()` e.g. `read_csv()`, where `read_csv` is the function name.

**base R** - functions that come built in with R e.g. `sum()`, `mean()`

**argument** - functions generally require arguments. Usually this is the object or variable to operate on (e.g. data) and any other options that can be set (e.g if you are sorting something, do you want it to ascend or descend?). Arguments are inside the brackets when calling a function - `function(argument1, argument2)`

**package** - a collection of functions - e.g. `dplyr` contains many functions for working with data, `ggplot` has functions for plotting.

useful functions in R
---------------------

**`?function`** - get help about a function e.g. `?dim` or `?sum`

**`<-`** - the assign function. This reads from right to left - whatever is on the right hand side is assigned to the object on the left hand side. This is how you create objects e.g. `x <- 10` assigns 10 to the object `x`, which can then be used in calculations, functions etc.

**`c()`** - combine or concatenate multiple objects/inputs into a vector of objects e.g `x <- c(1, 2, 3, 4, 5)`

**`str()`** - display the structure of an object - e.g. try: `str(iris)`

**`dim()`** - display the dimensions (number of rows and columns) of an object - e.g. try: `dim(iris)`

**`ncol()`** - display the columns of an object - e.g. try: `ncol(iris)`

**`nrow()`** - display the columns of an object - e.g. try: `nrow(iris)`

**`colnames()`** - display the column names of an object - e.g. try: `colnames(iris)`

**`class()`** - what type is the object? - e.g. try: `class("a")`, `class(1)`, `class(TRUE)`, `class(iris)`

**`length()`** - length of an object - e.g. try: `length(c(1, 2, 3))`

**`rm()`** - remove an object from the environment - e.g. `rm(x)`. can remove multiple e.g. `rm(x, y, z)`

**`getwd()`** - show working directory - where is R looking? Note: no argument required, just empty brackets.

**`setwd()`** - change working directory e.g. `setwd("path/to/directory")`. Not required if using projects!

**`list.files()`** - show files in working directory. Note: no argument required, just empty brackets.

**`install.packages()`** - install external packages - needs quote marks - e.g. `install.packages("dplyr")`

**`library()`** - load an installed package - doesn't need quote marks - e.g. `library(dplyr)`

object/variable type in R
-------------------------

Note: you can test for many of these using `is.` (e.g. `is.character("abc")`, `is.factor(iris$Species)`)

**character** - used for text (strings, e.g. name) or numbers that should be treated as strings (e.g. CHI number, NHS number)

**double** - stores numbers

**date** - dates are stored as unambiguous format (YYYY-MM-DD)

**factor** - can contain only predefined values, used to store categorical data. The available values are referred to as levels e.g. health boards have a predefined and fixed number of levels.

**logical** - TRUE/FALSE

**`NA`** - Not Available, used to represent missing values

data structures in R
--------------------

Note: you can test for many of these structures using `is.` (e.g. `is.data.frame(iris)`, `is.vector(c(1, 2, 3))`)

**vector** - one dimensional collection of elements, all elements must be the same type - e.g. `c(1, 2, 3)`, `c("this", "is", "a", "vector")`

**dataframe** - most common way of storing data in R. Two dimensional (rows and columns) collection of elements, each variable must contain the same type of element (e.g numeric) but variables can be different from each other - e.g. one variable of dates, one of characters, one of logical.

**tibble** - special `tidyverse` form of a dataframe, functionally very similar but has some improvements in e.g. printing (compare `iris` vs `as_tibble(iris)`). `read_csv()` will return a `tibble`, `read.csv()` from base R will return a `dataframe`

**list** - a vector, but very flexible as the elements can be anything, including other lists. `dataframes` are lists of equal length vectors.

**matrix** - two dimensional collection of elements, all of the same type (e.g. numeric)
