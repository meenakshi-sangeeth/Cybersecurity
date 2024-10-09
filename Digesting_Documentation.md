# Digesting Documentation

## 1. Learning From Documentation

### Challenge

To collect the flag by invoking `/challenge/challenge` program with the argument `--giveflag`

### Thought Process

The task required me to run`/challenge/challenge` with athe argument `--giveflag`. I recalled that arguments are additional datas passed to the command and its syntax is command followed by an argument.

### Solution

I used the following command
```bash
/challenge/challenge --giveflag
```
Upon execution, I got the flag

## 2. Learning Complex Usage

### Challenge

To collect the flag by invoking `/challenge/challenge` program with the argument `--printfile`

### Thought Process

I knew that `--printfile` argument prints arbitrary files to the terminal and the argument to the --printfile argument is the path of the flag to read.

### Solution

I used the following command
```bash
/challenge/challenge --printfile /flag
```
Upon execution, I got the flag

## 3. Reading Manuals

### Challenge

To collect the flag by using a secret option which will be displayed through the man page for `challenge`

### Thought Process

I knew that man is short for manual, and will display (if available) the manual of the command you pass as an argument. I recalled that I can scroll around the manpage with arrow keys and PgUp/PgDn and when I'm done reading the manpage, I can hit 'q' to quit

### Solution

To display the manpage, I used the following command
```bash
man challenge
```
Upon execution, I got the following output
```bash
CHALLENGE(1)                                                                            Challenge Commands                                                                           CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --vhjuka NUM
              print the flag if NUM is 591
```
Thus I figured I'll have to run `/challenge/challenge` along with the the argument `--vhjuka 591`
```bash
/challenge/challenge --vhjuka 591
```
Upon execution, I got the flag

## 4. Searching Manuals

### Challenge

To collect the flag by reading the `challenge` man page and finding the option that will give the flag

### Thought Process

I knew that man is short for manual, and will display (if available) the manual of the command you pass as an argument. I recalled that I can search through the manpage by hitting *n* to go to the next result and *N* to go to the previous result

### Solution

To display the manpage, I used the following command
```bash
man challenge
```
Upon execution, I got the manpage comprising of a large number of lines. I figured I'll have to search through the manpage in order to find the right argument. I tried hitting *n* and the part of lines containing "flag" were highlighted. Thus I kept hitting *n* until I found the following line

![cryptonite_taskphase_meenakshi/Screenshot 2024-10-09 173014.png](https://github.com/meenakshi-sangeeth/cryptonite_taskphase_meenakshi/blob/main/Screenshot%202024-10-09%20173014.png)


Then I used the following command
```bash
/challenge/challenge --tg
```
Upon execution, I got the flag

## 5. Searching For Manuals

### Challenge

To collect the flag by using `man man` to figure out how to search for the hidden manpage that will tell you how to use `/challenge/challenge`

### Thought Process

I knew that all of the man pages are gathered in a searchable database and that I'll be able to search the man page database with the usage of `mam man` to find the hidden challenge man page

### Solution

I used the following command
```bash
man man
```
Upon execution, I got the following output
```bash
MAN(1)                                                                                  Manual pager utils                                                                                 MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...

DESCRIPTION
       man  is  the  system's  manual pager.  Each page argument given to man is normally the name of a program, utility or function.  The manual page associated with each of these arguments is
       then found and displayed.  A section, if provided, will direct man to look only in that section of the manual.  The default action is to search in all of the available sections following
       a pre-defined order (see DEFAULTS), and to show only the first page found, even if page exists in several sections.

       The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions, e.g. /etc/passwd
       6   Games
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
       8   System administration commands (usually only for root)
       9   Kernel routines [Non standard]

       A manual page consists of several sections.

       Conventional section names include NAME, SYNOPSIS, CONFIGURATION, DESCRIPTION, OPTIONS, EXIT STATUS, RETURN VALUE, ERRORS, ENVIRONMENT, FILES, VERSIONS, CONFORMING TO, NOTES, BUGS, EXAM‐
       PLE, AUTHORS, and SEE ALSO.

       The following conventions apply to the SYNOPSIS section and can be used as a guide in other sections.

       bold text          type exactly as shown.
       italic text        replace with appropriate argument.
       [-abc]             any or all arguments within [ ] are optional.
       -a|-b              options delimited by | cannot be used together.
       argument ...       argument is repeatable.
       [expression] ...   entire expression within [ ] is repeatable.

       Exact rendering may vary depending on the output device.  For instance, man will usually not be able to render italics when running in a terminal, and will typically  use  underlined  or
       coloured text instead.

       The  command  or  function illustration is a pattern that should match all possible invocations.  In some cases it is advisable to illustrate several exclusive invocations as is shown in
       the SYNOPSIS section of this manual page.

EXAMPLES
       man ls
           Display the manual page for the item (program) ls.

       man man.7
           Display the manual page for macro package man from section 7.  (This is an alternative spelling of "man 7 man".)

       man 'man(7)'
           Display the manual page for macro package man from section 7.  (This is another alternative spelling of "man 7 man".  It may be more convenient when copying and pasting  cross-refer‐
           ences to manual pages.  Note that the parentheses must normally be quoted to protect them from the shell.)

       man -a intro
           Display, in succession, all of the available intro manual pages contained within the manual.  It is possible to quit between successive displays or skip any of them.

       man -t bash | lpr -Pps
           Format  the  manual  page for bash into the default troff or groff format and pipe it to the printer named ps.  The default output for groff is usually PostScript.  man --help should
           advise as to which processor is bound to the -t option.

       man -l -Tdvi ./foo.1x.gz > ./foo.1x.dvi
           This command will decompress and format the nroff source manual page ./foo.1x.gz into a device independent (dvi) file.  The redirection is necessary as the -T flag causes  output  to
           be directed to stdout with no pager.  The output could be viewed with a program such as xdvi or further processed into PostScript using a program such as dvips.

       man -k printf
           Search the short descriptions and manual page names for the keyword printf as regular expression.  Print out any matches.  Equivalent to apropos printf.

       man -f smail
           Lookup the manual pages referenced by smail and print out the short descriptions of any found.  Equivalent to whatis smail.
```
From the examples, I figured I might get the hidden challenge manpage on executing `man -k` with `challenge` as the argument. Thus I used the following command
```bash
man -k challenge
```
I got the following output upon execution
```bash
czgpyodedy (1)       - print the flag!
```
Now that I knew the manpage, I executed `man czgpyodedy` which gave me the following output
```bash
CHALLENGE(1)                                                                            Challenge Commands                                                                           CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --czgpyo NUM
              print the flag if NUM is 263
```
Now that I knew what argument I should give to `/challenge/challenge`, I used the following command
```bash
/challenge/challenge --czgpyo 263
```
Upon execution, I got the flag

## 6. Helpful Programs

### Challenge

To collect the flag by using `--help` 

### Thought Process

Since the challenge rewuired the usage of `--help`, I figured I'll have to pass `--help` to `/challenge/challenge`. I recalled that some programs don't have a man page, but might tell you how to run them if invoked with `--help`, often used as `-h` or, in rare cases, `-?`, `help`, or other esoteric values like `/?`

### Solution

I used the following command
```bash
/challenge/challenge --help
```
Upon execution, I got the following output
```bash
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
```
From the optional arguments, I figured I must pass `-p` and `-g` as the arguments to `/challenge/challenge` and hence I used the command `/challenge/challenge -p` which generated the following output
```bash
The secret value is: 981
```
Thus I used the following command
```bash
/challenge/challenge -g 981
```
Upon execution, I got the flag

## 7. Help For Builtins

### Challenge

To collect the flag by looking up the help of `challenge`, which is a shell builtin, to figure out the secret value that should be passed

### Thought Process

I knew that some commands, rather than being programs with man pages and help options, are built into the shell itself called as bultins. Since it was mentioned that `challenge` is a builtin, I recalled that I can get a list of shell builtins as well as help on a specific one by passing it to the `help` which was required for this challenge

### Solution

I used the following command
```bash
help challenge
```
Upon execution, I got the following output
```bash
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "AaeG6NiH".
```
I figured I must pass "AaeG6NiH" to the argument `--secret`. Thus I used the following command
```bash
challenge --secret AaeG6NiH
```
Upon execution, I got the flag
