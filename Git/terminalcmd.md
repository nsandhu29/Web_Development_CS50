# Shortcuts on Mac Terminal 

* `Tab` Auto-complete file and folder names
* `Ctrl + A` Go to the beginning of the line you're currently typing on
* `Ctrl + E` Go to the end of the line you're currently typing on
* `Ctrl + U` Clear the line before the cursor
* `Ctrl + K` Clear the line after the cursor
* `Ctrl + W` Delete the word before the cursor
* `Ctrl + T` Swap the last two characters before the cursor
* `Esc + T` Swap the last two words before the cursor
* `Ctrl + L` Clear the screen
* `Ctrl + C` Kill whatever you're running
* `Ctrl + D` Exit the current shell
* `Option + →` Move cursor one word forward
* `Option + ←` Move cursor one word backward
* `Ctrl + F` Move cursor one character forward
* `Ctrl + B` Move cursor one character backward
* `Ctrl + Y` Paste whatever was cut by the last command
* `Ctrl + Z` Puts whatever you're running into a suspended background process
* `Ctrl + _` Undo the last command

## Basics

* `/` *(Forward Slash)*: Top level directory
* `.` *(Single Period)*: Current directory
* `..` *(Double Period)*: Parent directory
* `~` *(Tilde)*: Home directory
* `sudo [command]` Run command with the security privileges of the super user
* `nano [file]` Opens the Terminal editor
* `open [file]` Opens a file
* `[command] -h` Get help about a command
* `man [command]` Show the help manual of the command

## Change Directory

* `cd` Home directory
* `cd [folder]` Change directory, e.g. cd Documents
* `cd ~` Home directory
* `cd/` Root of the drive
* `cd -` Previous directory or folder you last browsed
* `pwd` Show your working directory
* `cd..` Move up to the parent directory
* `cd../..` Move up two levels

## List Directory Contents

* `ls` Display the name of files and subdirectories in the directory
* `ls -C` Force multi-column output of the listing
* `ls -a `List all entries including those with .(period) and ..(double * period)
* `ls -1` Output the list of files in one entry per line format
* `ls -F` Display a / (slash) immediately after each path that is a directory,*  * (asterisk) after executable programs or scripts, and @ after a * symbolic link
* `ls -S` Sort files or entries by size
* `ls -l` List in a long format. Includes file mode, owner and group name, * date and time file was modified, pathname, and more
* `ls -lt` List the files sorted by time modified (most recent first)
* `ls -lh` Long listing with human readable file sizes in KB, MB, or GB
* `ls -lo` List the file names with size, owner, and flags
* `ls -la` List detailed directory contents, including hidden files

## File Size and Disk Space

* `du` List usage for each subdirectory and its contents
* `du -sh [folder]` Human readable output of all files in a directory
* `du -s` Display an entry for each specified file
* `du -sk* | sort -nr` List files and folders, totaling the size including * the subfolders. Replace sk* with sm* to list directories in MB
* `df -h` Calculate your system's free disk space
* `df -H` Calculate free disk space in powers of 1,000 (as opposed to 1,024)


## File and Directory Management

* `mkdir` Create new folder named
* `mkdir` -p /: Create nested folders
* `mkdir` &lt;dir1&gt; &lt;dir2&gt; &lt;dir3&gt;: Create several folders at * once
* `mkdir` "": Create a folder with a space in the filename
* `rmdir` Delete a folder (only works on empty folders)
* `rm -R` Delete a folder and its contents
* `touch` &lt;file&gt;: Create a new file without any extension
* `cp` &lt;file&gt; Copy a file to the folder
* `cp` &lt;file&gt; &lt;newfile&gt;:Copy a file to the current folder
* `cp` &lt;file&gt;~//&lt;newfile&gt;:Copy a file to the folder and rename * the copied file
* `cp -R`  &lt;"new dir"&gt;:Copy a folder to a new folder with spaces in the * filename
* `cp -i` &lt;file&gt;Prompts you before copying a file with a warning * overwrite message
* `cp` &lt;file1&gt; &lt;file2&gt; &lt;file3&gt;/Users/Copy multiple files to * a folder
* `rm` &lt;file&gt;:Delete a file (This deletes the file permanently; use * with caution.)
* `rm -i` &lt;file&gt;:Delete a file only when you give confirmation
* `rm -f` &lt;file&gt;:Force removal without confirmation
* `rm` &lt;file1&gt; &lt;file2&gt; &lt;file3&gt;:Delete multiple files * without any confirmation
* `mv` &lt;file&gt; &lt;newfilename&gt;:Move/rename
* `mv` &lt;file&gt; Move a file to the folder, possibly by overwriting an * existing file
* `mv -i` &lt;file&gt; Optional -i flag to warn you before overwriting the * file
* `mv *.png` ~/Move all PNG files from current folder to a different folder

## Command History

* `Ctrl + R`:Search through previously used commands
* `history n`:Shows the previous commands you've typed. Add a number to * limit to the last n items
* `![value]`:Execute the last command typed that starts with a value
* `!!:`Execute the last command typed

## Permissions

* `ls -ld:` Display the default permission for a home directory
* `ls -ld/`Display the read, write, and access permission of a particular folder 
* `chmod 755` &lt;file&gt;:Change the permission of a file to 755
* `chmod -R 600` Change the permission of a folder (and its contents) to 600
* `chown` &lt;user&gt;:&lt;group&gt; &lt;file&gt;:Change the ownership of a file to user and group. Add -R to include folder contents

## Processes

* `ps -ax`:Output currently running processes. Here, a shows processes from all users and x shows processes that are not connected with the Terminal
* `ps -aux`:Shows all the processes with %cpu, %mem, page in, PID, and command
* `top`:Display live information about currently running processes
* `top -ocpu -s 5`:Display processes sorted by CPU usage, updating every 5 seconds
* `top -o rsize`:Sort top by memory usage

## Network

* `ping` &lt;host&gt;:Ping host and display status
* `whois` &lt;domain&gt;:Output whois info for a domain
* `curl -O` &lt;url/to/file&gt;:Download file via HTTP, HTTPS, or FTP
* `ssh` &lt;username&gt;@&lt;host&gt;:Establish SSH connection to &lt;host&gt; with user &lt;username&gt;
* `scp` &lt;file&gt;&lt;user&gt;@&lt;host&gt;:/remote/path:Copy &lt;file&gt;  to a remote &lt;host&gt;

## Homebrew

* `brew doctor`:Check brew for potential problems
* `brew install` &lt;formula&gt;:Install a formula
* `brew uninstall` &lt;formula&gt;:Uninstall a formula
* `brew list`:List all the installed formulas
* `brew search`:Display available formulas for brewing
* `brew upgrade`:Upgrade all outdated and unpinned brews
* `brew update`:Fetch latest version of homebrew and formula
* `brew cleanup`:Remove older version of installed formula
* `brew tap homebrew/cask`:Tap the cask repository from GitHub
* `brew cask list`:List all installed casks
* `brew cask install` &lt;cask&gt;:Install the given cask
* `brew cask uninstall` &lt;cask&gt;:Uninstall the given cask

## Search

* `find  -name `&lt;"file"&gt;:Find all files named &lt;file&gt; inside . Use wildcards (*) to search for parts of filenames
* `grep `"&lt;text&gt;" &lt;file&gt;:Output all occurrences of &lt;text&gt; inside &lt;file&gt; (add -i for case insensitivity)
* `grep -rl` "&lt;text&gt;" Search for all files containing &lt;text&gt; inside 

## Output

* `cat `&lt;file&gt;:Output the content of &lt;file&gt;
* `less` &lt;file&gt;:Output the contents of &lt;file&gt; using the less command that supports pagination and more
* `head` &lt;file&gt;:Output the first 10 lines of &lt;file&gt;
* &lt;`cmd`&gt; &gt; &gt; &lt;file&gt;:Appends the output of &lt;cmd&gt; to &lt;file&gt;
* &lt;`cmd`&gt; &gt; &lt;file&gt;:Direct the output of &lt;cmd&gt; into &lt;file&gt;
* &lt;`cmd1`&gt; `|` &lt;`cmd2`&gt;:Direct the output of &lt;cmd1&gt; to &lt;cmd2&gt;