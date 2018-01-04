---
title       : Factors and data frames
description : Here is a short description.

--- key:d75143e5ab
## More work

```yaml
type: BulletExercise
xp: 100
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

```
