# Get started by making shell scripts!
Basic shell script examples.

The first script takes your height and appends to a heigh tracking markdown file.

```sh
#!/usr/bin/bash
# takes input
echo -n "Enter height: "
read height
currentDate=`date +"%d/%m/%Y"`
# The output must be in table format in markdown
echo "| $currentDate | $height |" >> ~/Documents/heightLogger.md
```

Or we could have it take one argument

```sh
#!/usr/bin/bash
currentDate=`date +"%d/%m/%Y"`
# The output must be in table format in markdown
echo "| $currentDate | $1 |" >> ~/Documents/heightLogger.md
```

Now we can add some additional checks to it

```sh
#!/usr/bin/bash

if [ -z $1 ]; then
	echo "First argument required (your height)"
else
	currentDate=`date +"%d/%m/%Y"`
	# The output must be in table format in markdown
	echo "| $currentDate | $1 |" >> ~/Documents/heightLogger.md
fi
```


