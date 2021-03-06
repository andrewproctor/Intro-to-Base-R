---
title: 'Vectors and Matrices'
description: 'Exercises focused on one-dimension data objects (vectors) and homogenous, two-dimensional objects (matrices).'
---

## Creating a vector

```yaml
type: NormalExercise
key: acd9c7ffdd
lang: r
xp: 100
skills: 1
```



`@instructions`
- Create a vector called `numbers` with the following elements: 1,2,3,4,5

`@hint`
To create a vector, pass the elements into the function <code>c()</code>, which stands for combined values.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Create 'numbers'


# Display 'numbers'


```

`@solution`
```{r}
# Create 'numbers'
numbers <- c(1,2,3,4,5)

# Display 'numbers'
numbers


```

`@sct`
```{r}
test_object("numbers", undefined_msg = "Make sure to define the vector as `numbers`.",
            incorrect_msg = "Make sure that you assign the elements to the `numbers` vector.") 
test_output_contains("numbers", incorrect_msg = "Make sure to display the `numbers` vector.")
success_msg("Great!")

```

---

## Creating a character vector

```yaml
type: NormalExercise
key: 591aa8489a
lang: r
xp: 100
skills: 1
```



`@instructions`
- Create a vector called `animals` with the following elements: `dog`, `cat`, `tiger`, `lion`, `panda`, `wolf`.

`@hint`
String elements (like words) should be listed in quotes as arguments for <code>c()</code>.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Create 'animals'


# Display 'animals'


```

`@solution`
```{r}
# Create 'animals'
animals <- c("dog","cat","tiger","lion","panda", "wolf")

# Display 'animals'
animals

```

`@sct`
```{r}
test_object("animals", undefined_msg = "Make sure to define the vector as `animals`.",
            incorrect_msg = "Make sure that you assign the elements to the `animals` vector.") 
test_output_contains("animals", incorrect_msg = "Make sure to display the `animals` vector.")
success_msg("Great!")

```

---

## Getting help

```yaml
type: NormalExercise
key: bcb2a2b508
lang: r
xp: 100
skills: 1
```

In the next exercise, you will be creating a matrix.  

To prepare, look over the helpfile for the <code>matrix</code> function.

`@instructions`
- Access the R help file for the <code>matrix</code> function.

`@hint`
- You can access the help file two different ways, through <code>?FUNCTION</code> or <code>help(FUNCTION)</code>.

`@pre_exercise_code`
```{r}
# No PEC
```

`@sample_code`
```{r}
# View the help file for the `matrix` function

```

`@solution`
```{r}
# View the help file for the `matrix` function
help(matrix)
?matrix
```

`@sct`
```{r}
test_or(test_function("help", args="topic", 
         not_called_msg = "Try using the <code>help()</code> function!",
              args_not_specified = "Remember to supply <code>matrix</code> as the topic for the help function.",
              incorrect_msg = "Remember to supply <code>matrix</code> as the topic for the <code>help()</code> function."),
        test_student_typed("?matrix"))
success_msg("Great!")
```

---

## Matrices in R

```yaml
type: NormalExercise
key: 21a0b0683c
lang: r
xp: 100
skills: 1
```



`@instructions`
- Create a matrix of randomly sampled values from a normal distribution.  There should be 3 rows and 3 columns, with the data filled in by row.  Call it  `norm_matrix`.
- You can generate a random sample of *n* values from the standard normal distribution is: <code>rnorm(n)</code>.

`@hint`
To create a matrix, use the <code>matrix()</code> function. Remember to specify nrow, ncol, and "byrow=TRUE".

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Generate a 3x3 matrix of standard normal values


```

`@solution`
```{r}
# Generate a 3x3 matrix of standard normal values
norm_matrix <- matrix(rnorm(9),nrow=3,ncol=3, byrow=TRUE)

```

`@sct`
```{r}
test_object("norm_matrix", undefined_msg = "Make sure to define the matrix as `norm_matrix`.",
            incorrect_msg = "Make sure that you have correctly specified `norm_matrix`.") 
success_msg("Great!")

```
