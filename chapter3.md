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
## Using ordered factors

```yaml
type: NormalExercise
xp: 100
skills: 1
key: 88d3164325
```

Since factor variables represent categorical variables, it makes sense to distinguish between cases where there is no underlying quantitative relationship between values (ie *qualitative data*) and data where there is intrinsic ordering of values (*ordinal data*) 

This is readily accomodated in R by the use of factor *ordering*.  Let's try an example with the PSID data you created earlier.

`@instructions`
- First, view the structure of the PSID data frame already saved in the environment.

- Change `education` so that it is an ordered factor with the following ordering: `elementary`, `middle`, `HS`, `bachelors`, `masters`

- Look at the structure of PSID again to see how it's changed.

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
# View the structure of the education column in PSID


# Change education into an ordered factor


# View the structure of the education column in PSID again


```

`@solution`
```{r}
# View the structure of the education column in PSID
str(PSID$education)

# Change education into an ordered factor
PSID$education <-factor(PSID$education, ordered=TRUE, 
    levels = c("elementary", "middle", "hs", "bachelors", "masters"))

# View the structure of the education column in PSID again
str(PSID$education)


```

`@sct`
```{r}
test_object("PSID", undefined_msg = "Ahhh!  This isn't supposed to happen!  Have you deleted PSID?", incorrect_msg = "You haven't changed education into an ordered vector correctly.  Try looking at the help file for `factor()`!")
test_output_contains("str(PSID$education)", incorrect_msg = "Have you correctly displayed the structure of the `education` column of `PSID`? Use `str()` to do this!")

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

Now let's practice selecting elements from a data frame using bracket arguments (eg `mydf[,]`).  For this exercise, you'll be using a larger sample from the same PSID dataset, `PSID2`.

`@instructions`
Using the `PSID2` data frame:
- Display the first row of observations. 
- Select only observations where `age` is less than 40 and marital status (`married`) is coded as "never".  Define this subset as `PSID.u40.unmarried`.

`@hint`

- To display the first row of a dataframe `x`, simply enter `x[1,]`.
- To assign the subset to a new data frame called `mysubset`, the code would be `mysubset <- x[1,]`.
- Remember you can used the AND operator (`&`) to place multiple conditions on the rows.

`@pre_exercise_code`
```{r}
earnings <-c(9700,1500,18300,0,0,0,0,1500,8921,13000,37000,7000,40000,21500,5200,34000,13000,21500,120,31000)
age <- c(45,40,50,43,30,30,35,36,37,36,40,44,44,32,35,35,35,37,34,31)
education <-c(11,12,12,10,11,12,12,16,12,10,16,16,13,12,13,17,12,14,13,14)
married <- c("divorced","separated","separated","married","married","separated","married","married","married","separated","married","married","divorced",
    "married","never","married","married","married","never","married")
PSID2 <- data.frame(earnings,age,education,married)
```

`@sample_code`
```{r}
# Display the first row of the data


# Save the subset of observations with age < 40 & married equal to 'never' as a data framed called PSID.u40.unmarried



```

`@solution`
```{r}
# Display the first row of the data
PSID2[1,]

# Save the subset of observations with age less than 40 and marital status equal to 'never' as a data framed called PSID.u40.unmarried
PSID.u40.unmarried <- PSID2[(age < 40) & (married=="never"),]


```

`@sct`
```{r}
test_object("PSID.u40.unmarried", undefined_msg = "Did you save the under 40, unmarried selection as a new data frame called PSID.u40.unmarried?", incorrect_msg = "Your subset conditions for PSID.u40.unmarried are not correct!")
test_output_contains("PSID2[1,]", incorrect_msg = "Have you correctly selected and printed out the first row of the `PSID2` data frame?")

success_msg("Good job!")
```
---
## Selection of data frame elements II

```yaml
type: NormalExercise
xp: 100
skills: 1
key: 63264c6763
```

Now let's select elements not only by subset conditions on the rows, but also on columns.

`@instructions`
Using the `fuelecon2` data frame
- Create a dataframe called `large.cyl.mpg` containing the columns `make`,`model`, and `mpg` of `fuelecon2` for cars with 8 or more cylinders.
- Display `large.cyl.mpg`

`@hint`

- Use the `c()` function to select multiple columns in your bracket.

`@pre_exercise_code`
```{r}
make <- c("Saturn","Nissan","BMW","Audi","Honda","Kia","Mazda","Lamborghini","Subaru","Volkswagen")
model <- c("Ion","Titan","Z4","S6","Civic","Optima Hybrid","RX8","Gallardo","Outback","Jetta")
year <- c(2006,2012,2005,2009,2010,2012,2006,2010,2007,2007)
cyl <- c(4,8,6,10,4,4,2,10,4,5)
drive <- c("Front-Wheel Drive","All-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","Front-Wheel Drive","Front-Wheel Drive","Rear-Wheel Drive","All-Wheel Drive","All-Wheel Drive","Front-Wheel Drive")
mpg <- c(31,17,26,19,36,39,22,20,26,28)
fuelecon2 <-data.frame(make,model,year,mpg,cyl,drive)
```

`@sample_code`
```{r}
# Create 'large.cyl.mpg'


# Display 'large.cyl.mpg'


```

`@solution`
```{r}
# Create 'large.cyl.mpg'
large.cyl.mpg <- fuelecon2[(cyl >=8),c("make","model","mpg")]

# Display 'large.cyl.mpg'
large.cyl.mpg

```

`@sct`
```{r}
test_object("large.cyl.mpg", undefined_msg = "Did you save the selection as `large.cyl.mpg`?", incorrect_msg = "Your subset conditions for large.cyl.mpg are not correct!")

test_output_contains("large.cyl.mpg", incorrect_msg = "You have not displayed `large.cyl.mpg`")

success_msg("Good job!")
```