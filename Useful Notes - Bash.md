# **LINUX BASH**

**`clear`** 							- *Clear the screen.*

**`exit`** or **`logout` or `CTRL-D`**	- *Exit the terminal.*

**`ps`**								- *Display currently active processes.*

**`ls`** 								- *List directory contents. `-a`: Include hidden files / directories. `-l`: Show details. `-t`: List by time. `-r`: Reverse order. `-F`: Show file type.
        								- `-R`: Recursively. - `-d`: Directories only. `--color`: Colourise.*
							
**`tree`**								- *List directory contents recursively for visually appealing structure. `-C`: Colourise. `-d`: Directories only.*

**`pwd`** 								- *Show current directory.*

**`$OLDPWD`**							- *Variable containing the previous `pwd`.*

**`$PATH`**								- *Variable containing the directories checked when executing a command.*

**`$EDITOR`**							- *Variable containing the default text editor.*

**`$PS1`**								- *Variable containing the default shell message.*

**`printenv`**							- *Print contents of all environment variables.*

**`which` [`command`]**					- *Shows which directory in `$PATH` contains [`command`].*

**`cd` [`dir`]** 						- *Change `pwd` to [`dir`].*

**`.`**									- *This directory.*

**`..`**								- *Parent directory.*

**`-`**									- *Previous directory (or use `cd $OLDPWD`).*

**`echo` [`argument`]**					- *print [`argument`] to screen.*

**`cat` [`file`]**						- *Concatenate and display files.*

**`more` [`file`]**						- *Browse a text file page by page.*

**`less` [`file`]**						- *The same, but backwards.*

**`head -x` [`file`]**					- *display first `x` lines of the file.*

**`tail -x` [`file`]**					- *Display last `x` lines of the file. `-f`: Follow the file. Displays data as it is written to the end of the file, i.e. a log file.* 

**`man` [`command`]**					- *Show the manual for [`command`].*

**[`command`] `--help`** 				- *Show the help page for [`command`].*

**`mkdir` [`directory`]**				- *Make a directory.*

**`rmdir` [`directory`]**				- *Remove an empty directory.*

**`rm -rf` [`directory`]**				- *Recursively remove a direcotry and all its contents.*

**`cp` [source] [destination]**			- *Copy source file to destination file / folder. `-r`: Copy recursively. `-i`: Interactive mode: Prompt user before overwriting.*

**`mv` [source] [destination]**			- *Move source file into directory, or rename file to new name (destination).*

**`groups`**							- *Display which groups a user belongs to.*

**`chmod` [`ugoa`] [`+-=`] [`rwx`]** 	- *Add, remove or set rwx file permissions for users, groups, others or all.*

**`chmod` [`xxx`]**						- *[`xxx`] is 3 digits 0-7 representing binary 000 - 111 switches for rwx, for the 3 groups.*

**`umask` [`xxx`]**						- *[`xxx`] is 3 digits 0-7 to be deducted from 777 to give the standard permission level of a newly created file.*

**`chgrp` [`group`]**					- *Change the file's group.*

**`find` [`directory`] `-iname` [`str`]**- *Find files in the [`directory`] matching the search string [`str`]. `-exec` [`command`] `{} \;`: Execute a `command` on all files returned from `find`.*

**`locate` [`str`]**					- *Searches faster than `find` as it uses a database of file names, but not always available / accurate.*

**`diff` or `sdiff` [`file1`] [`file2`]** - *Displays differences between two files. `sdiff` is more human-readable.*

**`file` [`file`]**						- *Display the file's type.*

**`grep` [`str`] [`file`]**				- *Search for string [`str`] within the file, display any lines containing it. `-v`: Inverse result. `-i`: Ignore case. `-c`: Count the results.*

**`strings` [`file`]**					- *Returns all printable strings in a binary file. Pipe to `grep` to filter results.*
										- *`strings BlueTrain.mp3 | grep -i john` searches the mp3 for strings mentioning 'john' or 'John'.*

**`sort` [`file`]**						- *Sort text in file alphabetically, by line. `-r`: Reverse order. `-kx`: Sort by key x? Not sure what this is.*

**`tar c\x\t f[tarfile] file(s)`**		- *Create, eXtract or lisT contents of a tar file. i.e. `tar cf test.tar test/` would archive the ./test/ directory and contents. `-v`: Show actions explicitly.*

**`gzip` or `gunzip` [`file`]**			- *Compress / decompress a single file.*

**`alias [methodname]='commands'`**     - *Create your own methods! i.e. `alias ll='ls -la'`. TO PERSIST, ADD TO .bash_profile.*




































