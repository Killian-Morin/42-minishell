<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">

<h3 align="center">minishell</h3>

  <p align="center">
    Summary:
    This project is about creating a simple shell.
    <br />
    <br />
  </p>
</div>

<!-- TABLE OF CONTENTS -->

- [About The Project](#about-the-project)
- [Usage](#usage)
- [Authors](#authors)
- [Sources](#sources)

<!-- ABOUT THE PROJECT -->
## About The Project

This is the first 'big' project of the 42 Cursus, they are a lot of things to do, not clearly said by the subject and you can lose yourself in following the man pages.

It was pretty interesting since we had to use a bunch of new functions that we never used before but also some that we had already used for the previous projects of the cursus.

The subject indicates the builtins, behaviors that we need to implement in this bash.

We need to have a working history. For that, the function `add_history()` and the [History Library](https://linux.die.net/man/3/history) were pretty simple to use and implement.

To read from the prompt we used the `readline()` function from the [readline library](https://man7.org/linux/man-pages/man3/readline.3.html).

We have to handle the `''` (single quotes) and `""` (double quotes), they prevent the shell from interpreting the meta-characters in the quoted sequence except for the double quotes when using the `$` (dollar sign).

From the [pipex](https://github.com/Killian-Morin/42-pipex) project, we can take the pipes comportement that needs to be implemented here.

The redirections are the next utilities that we have to support:
  - `<` should redirect the input.
  - `>` should redirect the output.
  - `<<` should be given a delimiter, then read the input until a line containing the delimiter is seen. However, it doesn’t have to update the history!
  - `>>` should redirect output in append mode.

The `ctrl-C`, `ctrl-D` and `ctrl-\` needs to behave like in bash with `ctrl-C` that displays a new prompt on a new line, `ctrl-D` exits the shell and `ctrl-\` does nothing.

The **environnemental variables**, that are prefixed by a `$` followed by a sequence of characters that correspond to their names have to expand to their associated values.

Finally we have to handle several builtins that were recoded.

| builtin | Notes |
|:---------:|:-------------|
| `echo` | with the -n option and `$?` that expand to the exit status of the most recently executed foreground pipeline |
| `cd` | with only a relative or absolute path |
| `pwd` | with no options |
| `export` | with no options |
| `unset` | with no options |
| `env` | with no options |
| `exit` | with no options |

It was also a lot of fun to try and discover commands that would break it ... but also kinda stressful when the corrector puts a command and you don't know how your code will handle it.

It's coded in C.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- USAGE -->
## Usage

After compiling the program through the Makefile you can use the executable: `minishell`.

Then, all you have to do to launch and use our project is to run `./minishell` ... There, now you can enjoy our little bash.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- Authors -->
## Authors

* [@bkukaqi](https://github.com/Rimble5)
* [@kmorin](https://github.com/Killian-Morin)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- SOURCES -->
## Sources

* https://www.ibm.com/docs/en/aix/7.2?topic=shell-input-output-redirection-in-c
* http://tzimmermann.org/2017/07/28/data-structures-of-unix-file-io/
* http://tzimmermann.org/2017/08/17/file-descriptors-during-fork-and-exec/
* https://www.simplilearn.com/tutorials/c-tutorial/c-operators
* http://tzimmermann.org/2017/09/01/the-internals-of-unix-pipes-and-fifos/ (pipes explanation)
* https://www.rozmichelle.com/pipes-forks-dups/ (pipes + redirection + multipipes explanation) Summary part interesting for multipipes
* https://supunsetunga.medium.com/writing-a-parser-getting-started-44ba70bb6cc9 (parser)
* https://linuxconfig.org/list-of-exit-codes-on-linux (exit codes)
* https://tldp.org/LDP/abs/html/exitcodes.html (exit codes)
* https://www.gnu.org/software/bash/manual/bash.html (bash documentation)
* https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html (shell documentation)
* https://man7.org/linux/man-pages/man3/readline.3.html (readline documentation / man)
* https://tiswww.case.edu/php/chet/readline/readline.html (readline documentation)
* https://linux.die.net/man/3/history (history library documentation / man)
* https://www.thegeekstuff.com/2010/10/linux-error-codes/ (linux error codes)
* https://github.com/aaugu/minishellhttps://blog.devgenius.io/lets-build-a-linux-shell-part-i-954c95911501 (shell like construction)
* https://www.cs.purdue.edu/homes/grr/SystemsProgrammingBook/Book/Chapter5-WritingYourOwnShell.pdf (shell like construction)
* https://brennan.io/2015/01/16/write-a-shell-in-c/ (shell like construction)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
