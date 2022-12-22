# Shell Scripting

What is shell scripting
// TODO
// sh vs bash
// posix compliant

## Bash scripting

Basic shell script examples.

The first script takes your height and appends to a height tracking markdown file. The first line `#!/bin/bash` indicates
that it is a bash script.

```sh
#!/bin/bash
# takes input
echo -n "Enter height: "
read height
currentDate=`date +"%d/%m/%Y"`
# The output must be in table format in markdown
echo "| $currentDate | $height |" >> ~/Documents/heightLogger.md
```

Or we could have it take one argument

```sh
#!/bin/bash
currentDate=`date +"%d/%m/%Y"`
# The output must be in table format in markdown
echo "| $currentDate | $1 |" >> ~/Documents/heightLogger.md
```

Now we can add some additional checks to it

```sh
#!/bin/bash
if [ -z $1 ]; then
	echo "First argument required (your height)"
else
	currentDate=`date +"%d/%m/%Y"`
	# The output must be in table format in markdown
	echo "| $currentDate | $1 |" >> ~/Documents/heightLogger.md
fi
```

Now we can set an alias or make our file and executable to use it.
