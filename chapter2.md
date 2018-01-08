---
title       : Vectors, Matrices, and Data Frames
description : Insert the chapter description here

--- type:NormalExercise lang:r xp:100 skills:1 key:acd9c7ffdd
## Creating a Vector


*** =instructions

- Create a vector called *numbers* with the following elements: 1,2,3,4,5

*** =hint

To create a vector, pass the elements into the function c(), which stands for combined values. 

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

# Create `numbers`

```

*** =solution
```{r}
# Create `numbers`
numbers <- c(1,2,3,4,5)


```

*** =sct
```{r}
test_object("numbers", undefined_msg = "Make sure to define the vector as `numbers`.",
            incorrect_msg = "Make sure that you assign the elements to the `numbers` vector.") 


```
