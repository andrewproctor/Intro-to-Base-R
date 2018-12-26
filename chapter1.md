---
title: 'Basic objects and operations'
description: 'Introduction to basic math operations in R, variables, and data types.'
attachments:
    slides_link: 'https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf'
---

## Calculate a value.

```yaml
type: NormalExercise
key: bc36446b49
xp: 100
```



`@instructions`
- Without defining a new variable, calculate the log of (5 squared - 8).

`@hint`
You can take the log by using log() function.

`@pre_exercise_code`
```{r}

```

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
key: eda3643137
xp: 100
```



`@instructions`
- Create a new variable, called ***x***, equal to the log of (5 squared - 8).
- Print **x**.

`@hint`
You can print a variable just by entering it alone on a line.

`@pre_exercise_code`
```{r}
# no pec
```

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
key: 2c80ac45d5
xp: 100
```



`@instructions`
- Now create a new variable, `y` equal to the remainder of 12 / 5, using the modulo operator:  <code> %% </code>.
- Create a new variable `z`, equal to x times y.
- Display the value of `z`.

`@hint`
- The remainder (or modulo) is indicated in R by %%.

`@pre_exercise_code`
```{r}
x <- log(5^2-8)
```

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


```

***

```yaml
type: NormalExercise
key: cee78970e4
xp: 35
```

`@instructions`
- Display object `a` (commenting your code appropriately).

`@hint`
- To display an object, just enter it on a seperate line.

`@sample_code`
```{r}

```

`@solution`
```{r}
# Display variable a
a

```

`@sct`
```{r}
test_output_contains("a", incorrect_msg = "Make sure to print the variable a.")
test_student_typed("#", not_typed_msg = "Make sure to add a comment to explain what you're doing.")
success_msg("Good job!")

```

***

```yaml
type: NormalExercise
key: 482a6c9639
xp: 35
```

`@instructions`
- Check if `a` is logical (commenting your code appropriately).

`@hint`
- To check the type of an object, you can use class() or str().

`@sample_code`
```{r}


```

`@solution`
```{r}
# Determine the data type of object a
str(a)
class(a)
is.logical(a)
```

`@sct`
```{r}
test_or(test_function("str","object"),
        test_function("class","x"),
     incorrect_msg = "Have you passed the correct variable to the function?")
test_student_typed("#", not_typed_msg = "Make sure to add a comment to explain what you're doing.")
success_msg("Nice job!")
              
```

***

```yaml
type: NormalExercise
key: 1494a0adbd
xp: 30
```

`@instructions`
- Convert `a` so that it is logical object (commenting your code appropriately).

`@hint`
- Logical values are in all caps, eg TRUE or FALSE.

`@sample_code`
```{r}


```

`@solution`
```{r}
# Make a logical
a <- FALSE
```

`@sct`
```{r}
test_object("a", undefined_msg = "Make sure to define a variable `a`.",
            incorrect_msg = "Make sure that you assign the correct value to `a`.") 
test_student_typed("#", not_typed_msg = "Make sure to add a comment to explain what you're doing.")
success_msg("Nice job!")
              
```

---

## Data Types II

```yaml
type: TabExercise
key: 8f0e54b951
lang: r
xp: 100
```



`@pre_exercise_code`
```{r}
b <- "forty two"

```

***

```yaml
type: NormalExercise
key: 502b6d5d72
xp: 35
```

`@instructions`
- Display object `b` (commenting your code appropriately)

`@hint`
- To display an object, just enter it on a seperate line.

`@sample_code`
```{r}


```

`@solution`
```{r}
# Display variable b
b

```

`@sct`
```{r}
test_output_contains("b", incorrect_msg = "Make sure to print the variable b.")
test_student_typed("#", not_typed_msg = "Make sure to add a comment to explain what you're doing.")
success_msg("Good job!")

```

***

```yaml
type: NormalExercise
key: f217afbbda
xp: 35
```

`@instructions`
- Check if `b` is numeric.

`@hint`
- To check the type of an object, you can use class() or str().

`@sample_code`
```{r}

```

`@solution`
```{r}
# Determine the data type of object b
str(b)
class(b)

```

`@sct`
```{r}
test_or(test_function("str","object"),
        test_function("class","x"),
     incorrect_msg = "Have you passed the correct variable to the function?")
test_student_typed("#", not_typed_msg = "Make sure to add a comment to explain what you're doing.")
success_msg("Nice job!")
              
```

***

```yaml
type: NormalExercise
key: b93ed45091
xp: 30
```

`@instructions`
- Convert `b` so that it is numeric.

`@hint`
- Numeric values are defined in numbers (not text), without quotes.

`@sample_code`
```{r}


```

`@solution`
```{r}
# Make b numeric
b <- 42

```

`@sct`
```{r}
test_object("b", undefined_msg = "Make sure to define a variable `b`.",
            incorrect_msg = "Make sure that you assign the correct value to `b`.") 
test_student_typed("#", not_typed_msg = "Make sure to add a comment to explain what you're doing.")
success_msg("Nice job!")
              
```
