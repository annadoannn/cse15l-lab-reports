# Remote Access and FileSystem 
For each of the commands cd, ls, and cat, and using the workspace you created in this lab:
1. Share an example of using the command with no arguments.
2. Share an example of using the command with a path to a directory as an argument.
3. Share an example of using the command with a path to a file as an argument.

For each, include:

- A screenshot or Markdown code block showing the command and its output
- What the working directory was when the command was run
- A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
- Indicate whether the output is an error or not, and if it’s an error, explain why it’s an error.

## 1. Share an example of using the command with no arguments. 
![image](lab1-ex1.png)

*`cd:`*
- **What was the working directory when the command was run?**
  `/home`
- **How did you get the output?**
      `cd` stands for change directory. Due to `cd` not having an argument, it would result in not having an output because there is no path to lead to another directory outside of `/home`. 
- **Is the output an error? Why or why not?**
      The output is not an error. Due to `ls` not having an argument, it's the same as saying there's nothing to change. Therefore, there's no output error.


*`ls`:*
- **What was the working directory when the command was run?**
      `/home`
- **How did you get the output?**
       `ls` is the library function in the terminal. By using `ls` at the `/home` directory, it shows what file and/or directory can be accessed directly from the working directory. 
- **Is the output an error? Why or why not?**
      The output is not an error. Due to `ls` not having an argument, it should only show that the `lecture1` directory can be accessed, unless otherwise noted in the argument. Only `lecture1` shows also due to the fact that the directories in this lab are nested. Therefore, there's no output error.


*`cat`:*


## 2. Share an example of using the command with a path to a directory as an argument 
![image](lab1-ex2.png)


## 3. Share an example of using the command with a path to a file as an argument.

