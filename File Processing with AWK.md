# File Processing with AWK

AWK is a programming language. It is named after its three developers: Alfred Aho, Peter J Weinberger and Brian KernIghan

It is particularly useful for processing text files and extracting data, particularly when a file is split into columns or delimited by a specific character (e.g. a comma). AWK is a standard package in most Linux releases as well as Mac OSX. AWK is generally written in upper case, although the command itself is lower case.

AWK can be used to write complex scripts and programs but, in this course, we will use it directly on the command line. It reads a file line by line and splits each line into columns according to a delimiter character. The default delimiter is a single space character.

For the example commands given below, we will work with two files from the course data. These are **Diamonds.csv**, which contains comma separated values and **Diamonds_fix.txt**, which is delimited with the tab character. Both files contain the same data in 10 columns: carat, cut, color, clarity, depth, table, price, x, y and z. The last 3 (x, y and z) relate to the dimensions of the diamond in question.

In order to follow the commands below, please change directory into the directory containing your course data. Before beginning, it may be useful to run

```
man awk 
```

to see the options available for AWK and also see how some of the commonly used delimiter characters are viewed.

The first command to run is:

```
awk -F”\t” ‘{print $1}’ Diamonds_fix.txt
```

This will print the value in the first column of the file Diamonds_fix.txt.

A little explanation:

- The option -F”\t” tells AWK that the delimiter is tab, which is generally represented as \t on the command line.
- Each delimited column is represented by a $ symbol followed by a number. The number represents the column number so $1 is column1, $2 is column 2 etc. $0 prints the whole line.
- For each line of the file, AWK will do whatever command is contained in the curly brackets. In this case, we are asking it to print the value in the first column.

You may wish to change this command so it runs on the file Diamonds.csv by changing the delimiter in the -F option.

Like grep, AWK can be used to filter files based on a line by line basis, based on the text they contain. However, as AWK splits lines into columns according to the delimiter, more precision is available. AWK can print only lines which have a specific value in a specific column. For example:

```
awk -F”\t” ‘$2==”Ideal” {print $0}’ Diamonds_fix.txt
```

This prints only the lines of Diamonds_fix.txt in which column 2 (cut) contains the value “Ideal”.

Some explanation:

- The == symbol means ‘is equal to’. This is a common convention in programming languages with a single equals symbol generally meaning set the value to be.
- The print command only happens when column 2 contains the value ‘Ideal’.

Generally, AWK commands made of two parts, a pattern, such as ‘$2==”Ideal”’, and an action, in braces, such as ‘{print $0}’. The pattern defines the lines to which the action is applied. We could actually miss the action in this example, as AWK, by default will print the full line as output. Likewise, as we saw in the first example, if the pattern is omitted, AWK will perform the action on every line.

Patterns can be combined using the && symbol (for and) so a line is printed only if two or more conditions are met. For example:

```
awk -F”\t” ‘$2==”Ideal” && $4==”SI2”’ Diamonds_fix.txt
```

This command will print all lines in which column 2 has the value ‘Ideal’ and column 4 has the value ‘SI2’.

Likewise, using the || symbol (for or), we can print if any one of two or more conditions is met. For example:

```
awk -F”\t” ‘$2==”Ideal” || $4==”SI2”’ Diamonds_fix.txt
```

This will print a line column 2 has the value ‘Ideal’ or column 4 has the value ‘SI2’.

In addition to strings, awk can also filter on numeric values. For example:

```
awk -F”\t” ‘$1>1’ Diamonds_fix.txt
```

This will print all lines in which the first column has a value greater than 1. You will notice that the first line of header values is included in this. We can omit this simply by adding the condition ‘FNR>1’:

```
awk -F”\t” ‘FNR>1 && $1>1’ Diamonds_fix.txt
```

FNR represents the current line number so we’re asking AWK to print the line if this is greater than 1 (i.e. omit line 1).

[**Creative Commons license CC BY-NC-SA**](https://creativecommons.org/licenses/by-nc-sa/3.0/). © Wellcome Genome Campus Advanced Courses and Scientific Conferences 