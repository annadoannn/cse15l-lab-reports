# Lab Report 3 -- Bugs and Commands
## PART ONE - BUGS
Provide:

- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
- An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.

## PART TWO - RESEARCHING COMMANDS
I chose `grep`.
### Find four command-line options or alternate ways to use the `grep` command.
give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.


### 1. `-i` command-line option
__example of using `grep -i` on file from directories:__
~~~~
grep -i "emergency" technical/911report/chapter-9.txt
~~~~
