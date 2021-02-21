# File Manipulation: sort and uniq

## What are sort and uniq?

Ordering and manipulating data in Linux-based text files can be carried out using the **sort** and **uniq** utilities. The **sort** command orders a list of items both alphabetically and numerically, whereas the **uniq** command removes adjacent duplicate lines in a list.

**Let’s work through an example together, please play along!**

First, using nano editor (or any other text editor that you might prefer) create a text file with the following content (one fruit per line): orange pear apple banana grape satsuma melon pomegranate banana grape. Name it **fruit.txt**

**How to use sort**

The sort command accepts input from a text-based file and outputs its results to the screen.

```
sort  fruit.txt
```

The sort results can also be output into another text file.

```
sort fruit.txt > sorted_fruit.txt
```

You can reverse the order of the sort with the -r option.

```
sort -r fruit.txt
```

Scrambling the order of lines is also possible with the -R option

```
sort -R fruit.txt
```

This can be scrambled even further using the system random number generator

```
sort -R fruit.txt –random-source=/dev/random
```

The -f option forces the sort to ignore the case of a letter when ordering lines.

```
sort -f fruit.txt
```

The -s option stabilises the sort by outputting identical lines in the same order as they appeared in the original file.

```
sort -s fruit.txt
```

Duplicate lines can be removed with the -u option

```
sort -u fruit.txt
```

**How to use uniq**

The **uniq** command accepts input from a text-based file and removes any repeated lines, only if they are adjacent to each other. That’s why it’s used in conjunction with sort to remove non-adjacent lines.

```
sort fruit.txt | uniq
```

Case differences can be ignored when dropping duplicate adjacent lines, using the -i option.

```
sort fruit.txt | uniq -i
```

Combining -i with the -c option for uniq, counts the number of times a line occurs in a file.

```
sort fruit.txt | uniq -ic
```

Using the -d option with -i inverts the behaviour of uniq and only prints the duplicated lines.

```
sort fruit.txt | uniq -id
```

It can be helpful to pipe this output into the input of another uniq command.

```
sort fruit.txt | uniq -id | uniq -i
```

For more on sort and uniq visit https://www.linode.com/docs/guides/manipulate-lists-with-sort-and-uniq/

## Your task

How would you extract only the lines that repeat more than once in the file fruit.txt into a new file named repeated_fruit.txt file?

Post your answers to the comment area below and discuss your answers with the other learners.

[**Creative Commons license CC BY-NC-SA**](https://creativecommons.org/licenses/by-nc-sa/3.0/). © Wellcome Genome Campus Advanced Courses and Scientific Conferences 