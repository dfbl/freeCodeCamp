---
title: Shell scripting
---

# Shell scripting

In the command line, a shell script is an executable file that contains a set
of instructions that the shell will execute. It's main purpose its to reduce
a set of instructions (or commands) in just one file. Also it can handle
some logic because it's a programming language.

## How to create it

1) Create the file:
```bash
$ touch myscript.sh
```
2) Add a [shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) at the start of the file. The Shebang line is responsible for letting the command interpreter know which interpreter the shell script will be run with:
```bash
$ echo "#!/bin/bash" > myscript.sh
# or
$ your-desired-editor myscript.sh
# write at the first line #!/bin/bash
```
3) Add some commands:
```bash
$ echo "echo Hello World!" >> myscript.sh
```
4) Give the file _execution_ mode:
```bash
$ chmod +x myscript.sh
```
5) Execute it!
```bash
$ ./myscript.sh
Hello World!
```

## Passing variables from the command line

Oftentimes, you will need to use variables from the command line in your shell-script. For example, if you needed to do something with a file, but the file would change every time you ran your shell-script. In order to pass variables from the command line, $1 must be used in the script file, and so on down the number line. An example of a script like this is below:
```#!/bin/bash
# A simple copy script
cp $1 $2
```
Then, when running this script in the command line in order to copy a file, it would look like this:
```
$ myscript.sh foo.txt bar.txt
```
foo.txt will be read as $1 and bar.txt as $2 in the script.

More info about shell-scripting can be found [here](https://www.shellscript.sh/)
