# Passing Command Line Arguments to Bash Scripts

A command line argument is a parameter that we can supply to our Bash script at execution. They allow a user to dynamically affect the actions your script will perform or the output it will generate.

To pass an argument to your Bash script, your just need to write it after the name of your script:

```
./script.sh my_argument
```

In our Bash script, there are several reserved/pre-defined variables which we can use to recall the user-defined parameters. The first argument is stored in **$1**, the second in **$2**, the third in **$3**…and so on. We cannot use **$0** as that references your Bash script itself.

Let’s see how this works using an example script:

```
#!/usr/bin/env bash
 
echo "The first fruit is: $1"
echo "The second fruit is: $2"
echo "The third fruit is: $3"
```

If we run our script and don’t give an argument, we will see no output for our pre-defined variables:

```
./script.sh
The first fruit is:
The second fruit is:
The third fruit is:
```

Alternatively, if we provide three fruits, our script detects these and will return those values back to use via the pre-defined variables.

```
./fruit.sh apple pear orange
The first fruit is: apple
The second fruit is: pear
The third fruit is: orange
```

Sometimes, we may want to access all of the arguments. We can do this using **$@**.

Let’s update our example script to return all of the fruits provided as arguments to the script as well:

```
#!/usr/bin/env bash
 
echo "The first fruit is: $1"
echo "The second fruit is: $2"
echo "The third fruit is: $3"
echo "All fruits are: $@"
```

When we run our script, you can see that we now have an extra output which lists all of the fruits we gave to our script on the command line.

```
./fruit.sh apple pear orange
The first fruit is: apple
The second fruit is: pear
The third fruit is: orange
All fruits are: apple pear orange
```

© Wellcome Genome Campus Advanced Courses and Scientific Conferences