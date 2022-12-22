# Terminal basics

## Commands

- `ls`: lists subdirectories or files in your current directory
- `pwd`: gives your current directory
- `cat <file>`: Outputs the contents of the file onto the terminal. Used to look at the contents of a file without opening it.
- `cd <target_directory>`: Changes your current directory to the the specified target directory. The target directory must be in your current working folder/directory. You can check this by typing the `ls` command.
- `grep "<string>" <file>` : This is the most basic usage of grep, for more flags/options, see [here](https://www.man7.org/linux/man-pages/man1/grep.1.html) and [here](https://www.howtogeek.com/496056/how-to-use-the-grep-command-on-linux/). Some usage flags include: `-i` : ignore case, `-H` : with file name (prints file name where each match is found), `-L` stops at first match.
- `touch <file>`: can be used to create a file in the current working directory, or in the directory provided like this -> `touch <path_to_file>`.
- `sed` : Extremely powerful tool, Sed, the ultimate stream editor. We can substitute words(like find and replace tool) using regex and so much more. Some examples would be:

```sh
sed -i 's/old/new/g' file
```

This would replace "old" with "new" for all occurrence's in file. For information on sed can be found [here](https://www.grymoire.com/Unix/Sed.html).
- `<command1>|<command2>`: The pipe command transfers the output of a given command (Here output of command1 is transferred to command2). For example if I wanted to transfer
- `>`  and `>>`:  The  '>' operator overwrites the existing file, or creates the file if file mentioned cannot be found. The '>>' operator appends to the existing file, or creates the file if file does not exist. See script below. Usage of the operators would be :`{command_with_output} > file` . Here is an example of a simple shell script.
```bash
#!/usr/bin/bash
# This is script I wrote that will append the given data to the file logger.md
echo -n "Enter line to be appended: "
read userinput
echo "$userinput" >> ~/Documents/logger.md
```
