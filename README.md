NAME
----

autojump - a faster way to navigate your filesystem

DESCRIPTION
-----------

autojump is a faster way to navigate your filesystem. It works by
maintaining a database of the directories you use the most from the
command line.

*Directories must be visited first before they can be jumped to.*

USAGE
-----

`j` is a convenience wrapper function around `autojump`. Any option that
can be used with `autojump` can be used with `j` and vice versa.

-   Jump To A Directory That Contains `foo`:

        j foo

-   Jump To A Child Directory:

    Sometimes it's convenient to jump to a child directory
    (sub-directory of current directory) rather than typing out the full
    name.

        jc bar

-   Open File Manager To Directories (instead of jumping):

    Instead of jumping to a directory, you can open a file explorer
    window (Mac Finder, Windows Explorer, GNOME Nautilus, etc.) to the
    directory instead.

        jo music

    Opening a file manager to a child directory is also supported:

        jco images

-   Using Multiple Arguments:

    Let's assume the following database:

        30   /home/user/mail/inbox
        10   /home/user/work/inbox

    `j in` would jump into /home/user/mail/inbox as the higher weighted
    entry. However you can pass multiple arguments to autojump to prefer
    a different entry. In the above example, `j w in` would then change
    directory to /home/user/work/inbox.

For more options refer to help:

    autojump --help

INSTALLATION
------------

### REQUIREMENTS

-   Python v2.6+
-   Supported shells:
    -   bash v4.0+
    -   zsh
    -   fish
    -   tcsh (experimental)
    -   clink (Windows, experimental)

### AUTOMATIC

#### Linux

autojump is included in the following distro repositories, please use
relevant package management utilities to install (e.g. yum, apt-get,
etc):

-   Debian testing/unstable, Ubuntu, Linux Mint

    All Debian-derived distros require manual activation for policy
    reasons, please see `/usr/share/doc/autojump/README.Debian`.

-   RedHat, Fedora, CentOS (install `autojump-zsh` if you use zsh, `autojump-fish` for fish ...)
-   ArchLinux
-   Gentoo
-   Frugalware
-   Slackware

#### OS X

Homebrew is the recommended installation method for Mac OS X:

    brew install autojump

MacPorts also available:

    port install autojump

Windows
-------

Windows support is enabled by [clink](https://code.google.com/p/clink/)
which should be installed prior to installing autojump.

### MANUAL

Grab a copy of autojump:

    git clone git://github.com/joelthelion/autojump.git

Run the installation script and follow on screen instructions.

    cd autojump
    ./install.py or ./uninstall.py

KNOWN ISSUES
------------

-   autojump does not support directories that begin with `-`.

-   For bash users, autojump keeps track of directories by modifying
    `$PROMPT_COMMAND`. Do not overwrite `$PROMPT_COMMAND`:

        export PROMPT_COMMAND="history -a"

    Instead append to the end of the existing $PROMPT\_COMMAND:

        export PROMPT_COMMAND="${PROMPT_COMMAND:+$PROMPT_COMMAND ;} history -a"

REPORTING BUGS
--------------

For any questions or issues please visit:

    https://github.com/joelthelion/autojump/issues

AUTHORS
-------

autojump was originally written by Joël Schaerer, and currently
maintained by William Ting. More contributors can be found in `AUTHORS`.

COPYRIGHT
---------

Copyright © 2012 Free Software Foundation, Inc. License GPLv3+: GNU GPL
version 3 or later <http://gnu.org/licenses/gpl.html>. This is free
software: you are free to change and redistribute it. There is NO
WARRANTY, to the extent permitted by law.
