# Bash Arrays

In the previous step we introduced you to Bash variables which can be used to hold temporary information. A variable holds a single value under a single name. By contrast, a Bash array can hold multiple values under a single name.

You can initialise an array by assigning values that are separated by spaces in standard brackets.

For example:

```
array=("value 1" "value 2" "value 3")
```

Remember, there should be no spaces on either side of the = symbol.

Each value in an array is known as an **element**. Each element in an array is referenced by a numerical index. This index starts at 0.

The syntax to access the first value in our array would be:

```
echo "${array[0]}"
```

Notice that the index (0) is encased in square brackets. This will return the first value in our array:

```
value 1
```

We can return all of the values in our array by using the **@** symbol:

```
echo "${array[@]}"
value 1 value 2 value 3
```

To count the number of elements in our array, we can prepend the array name with the # sign. In this case, we have 3 elements in our array:

```
echo "${#array[@]}"
3
```

We’ll learn a little more about working with arrays later in the week when we discuss wrapping our code into reusable chunks known as functions.

## Your task:

Write a Bash script in which you:

1. Create an array called **fruits** which contains: pineapple, peach, raspberry, plum, apple and kiwi
2. Output the number of elements in the fruit array
3. Output the last element of the fruit array

Please try to answer the questions yourself first and then compare the results with other learners. If you get stuck, you can find solutions in the download area.

© Wellcome Genome Campus Advanced Courses and Scientific Conferences