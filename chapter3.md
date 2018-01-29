---
title       : Data Frames, Factors, and Selections
description : Practice with Data Frames, heterogeneous two-dimension data objects, including how to define factors and create selections of a data frame.

---
## Creating a data frame 

```yaml
type: TabExercise
key: 54b1efd4a9
lang: r
xp: 50
```


`@pre_exercise_code`
```{r}
```

`@sample_code`
```{r}

```

***
```yaml
type: NormalExercise
xp: 150
skills: 1
key: df0b89706d90526b3c0bbe15e400b74cbd900704
```

While matrices are appropriate for homogenous data (ie numeric data), most of data objects will contain a mixture of data classes. The basic data object in R that does this is the "data frame."

For this exercise, you will create a data frame manually, using data on earnings in 1980 from the Panel Study of Income Dynamics:

`@instructions`
Create vectors with the names and values as follows:
1. **earnings**:  0,11000,0,1600,37730
2. **age**: 36,31,34,35,45
3. **education**: hs, hs, middle, hs, masters
4. **married**:  never, divorced, never, married, married

Then combine the vectors into a data frame called **PSID**.

`@hint`
- Insert elements values in the `c()` function, in the same tense as they appear.  Each string element should be wrapped in quotation marks. 

- Use the function <code>data.frame()<\code> to combine the vectors into a data frame.

`@pre_exercise_code`
```{r}
# no pec
```

`@sample_code`
```{r}
# Create 'earnings' vector

# Create 'age' vector'

# Create 'education' vector

# Create 'married' vector

# Create the 'PSID' data frame

```

`@solution`
```{r}
# Create 'earnings' vector
earnings <- c(0,11000,0,1600,37730)

# Create 'age' vector'
age <- c(36,31,34,35,45)

# Create 'education' vector
education <-c("hs","hs","middle","hs","masters")

# Create 'married' vector
married <- c("never","divorced","never","married","married")

# Create the 'PSID' data frame
PSID <-data.frame(earnings,age,education,married)

```

`@sct`
```{r}
test_object("earnings", undefined_msg = "The earnings vector is not defined", incorrect_msg = "Be sure to write the earnings vector exactly as it appears (ie check case and spelling).")
test_object("age", undefined_msg = "The age vector is not defined", incorrect_msg = "Be sure to write the age vector exactly as it appears (ie check case and spelling).")
test_object("education", undefined_msg = "The education vector is not defined", incorrect_msg = "Be sure to write the education vector exactly as it appears (ie check case and spelling).")
test_object("married", undefined_msg = "The married vector is not defined", incorrect_msg = "Be sure to write the married vector exactly as it appears (ie check case and spelling).")
test_object("PSID", undefined_msg = "You haven't create the PSID object as a data frame.", incorrect_msg = "Be sure you are using combining the vectors in the same order that they were originally written.")

success_msg("Great job!");
```
---
## Creating and expanding a data frame

```yaml
type: NormalExercise
xp: 100
skills: 1
key: c13ea421dd078030a225f49e53a8927ce8fefbe0
```

Based off of vehicle fuel economy data from the Environment Protection Agency, the following vectors have already been crated for you:  `make`, `model`,`year`, `cylinder`, `drive`, and `mpg`.

Using these vectors, once again make a data frame and then add columns to it.


`@instructions`
- Create a dataframe called **fuelecon1** from the following vectors:  `make`, `model`, `year`, and `mpg`.

- Then add the `cyl` and `drive` vectors as additional columns to the data frame, naming the new data frame `fuelecon2`.

`@hint`
- Use the function <code>data.frame()<\code> to combine the vectors into a data frame.

- Add columns to the data frame using the <code>cbind()<\code> function.

`@pre_exercise_code`
```{r}
make <- c("Saturn","Nissan","BMW","Audi","Honda","Kia","Mazda","Lamborghini","Subaru","Volkswagen")
model <- c("Ion","Titan","Z4","S6","Civic","Optima Hybrid","RX8","Gallardo","Outback","Jetta")
year <- c(2006,2012,2005,2009,2010,2012,2006,2010,2007,2007)
cyl <- c(4,8,6,10,4,4,2,10,4,5)
drive <- c("Front-Wheel Drive","All-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","Front-Wheel Drive","Front-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","All-Wheel Drive","Front-Wheel Drive")
mpg <- c(31,17,26,19,36,39,22,20,26,28)
```

`@sample_code`
```{r}
# Create the 'fuelecon1' data frame


# Creat the 'fuelecon2' data frame by adding the vectors 'cyl' and 'drive' to 'fuelecon1'


```

`@solution`
```{r}
# Create the 'fuelecon1' data frame
fuelecon1 <-data.frame(make,model,year,mpg)

# Creat the 'fuelecon2' data frame by adding the vectors 'cyl' and 'drive' to 'fuelecon1'
fuelecon2 <-cbind(fuelecon1,cyl,drive)


```

`@sct`
```{r}
test_object("fuelecon1", undefined_msg = "Be sure to create `fuelecon1` as a dataframe.", incorrect_msg = "You have not correctly defined `fuelecon1`")
test_object("fuelecon2", undefined_msg = "Be sure to create `fuelecon2`.", incorrect_msg = "You have not correctly defined `fuelecon2`")
success_msg("Awesome!")
```

---
## Viewing the structure of a data frame

```yaml
type: NormalExercise
xp: 50
skills: 1
key: 5dd038451f
```

Similar to inspecting the class of vector, you will often want to look at how data is formatted within data frames.  


`@instructions`
Use the <code>str()</code> command to check out the structure of `fuelecon2`.

`@hint`
- The only argument of `str()` is the data object you would like to inspect!  

`@pre_exercise_code`
```{r}
make <- c("Saturn","Nissan","BMW","Audi","Honda","Kia","Mazda","Lamborghini","Subaru","Volkswagen")
model <- c("Ion","Titan","Z4","S6","Civic","Optima Hybrid","RX8","Gallardo","Outback","Jetta")
year <- c(2006,2012,2005,2009,2010,2012,2006,2010,2007,2007)
cyl <- c(4,8,6,10,4,4,2,10,4,5)
drive <- c("Front-Wheel Drive","All-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","Front-Wheel Drive","Front-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","All-Wheel Drive","Front-Wheel Drive")
mpg <- c(31,17,26,19,36,39,22,20,26,28)
fuelecon2 <-data.frame(make,model,year,mpg,cyl,drive)
fuelecon2$drive <- as.character(fuelecon2$drive)

```

`@sample_code`
```{r}
# Check out the structure of 'fuelecon2'

```

`@solution`
```{r}
# Check out the structure of 'fuelecon2'
str(fuelecon2)

```

`@sct`
```{r}
test_output_contains("str(fuelecon2)", incorrect_msg = "Have you correctly displayed the structure of `fuelecon2`? Use `str()` to do this!")
success_msg("Awesome!")
```

---
## Changing the structure of a data frame

```yaml
type: NormalExercise
xp: 50
skills: 1
key: '6725886057'
```

Did you notice that the `drive` variable in `fuelecon2` has the character class?  Since the type of drive is a categorical variable, with possible values of "Rear-Wheel Drive", "Front-Wheel Drive", and "All-Wheel Drive", we should change the data type so that it is stored as a factor.

Just for practice, let's also change the class of `make` and `model` to character.

`@instructions`
- Change  `make` and `model` variables to character.

- Change `drive` so that is formatted as factor.

`@hint`
- Use the functions `as.factor()` and `as.character()` to change data classes.  

`@pre_exercise_code`
```{r}
make <- c("Saturn","Nissan","BMW","Audi","Honda","Kia","Mazda","Lamborghini","Subaru","Volkswagen")
model <- c("Ion","Titan","Z4","S6","Civic","Optima Hybrid","RX8","Gallardo","Outback","Jetta")
year <- c(2006,2012,2005,2009,2010,2012,2006,2010,2007,2007)
cyl <- c(4,8,6,10,4,4,2,10,4,5)
drive <- c("Front-Wheel Drive","All-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","Front-Wheel Drive","Front-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","All-Wheel Drive","Front-Wheel Drive")
mpg <- c(31,17,26,19,36,39,22,20,26,28)
fuelecon2 <-data.frame(make,model,year,mpg,cyl,drive)
fuelecon2$drive <- as.character(fuelecon2$drive)
```

`@sample_code`
```{r}
# Change the class of 'make' to character


# Change the class of 'model' to character


# Change the class of 'drive' to factor


```

`@solution`
```{r}
# Change the class of 'make' to character
fuelecon2$make <- as.character(fuelecon2$make)


# Change the class of 'model' to character
fuelecon2$model <- as.character(fuelecon2$model)


# Change the class of 'drive' to factor
fuelecon2$drive <- as.factor(fuelecon2$drive)




```

`@sct`
```{r}
test_object("fuelecon2", undefined_msg = "Ahhh!  This isn't supposed to happen!  Have you deleted fuelecon2?", incorrect_msg = "You have not changed the class correctly.")
success_msg("Awesome!")
```

---
## Using Ordered Factors

```yaml
type: NormalExercise
xp: 100
skills: 1
key: 88d3164325
```

Since factor variables represent categorical variables, it makes sense to distinguish between cases where there is no underlying quantitative relationship between values (ie *qualitative data*) and data where there is intrinsic ordering of values (*ordinal data*) 

This is readily accomodated in R by the use of factor *ordering*.  Let's try an example with the PSID data you created earlier.

`@instructions`
- First, view the structure of the PSID data framea already saved in the environment.

- Change `education` so that it is an ordered factor with the following ordering: `elementary`, `middle`, `HS`, `bachelors`, `masters`

`@hint`
- Try using the help file for `factor()` to see how ordering should be specified.

`@pre_exercise_code`
```{r}
earnings <- c(0,11000,0,1600,37730)
age <- c(36,31,34,35,45)
education <-c("hs","hs","middle","hs","masters")
married <- c("never","divorced","never","married","married")
PSID <-data.frame(earnings,age,education,married)
```

`@sample_code`
```{r}
# Change education into an ordered factor


```

`@solution`
```{r}
# Change education into an ordered factor
PSID$education <-factor(PSID$education, ordered=TRUE, 
    levels = c("elementary", "middle", "HS", "bachelors", "masters"))


```

`@sct`
```{r}
test_object("PSID", undefined_msg = "Ahhh!  This isn't supposed to happen!  Have you deleted PSID?", incorrect_msg = "You haven't changed education into an ordered vector correctly.  Try looking at the help file for `factor()`!")
success_msg("Awesome!")
```
---
## Selection of data frame elements

```yaml
type: NormalExercise
xp: 100
skills: 1
key: 8c664726b8a173cda730cbb20a52ac1795d9a0e9
```

Similar to vectors and matrices, you select elements from a data frame with the help of square brackets `[ ]`. By using a comma, you can indicate what to select from the rows and the columns respectively. For example:

- `my_df[1,2]` selects the value at the first row and second column in `my_df`.
- `my_df[1:3,2:4]` selects rows 1, 2, 3 and columns 2, 3, 4 in `my_df`.

Sometimes you want to select all elements of a row or column. For example, `my_df[1, ]` selects all elements of the first row. Let us now apply this technique on `planets_df`!

`@instructions`
- From `planets_df`, select the diameter of Mercury: this is the value at the first row and the third column. Simply print out the result.
- From `planets_df`, select all data on Mars (the fourth row). Simply print out the result.

`@hint`
To select the diameter for Venus (the second row), you would need: `planets_df[2,3]`. What do you need for Mercury then?

`@pre_exercise_code`
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

`@sample_code`
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Print out diameter of Mercury (row 1, column 3)


# Print out data for Mars (entire fourth row)

```

`@solution`
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Print out diameter of Mercury (row 1, column 3)
planets_df[1,3]

# Print out data for Mars (entire fourth row)
planets_df[4, ]
```

`@sct`
```{r}
msg = "Do not remove or overwrite the `planets_df` data frame!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("planets_df[1,3]", incorrect_msg = "Have you correctly selected and printed out the diameter for Mercury? You can use `[1,3]`.")
test_output_contains("planets_df[4, ]", incorrect_msg = "Have you correctly selected and printed out all data for Mars? You can use `[4,]`.")
success_msg("Great! Apart from selecting elements from your data frame by index, you can also use the column names. To learn how, head over to the next exercise.")
```


---
## Selection of data frame elements (2)

```yaml
type: NormalExercise
xp: 100
skills: 1
key: faf104fb0c605fd89f048648a4a588200bc89c76
```

Instead of using numerics to select elements of a data frame, you can also use the variable names to select columns of a data frame. 

Suppose you want to select the first three elements of the `type` column. One way to do this is

```
planets_df[1:3,1]
```

A possible disadvantage of this approach is that you have to know (or look up) the column number of `type`, which gets hard if you have a lot of variables. It is often easier to just make use of the variable name:

```
planets_df[1:3,"type"]
```

`@instructions`
Select and print out the first 5 values in the `"diameter"` column of `planets_df`.

`@hint`
You can select the first five values with `planets_df[1:5, ...]`. Can you fill in the `...` bit to only select the `"diameter"` column?

`@pre_exercise_code`
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

`@sample_code`
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Select first 5 values of diameter column

```

`@solution`
```{r}
# The planets_df data frame from the previous exercise is pre-loaded

# Select first 5 values of diameter column
planets_df[1:5, "diameter"]
```

`@sct`
```{r}
msg = "Do not remove or overwrite the `planets_df` data frame!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_output_contains("planets_df[1:5, \"diameter\"]", incorrect_msg = "Have you correctly selected the first five values from the diameter column and printed them out? You can use `[1:5, \"diameter\"]` here.")
success_msg("Nice! Continue to the next exercise!")
```


---
## Only planets with rings

```yaml
type: NormalExercise
xp: 100
skills: 1
key: e550ecb6ec45b856e6160ddfbb3d7875998e8365
```

You will often want to select an entire column, namely one specific variable from a data frame. If you want to select all elements of the variable `diameter`, for example, both of these will do the trick:

```
planets_df[,3]
planets_df[,"diameter"]
```

However, there is a short-cut. If your columns have names, you can use the `$` sign:

```
planets_df$diameter
```

`@instructions`
- Use the `$` sign to select the `rings` variable from `planets_df`. Store the vector that results as `rings_vector`.
- Print out `rings_vector` to see if you got it right.

`@hint`
`planets_df$diameter` selects the `diameter` column from `planets_df`; what do you need to select the `rings` column then?

`@pre_exercise_code`
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
```

`@sample_code`
```{r}
# planets_df is pre-loaded in your workspace

# Select the rings variable from planets_df
rings_vector <- 
  
# Print out rings_vector
```

`@solution`
```{r}
# planets_df is pre-loaded in your workspace

# Select the rings variable from planets_df
rings_vector <- planets_df$rings

# Print out rings_vector
rings_vector
```

`@sct`
```{r}
msg = "Do not remove or overwrite the `planets_df` data frame!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_object("rings_vector",
            incorrect_msg = "Have you correctly selected the `rings` variable from `planets_df`? Use `$rings`. Store the result as `rings_vector`.")
test_output_contains("rings_vector", incorrect_msg = "Don't forget to print out `rings_vector` after you've created it!")
success_msg("Great! Continue to the next exercise and discover yet another way of subsetting!")
```


---
## Only planets with rings (2)

```yaml
type: NormalExercise
xp: 100
skills: 1
key: 1581bf4667477f274188f4f637ec7fdc73659651
```

You probably remember from high school that some planets in our solar system have rings and others do not. Unfortunately you can not recall their names. Could R help you out?

If you type `rings_vector` in the console, you get:

```
[1] FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  TRUE
```

This means that the first four observations (or planets) do not have a ring (`FALSE`), but the other four do (`TRUE`). However, you do not get a nice overview of the names of these planets, their diameter, etc. Let's try to use `rings_vector` to select the data for the four planets with rings. 

`@instructions`
The code on the right selects the `name` column of all planets that have rings. Adapt the code so that instead of only the `name` column, _all_ columns for planets that have rings are selected.

`@hint`
Remember that to select _all_ columns, you simply have to leave the columns part inside the `[ ]` empty! This means you'll need `[rings_vector, ]`.

`@pre_exercise_code`
```{r}
load(url("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_r/planets.RData"))
rings_vector <- planets_df$rings
```

`@sample_code`
```{r}
# planets_df and rings_vector are pre-loaded in your workspace

# Adapt the code to select all columns for planets with rings
planets_df[rings_vector, "name"]
```

`@solution`
```{r}
# planets_df and rings_vector are pre-loaded in your workspace

# Adapt the code to select all columns for planets with rings
planets_df[rings_vector, ]
```

`@sct`
```{r}
msg <- "Do not remove or overwrite `planets_df` or `rings_vector`!"
test_object("planets_df", undefined_msg = msg, incorrect_msg = msg)
test_object("rings_vector", undefined_msg = msg, incorrect_msg = msg)
test_output_contains('planets_df[rings_vector, ]', incorrect_msg = "Have you correctly adapted the code to select _all_ columns for the planets that have rings? You can use `planets_df[rings_vector, ]`. Make sure to include the comma here, it's crucial!")
success_msg("Wonderful! This is a rather tedious solution. The next exercise will teach you how to do it in a more concise way.")
```


