# File System Concepts

![file system tree in unix](http://www.linuxstories.net/wp-content/uploads/2018/06/File-System-Structure-1024x495.png)

## Root

- Top of filesystem is called _root_ directory
- Denoted by "/" forward slash
- All other files and directories fall under root directory

## Common Unix Directories

- / the root
- / bin binaries (executables)
- / dev devices (peripherals)
- / devices where the devices really live
- / etc startup and control files
- / lib libraries (really in /usr)
- / opt optional software packages
- / proc access to processes
- / sbin standalone binaries
- / tmp place for temporary files- / root
- /usr user stuff
- /usr/bin binaries again (user)
- /usr/include include files for compilers
- /usr/lib libraries of functions
- /usr/local local stuff
- /usr/local/bin local binaries
- /usr/local/lib local libraries
- /usr/openwin X11 stuff
- /usr/sbin sysadmin stuff
- /usr/tmp place for more temporary files
- /usr/ucb ucb binaries
- /var variable stuff

## Files

- Unix treats all data in filesystem as a file
- A file is
  - one way array of bytes
  - unaffected by restarts(unlike data in ram)
  - accessible by names
- OS takes care of translating file names to numbers to specific addresses on the disk

## Regular Files

- Text files
- Binary Files
- info about a file gets stored in index nodes/inodes (data structures that contain metadata for a given file)
  - inode numbers are integer values that makes it more efficient to reference a file

## Directory Files

- Contains filenames and inodes

## Link Files

- link to existing data in two ways: hard links & soft links
  - Hard link:
    - link to data in another file
    - can only link to regular files
    - to delete x data you must delete any hard links to x.
  - Soft links:
    - link to any file (regular or directory)
    - link as if an alias or a shortcut
    - also known as symbolic link or symlink
    - `ln -s target-name link-name` creates a link file called link-name which is a softlink/shortcut to target-name

## Pathname symbols

- . - current directory
- .. - parent directory
- ~ - user's home directory

## navigating file commands

- ls -F, ls -l, ls --color to determine file types
- cd dr, ommiting directory name will change to home directory
- pwd - print current working directory
- stat filename / file filename - determine filer type and see metadata

## File Operations

- touch filename: creates or updates the last modified time stamp.
- `cp source1 source2 ... destination` copies sources to destination
  - if destination is a directory, all sources are copied into the destination directory
  - if destination is a regular file or doesn't exist, one source is permitted(creates a duplicate of source)
- `mv source1 source2 ... destination`
  - if destination is a directory, all sources are moved into the destination directory
  - if destination is a regular file or doesn't exist, one source is permitted(renames source file, command fails if multiple sources supplied)
- rm filename - remove the file
  - doesn't prompt for confirmation
  - rm -i asks for confirmation
  - doesn't delete directories
  - rm -d removes empty directories
  - rm -r recursively remove directiories and all files inside given directory
- mkdir dir1 dir2 ... : makes directories
- rmdir dir1 dir2 ... : removes directories
  - only empty directories can be removed
  - similar to rm -d
- mv dir1 dir2 ... destination: moves directories to destination
- cp -r dir1 dir2 ... destination copies directories into destination
  - -r is necessary to ensure the directories AND any subfiles are copied into destination, otherwise the command will assume sources are regular files and fail.

## Naming Files

- only char that can't be used in file name: "/"
- special characters usually have diff meanings and should be avoided
- ~ and - should not be used as first char
- file names are case sensitive
- typically character limit = 255

## File extensions

- usually 1-3 letter
- _in unix, executable programs are identified by permissions, not extensions_
- hidden files begin with a period ex: .hiddenfilename
- ls and other commands by default ignore hidden files
- config files and helper files are typically hidden files

## Wildcarding(globbing)

- \* : matches any string, including empty string
- \? :matches any single character
- \[...] : matches any one of the enclosed characters
  - the enclosed chars could be a range of chars or a class
  - ex: A-Z, A-F, 0-5, :alpha:, etc.
- \[^...] or \[!...] : matches chars that do not match the enclosed chars
- backslash escapes special characters

- Examples
- ls *.txt
  - Matches: notes.txt, report.txt, summary.txt
  - Does not match: image.png, notes.txt.bak
- ls file_?.log
  - Matches: file_1.log, file_a.log, file_X.log
  - Does not match: file.log, file_12.log
- ls file_\[1-3].txt
  - Matches: file_1.txt, file_2.txt, file_3.txt
  - Does not match: file_4.txt, file_12.txt

## Quoting
- to escape special characters, file names can be wrapped in quotation marks
- this forces command line to interpret the text inside the quotation marks as a single token
  - all wildcards are ignored

## Find
- recursively locates files in a directory that match a particular criteria
- find path expression
- path: where search begins
- expression: _options_ specifiying what to search for


## tar
- tar command is used to unpack/unpack or bundle a directory into a single archive file and vice versa
- conventionally .tar = archive file
- also known as tarball
- used for backing up and restoring directories, copying and sharing entire directories
- example: tar -cvf Assignment2.tar Assignment2
- c create, v verbose, f file
- to unpack: tar -xvf Assignment2.tar
- x extract, v verbose, f file
- z option compress or decompress using gzip
