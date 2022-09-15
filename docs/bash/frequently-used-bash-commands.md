# Frequently used advanced Bash commands

Before we dive into bash commands, we need to understand Slash`(/)`, Tilde`(~)`, Dot`(.)`, Double Dot`(..)` symbol/characters because they are very importane if you're new to bash and command line.

-   Slash`(/)` is used for seperators for filesystem objects in both absolute paths and relative paths. Also it is used to represent the root directory.

-   Tilde`(~)` contains the path to the current user home directory (it gets expanded to the `$HOME` env variable).

-   Dot`(.)` is used to respresent the current directory.

-   Double Dot`(..)` is used to represt the parent directory of current directory.

**Conclusion**: `cd /` `cd ~/` `cd .` `cd ..` they are not equals. if you don't know what `cd` is here you'll learn it below.

> Hint: In terminals TAB key is used to auto-fill the path.

**If you're new to command lines and trying to learn all the commands then please visit <https://www.computerhope.com/unix.htm> to learn all the commands based on your Operating System and Shell.**

In this document I am just listing a couple of commands with advance options that we as a developer frequently use, I am also explaining each possible use case with examples here so that you can do things better.

> I am assuming that you already you bash commands and how to use that, if you don't know then learn them first from the above link then read this document for advance usage of some commands.

- [mkdir for Nested Directories](making-nested-directories.md)