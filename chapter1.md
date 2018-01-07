---
title       : Basics
description : Operations, Variables, and Data Types
attachments :

---
## Variables and Operations

```yaml
type: BulletExercise
xp: 100
key: 15d729634a
```

`@pre_exercise_code`
```{r}
# no pec
```

***

## Calculate a value.

```yaml
type: NormalExercise
xp: 50
key: 458889cb63
```

`@instructions`
- Without defining a new variable, calculate the log of (5 squared - 8).

`@hint`
You can take the log by using log().

`@sample_code`
```{r}
# Calculate the log of (5 squared - 8)

```

`@solution`
```{r}
# Calculate the log of (5 squared - 8)
log(5^2-8)

```

`@sct`
```{r}
test_output_contains("2.833213", incorrect_msg = "Make sure to calculate log of (5^2 - 8) on a new line. Do not start the line with a `#`, otherwise your R code is not executed!")
success_msg("Great!")

```
---


## Define a variable.

```yaml
type: NormalExercise
xp: 100
key: c4e91125fd
```

`@pre_exercise_code`
```{r}
# no pec
```

`@instructions`
- Create a new variable, called ***x***, equal to the log of (5 squared - 8).
- Print **x**.

`@hint`
You can print a variable just by entering it alone on a line.

`@sample_code`
```{r}
# Create the variable x.

# Print the variable x.

```

`@solution`
```{r}
# Create the variable x.
x <- log(5^2-8)

# Print the variable x.
x


```

`@sct`
```{r}
test_object("x", undefined_msg = "Make sure to define a variable `x`.",
            incorrect_msg = "Make sure that you assign the correct value to `x`.") 
test_output_contains("2.833213", incorrect_msg = "Make sure to print the variable x.")
success_msg("Good job!")


```


---

## Operations on Variables

```yaml
type: NormalExercise
xp: 100
key: bbede9b295
```


`@pre_exercise_code`
```{r}
x <- log(5^2-8)
```



`@instructions`
- Now create a new variable, ***y*** equal to the remainder of 12 / 5.
- Create a new variable z, equal to x times y.
- Display the value of z.

`@hint`
The remainder (or modulo) is indicated in R by %%.

`@sample_code`
```{r}
# Create the variable y.


# Create z, equal to x times y. 


# Display the variable of z.



```

`@solution`
```{r}
# Create the variable y.
y <- 12 %% 5

# Create z, equal to x times y. 
z <- x * y

# Display the variable of z.
z


```

`@sct`
```{r}
test_object("y", undefined_msg = "Make sure to define a variable `y`.",
            incorrect_msg = "Make sure that you assign the correct value to `y`.") 
test_object("z", undefined_msg = "Make sure to define a variable `z`.",
            incorrect_msg = "Make sure that you assign the correct value to `z`.")            
test_output_contains("5.666427", incorrect_msg = "Make sure to print the variable z.")
success_msg("Good job!")


```

---
## Data Object Types

```yaml
type: NormalExercise
xp: 100
key: '5093070519'
```


`@pre_exercise_code`
```{r}

a <- false
b <- "42"


```



`@instructions`
- Check if variable *a* is logical:
- Change *a* so that it is a logical variable (indicating false).
- Check if *b* is numeric:
- Change variable *b* so that it is numeric.

`@hint`
You can check the structure of a variable by using *str()*.
Logical statements should appear in all caps:  ie TRUE or FALSE.

`@sample_code`
```{r}
# Display variables a and b:
a
b

# Determine the data type of *a*.


# Change *a* so that is a logical variable.


# Determine the data type of *b*

# Change variable *b* so that it is numeric.



```

`@solution`
```{r}
# Display variables a and b:
a
b

# Determine the data type of *a*.
str(a)

# Change *a* so that is a logical variable.
a <- FALSE

# Determine the data type of *b*
str(b)

# Change variable *b* so that it is numeric.
b <-as.numeric(b)


```

`@sct`
```{r}
test_object("a", undefined_msg = "Make sure to define a variable `a`.",
            incorrect_msg = "Make sure that you assign the correct value to `a`.") 
success_msg("Good job!")

```





```
