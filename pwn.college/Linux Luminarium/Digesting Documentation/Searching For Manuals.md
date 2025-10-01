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
