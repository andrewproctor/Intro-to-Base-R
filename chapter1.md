---
title       : Basic objects and operations
description : Introduction to basic math operations in R, variables, and data types.
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

---

## Calculate a value.

```yaml
type: NormalExercise
xp: 100
key: bc36446b49
```

`@instructions`
- Without defining a new variable, calculate the log of (5 squared - 8).

`@hint`
You can take the log by using log() function.

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
key: eda3643137
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
success_msg("Great!")
```


---

## Operations on Variables

```yaml
type: NormalExercise
xp: 100
key: 2c80ac45d5
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
- The remainder (or modulo) is indicated in R by %%.

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
success_msg("Great!")

```



---
## Data Types

```yaml
type: TabExercise
key: 54b1efd4a9
lang: r
xp: 100
```


`@pre_exercise_code`
```{r}
a <- "false"

```

`@sample_code`
```{r}
# Display object a


```

***

### Display variable a:

```yaml
type: NormalExercise
xp: 50
```

`@instructions`
- Display object a.

`@solution`
```{r}
# Display variable a
a

```

`@hint`
- To display an object, just enter it on a seperate line.

`@sct`
```{r}
test_output_contains("a", incorrect_msg = "Make sure to print the variable b.")

success_msg("Good job!")

```

***

### Logical Data Type

```yaml
type: NormalExercise
xp: 50
```

`@instructions`

- Check if *a* is logical.

`@sample_code`
```{r}
# Determine the data type of object a


```


`@solution`
```{r}
# Determine the data type of object a
str(a)

```

`@hint`

- To check the type of an object, you can use class() or str().

`@sct`
```{r}
```{r}
test_or(test_function("str", args = c("object")),
        test_function("class",  args = c("object")),
  not_called_msg = "Make sure to call either the function <code>class()</code> or <code>str()</code> to inspect the class of <code>a</code>.", 
  incorrect_msg = "Have you passed the correct variable to the function <code>class()</code> or <code>str()</code>?"))
              
success_msg("Nice job!")
```
