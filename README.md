# cxpgrep
A multi-color grep with convenient features

![Alt Text](https://github.com/dczhu/cxpgrep/blob/master/res/cxpgrep.gif)

## Introduction
`cxpgrep` wraps up `grep` with some frequently used options (to save typing), and highlights different patterns in different colors, and organizes the output in a way convenient for anchoring at any matching line in the file opened in Vim. It has the following features:

- [x] By default includes the following `grep` options:
  > -sPHInr --exclude=*~ --exclude-dir=.vim --exclude-dir=.git --exclude-dir=.repo --exclude-dir=.svn
- [x] 1 color for each pattern - So a pattern (**Perl regular expression**) 'a|b' will have a and b in different colors.
- [x] Easy to construct command lines like `vim myfile +1270` to go to line 1270 of myfile.

## Installation
In ~/.bashrc:
1. source the script [h](https://github.com/dczhu/mch/blob/master/h), which is a multi-color pattern highlighter.
2. source the script [cxpgrep](https://github.com/dczhu/cxpgrep/blob/master/cxpgrep), which uses the command `h`. The commands `cxpgrep`/`cxpgrep2` will be available for use. `cxpgrep2` just displays the output in a format different from `cxpgrep`.

## Usage
* The command is like:
```shell
cxpgrep 'PAT1|PAT2|...' FILE-OR-DIRECTORY
```
Patterns will be highlighted in different colors in the output.
* It accepts other options of `grep`.
* To construct a Vim command line to jump to a hit line of a file, double click the file pathname and Shift + single click the line number in the `cxpgrep` output.

## Note
I designed a bunch of test cases to verify the implementation of `cxpgrep` and `cxpgrep2`. Cases can be added to the files cases\_cxpgrep and cases\_cxpgrep2, respectively. And there are 2 ways to use the cases: automated and interactive.

Automated:
```shell
source ch_tests_automated.sh cases_cxpgrep
```

Interactive:
```shell
source ch_tests_interactive.sh cases_cxpgrep
```

In both methods, one needs to compare the output of `cxpgrep` and `grep -P`. Certainly grep doesn't support multi-color highlighting.

Also, note that these 2 scripts are **NOT** to be run directly. They need to be sourced into the current shell environment. See above.

## Meta
Deng-Cheng Zhu (dengcheng _DOT_ zhu _AT_ gmail _DOT_ com)

Distributed under the MIT license. See LICENSE for more information.

https://github.com/dczhu/
