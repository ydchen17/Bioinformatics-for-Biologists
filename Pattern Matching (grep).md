# Pattern Matching (grep)

One thing we often need to do is check whether a particular file or set of files contains a string of characters.

This process is known as **pattern matching**. Using the command line, this is done with a command called **grep**. The name derives from the old Unix editor, ed, and stands for “*globally search for a regular expression and print matching lines*”. A regular expression is a string of characters defining a search pattern. Regular expressions can become incredibly complex, involving any number of special characters, short cuts and groupings so, for now, we will deal only with searches involving plain text.

At its most simple, **grep** is run like this on a single file:

```
grep -F querystring filename.txt
```

As output, it displays a line by line list of all lines containing the text querystring. Please note that if the query string includes space characters, quotes should be placed at either end of it. Additionally, the **-F** option signifies that we are searching for fixed strings rather than regular expressions. This can be omitted by advanced users searching for complicated regular expressions.

Grep has many command line options to refine searches and change the output format. Run the following to see all of the available options:

```
man grep
```

## Your task

Now, using this information and the files in the course_data directory, please answer the following questions, sharing your results in the comments area:

**Question 1**: Which files contain the word “difference”?

**Question 2** How many times does the word “Premium” occur in the file diamonds_fix.txt?

**Question 3** How many lines in the file diamonds_fix.txt do not include the phrase “Very good”?

Please try to answer the questions yourself first and then compare the results with other learners.

[**Creative Commons license CC BY-NC-SA**](https://creativecommons.org/licenses/by-nc-sa/3.0/). © Wellcome Genome Campus Advanced Courses and Scientific Conferences 