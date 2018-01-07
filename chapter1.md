---
title       : Basics
description : Operations, Variables, and Data Types
attachments :

---

## Calculate a value.

```yaml
type: NormalExercise
xp: 50
key: bc36446b49
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
type: NormalExercise
xp: 100
key: eda3643137

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
type: NormalExercise
xp: 100
key: 2c80ac45d5

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
## Data Types

```yaml
type: BulletExercise
key: a9fb759d8f
lang: r
xp: 100
```


`@pre_exercise_code`
```{r}
a <- false
b <- "42"

```



***

### Display objects a and b

```yaml
type: NormalExercise
xp: 100
```

`@instructions`

Print objects a and b:

`@hint`

To display an object, just enter it on a separate line.

`@sample_code`
```{r}
# Display a and b

```

`@solution`
```{r}
# Display a and b
a
b


```

`@sct`
```{r}
test_output_contains("42", incorrect_msg = "Make sure to print the variable b.")
test_output_contains("false", incorrect_msg = "Make sure to print the variable b.")
success_msg("Good job!")
```

***

### A logical object

```yaml
type: NormalExercise
xp: 100
```

`@instructions`

- Test whether object a is a logical data type.
- Convert object a to logical.

`@hint`

- You can view information about the structure of an object by using the str() command.
- Logical arguments should be in all caps.

`@sample_code`
```{r}
# Check the structure of a.


# Convert a to logical.


```

`@solution`
```{r}
# Check the structure of a.
str(a)

# Convert a to logical.
a <- FALSE

```

`@sct`
```{r}
test_object("a", undefined_msg = "Make sure to define a variable `a`.",
            incorrect_msg = "Make sure that you assign the correct value to `a`.") 
success_msg("Good job!")
```
