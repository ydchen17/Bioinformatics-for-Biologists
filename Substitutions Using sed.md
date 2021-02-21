# Substitutions Using sed

Replacing one text string with another is something we often need to do.

This could be because we’ve discovered a repeated typo or misspelling in a file or because we’ve decided one piece of text needs replacing with something which reads better. We could, of course, do this manually, going through a file, correcting each appearance of an error. However, this is both time consuming and prone to human error. Linux thus includes a command called **sed** which allows us to make such substitutions automatically. The name **sed** is an abbreviation of stream editor.

The command is run in the following way:

```
sed 's/oldtext/newtext/' file.txt
```

This will replace the string *oldtext* with *newtext*, taking input from the file file.txt and by default write the result to standout output, which is your terminal. To replace writing to a new file use a redirect:

```
sed 's/oldtext/newtext/' file.txt > newfile.txt
```

This will output instead to a file called newfile.txt.

To make changes in place in the input file, use the -i option:

```
sed -i  's/oldtext/newtext/' file.txt
```

Only do this when absolutely sure that the substitution you are making is correct.

By default, **sed** will replace all instances of the old text string with the new text string.

[**Creative Commons license CC BY-NC-SA**](https://creativecommons.org/licenses/by-nc-sa/3.0/). © Wellcome Genome Campus Advanced Courses and Scientific Conferences 