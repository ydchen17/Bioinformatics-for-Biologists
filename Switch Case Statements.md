# Switch Case Statements

Sometimes of conditional logic may be too complex for if statements. In these situations, the issue isn’t that it’s impossible to write the logic as nested if statements, but that to do so could result in confusing code.

In these situations, we can use **case statements** to check each of our conditions in turn and process commands based on those conditions.

The case syntax looks like this:

```
case $string in
    	pattern_1)
      	command
      	;;
    	pattern_2)
      	alternate command
      	;;
    	*)
      	default command
      	;;
esac
```

Let’s break this down. First, we start with **case** followed by the variable or expression we want to test and then **in**. Next, we have our case patterns against which we want to check our variable or expression. We use the **)** symbol to signify the end of each pattern. After each pattern, you can then specify one or more commands you want to execute in the event that the pattern matches the expression or variable, terminating each clause with **;;**. As our last switch, it is common practice to have a default condition which is defined by having ***** as the pattern. Finally, we signify the end of our case statement by closing it with **esac** (case typed backwards!).

Here is a simple example:

```
#!/usr/bin/env bash
 
fruit="pineapple"
case $fruit in
    	apple)
      	echo "Your apple will cost 35p"
      	;;
    	pear)
      	echo "Your pear will cost 41p"
      	;;
    	peach)
      	echo "Your peach will cost 50p"
      	;;
    	pineapple)
      	echo "Your pineapple will cost 75p"
      	;;
    	*)
      	echo "Unknown fruit"
      	;;
esac
```

First, we set our variable, **fruit**, to have the value “pineapple”. We then compare this against several conditions looking to see whether the value of our variable matches the pattern provided. In the event that none of the patterns match our fruit, we have a default response “Unknown fruit”.

As one of the patterns is indeed “pineapple” we meet that condition and return:

```
Your pineapple will cost 75p
```

## Your task

Create a Bash script called **farm.sh** that uses a case statement to perform the following functions:

1. Stores a command line argument in a variable called animal
2. Use a case switch statement which has the following conditions and responses

- When the user enters cow, return “Here, moo”
- When the user enters sheep, return “There a baa”
- When the user enters duck, return “Everywhere a quack”
- Otherwise, return “Old MacDonald had a farm”

###### Please try to answer the questions yourself first and then compare the results with other learners. Finally, you can find solutions in the download area.

© Wellcome Genome Campus Advanced Courses and Scientific Conferences