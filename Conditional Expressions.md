# Conditional Expressions

Earlier in the week, we look at how to assign values to variables. Now, we’re going to start looking at how we can compare them. To do this, we use conditional expressions.

Modern Bash syntax for **conditional expressions** encases our comparative expression inside double square brackets (**[[** and **]]**).

The syntax for this is:

```
[[ option arg1 ]]
```

or

```
[[ arg1 operator arg2 ]]
```

A conditional expression returns a Boolean value i.e. **true** or **false**. If the condition is met, it will return true and if not, false.

It’s worth noting that the spacing is important. Here are some examples of valid and invalid conditional expression syntax.

Valid:

```
[[ -f ${file} ]]
```

Invalid:

```
[[ -e file]]

[[-e file]]

[[-efile]]
```

## File and variable operators

When we process files in our Bash scripts, it is often useful to check that they exist or whether they’re empty before the rest of our script proceeds. File operators allow us to perform checks on files and give us the opportunity to handle errors gracefully.

Below are some of the most commonly used file operators.

Returns true if the file exists:

```
[[ -e ${file} ]]
```

Returns true if the file exists and is a directory:

```
[[ -d ${directory} ]]
```

Returns true if the file exists and is a regular file:

```
[[ -f ${file} ]]
```

Returns true if the file exists and is readable:

```
[[ -r ${file} ]]
```

Returns true if the file exists and has a file size > 0:

```
[[ -s ${file} ]]
```

We can also use conditional expressions to perform sanity checks on our variables.

For example, checking whether a value has been assigned to a particular variable (e.g. **var**):

```
[[ -v ${var} ]]
```

Or, to check that the variable length is greater than 0: [[ -n ${string} ]]

Or, that the length of the variable is 0:

```
[[ -z ${string} ]]
```

## String comparisons

**Strings**, as sequences of characters, can be compared. There are two string conditional expressions you need to be aware of:

- Is equal to **==**
- Is not equal to **!=**

This condition will return true if **string1** and **string2** are identical:

```
[[ ${string1} == ${string2} ]]
```

This condition will return true if **string1** and **string2** are different from one another:

```
[[ ${string1} != ${string2} ]]
```

## Arithmetic comparisons

In Bash, we don’t use the same syntax for string and arithmetic comparisons. There are six main arithmetic expressions:

- Is equal to **-eq**
- Is not equal to **-ne**
- Is less than **-lt**
- Is less than or equal to **-le**
- Is greater than **-gt**
- Is greater than or equal to **-ge**

This condition will return true if **arg1** is equal to **arg2**:

```
[[ ${arg1} -eq ${arg2} ]]
```

Alternatively, this condition will return true if **arg1** is not equal to **arg2**:

```
[[ ${arg1} -ne ${arg2} ]]
```

This condition will return true if **arg1** is less than **arg2**:

```
[[ ${arg1} -lt ${arg2} ]]
```

Meanwhile, this condition will return true if **arg1** less than or equal to **arg2**:

```
[[ ${arg1} -le ${arg2} ]]
```

This condition will return true if **arg1** is greater than **arg2**:

```
[[ ${arg1} -gt ${arg2} ]]
```

And, finally, this condition will return true if **arg1** is greater than or equal to **arg2**:

```
[[ ${arg1} -ge ${arg2} ]]
```

### Performing multiple comparisons

Using Bash syntax, we can also combine comparisons using the **&&** and the **||** operators which represent **AND** and **OR** respectively.

The following expression would only return true in the event that **var1** is equal to **var2** *AND* **var3** is equal to **var4**:

```
[[ ${var1} == ${var2} ]] && [[ ${var3} == ${var4} ]]
```

Alternatively, the following expression would only return true when either **var1** is equal to **var2** *OR* **var3** is equal to **var4**:

```
[[ ${var1} == ${var2} ]] || [[ ${var3} == ${var4} ]]
```

© Wellcome Genome Campus Advanced Courses and Scientific Conferences