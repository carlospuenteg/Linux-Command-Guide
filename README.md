# Index
* [Info](#info)
* [Commands](#commands)
  * [Create/modify](#createmodify)
    * [mkdir](#mkdir)
    * [tee](#tee)
    * [mv](#mv)
    * [cp](#cp)
    * [rm](#rm)

  * [Open files](#open-files)
    * [cat](#cat)
    * [more](#more)
    * [tail](#tail)
    * [head](#head)

  * [Paths](#paths)
    * [ls](#ls)
    * [pwd](#pwd)
    * [cd](#cd)

  * [Others](#others)
    * [man](#man)
    * [echo](#echo)
    * [who](#who)
    * [cal](#cal)
    * [clear](#clear)
    * [wc](#wc)
    * [id](#id)
    * [passwd](#passwd)
    * [date](#date)



# Info

A file that starts with `.`, like `.file1` file will be hidden, but can be seen with `ls -la`


# Commands

## Create/Modify
### mkdir
* Create directories

Syntax: `mkdir [options] directory_names`

| Option | Description |
|-|-|
| `-p` | Create parent directories as needed. |
| `-v` | Visualize the directories while they are being created |

Create directories `dir1`, `dir2` and `dir3`
```bash
mkdir dir1 dir2 dir3
```

Create directory `dir1` and create `dir2` inside
```bash
mkdir -p dir1/dir2
```


### tee
* Create and modify files

Syntax: `tee [options] [files_list]`

| Option | Description |
|-|-|
| `-a` | Append to the files instead of overwriting them |

Create a file `file1` and write `Hello World!` to it
```bash
tee file1
Hello World!
^D
```

Append `Appended text` to the file `file1`
```bash
tee -a file1
Appended text
^D
```



### mv
* Move or rename files

| Option | Description |
|-|-|
| `-i` | Ask for confirmation before overwriting files |
  
##### Rename
Syntax: `mv [-i] <filename/dirname> <new_filename/new_dirname>`

```bash
mv file1 file2_newname
```

##### Move
Syntax: `mv [-i] <files_list> <directory>`

```bash
mv file1 file2 dir1
```



### rm
* Remove files

Syntax: `rm [-ir] [files_list/directory]`

| Option | Description |
|-|-|
| `-i` | Ask for confirmation before removing files |
| `-r` | Remove directories and their contents recursively |

Remove file `file1`
```bash
rm file1
```

Remove directory `dir1` and ask for confirmation
```bash
rm -ir dir1
(answer "yes" to remove)
```




### cp
* Create copy files (creates a new file or folder if needed)

| Option | Description |
|-|-|
| `-i` | Ask for confirmation before overwriting files |
| `-r` | Copy directories recursively. Copy all the contents of a folder to other folder |
| `-p` | Preserve the file attributes |

##### Copy file to file
Syntax: `cp [-irp] <file1> <file2>`

```bash
cp file1 file1_copy
```

##### Copy directory to directory
Syntax: `cp [-irp] <dir1> <dir2>`

```bash
cp -r dir1 dir1_copy
```

##### Copy list of files to directory
Syntax: `cp [-irp] <files_list> <dir>`

```bash
cp file1 file2 dir1
```



## Open files

### cat
* Visualize the content of a file

Syntax: `[files_list]`

Visualize the content of `file1 and file2`
```bash
cat file1 file2
```

Write a file, like with `tee`: `cat > file1`
```bash
cat > file1
Hello 
World!
^D
```


### more
* Visualize the content of a file, page by page

Syntax: `more [files_list]`

Visualize the content of `file1`, page by page
```bash
more file1
```


### tail
* Prints the last N number of data from a file

Syntax: `tail [-n_lines][+n_lines] [-c n_chars][-f] [files_list]`

| Option | Description |
|-|-|
| `-n_lines` | return the last n_lines (**Default 10**) |
| `+n_lines` | return all lines except the first n_lines |
| `-c n_chars` | return the last n_chars |
| `-f` | follow the file (visualize changes in real time) |

Visualize the last 10 lines of `file1`
```bash
tail -10 file1
```

Visualize all lines except the first 10 of `file1`
```bash
tail +10 file1
```

Visualize the last 10 characters of `file1`
```bash
tail -c10 file1
```

Visualize the last 10 lines of `file1` in real time
```bash
tail -f file1
```


### Head
* Prints the first N number of data from a file

Syntax: `tail [-n_lines] [-c n_chars][-f] [files_list]`

| Option | Description |
|-|-|
| `-n_lines` | return the first n_lines (**Default 10**) |
| `-c n_chars` | return the first n_chars |

Visualize the first 10 lines of `file1`
```bash
head -10 file1
```

Visualize the first 10 characters of `file1`
```bash
tail -c10 file1
```

Visualize the last 10 lines of `file1` in real time
```bash
tail -f file1
```


## Paths

### pwd
* Print the current working directory

```bash
pwd
```

### cd
* Change the current working directory

Change it to `dir1`
```bash
cd dir1
```

Change it to the parent directory
```bash
cd ..
```

Change it to the home directory
```bash
cd
```

### ls
* List the contents of a directory

Syntax: `ls [-laRrtS] [directory_name] [filename]`

| Option | Description |
|-|-|
| `-l` | List in long format (More info about the files) |
| `-a` | List all files, including hidden files |
| `-R` | List subdirectories recursively |
| `-r` | Reverse alphabetical order |
| `-t` | Sort by time modified |
| `-S` | Sort by file size |

`-l` info:
* First column: file type
  * `-`: Regular file
  * `d`: Directory
  * `C`: Special file in character mode
  * `b`: Special file in block mode
  * `l`: Symbolic link
* Next 9 columns: file permissions
  * Permissions for each type of users
    * Columns 2-4: Owner
    * Columns 5-7: Members of the owner's **Group**
    * Columns 8-10: Other users
  * Permissions
    * `r`: Read (cols 2, 5, 8)
    * `w`: Write (cols 3, 6, 9)
    * `x`: Execute (cols 4, 7, 10)
  * `-`: No permission




## Others

### man
* Shows the system's manual of a command

Syntax: `man [-k] command_name`

| Option | Description |
|-|-|
| `-k` | Search by keyword |

Seach the `date` manual
```bash
man date
```


### echo
* Outputs the strings passed as arguments

Syntax: echo [-ne] `<text>`

| Option | Description |
|-|-|
| `-n` | Doesn't insert a line break after the text (next line starts in same line) |
| `-e` | Activates the interpretation of backslash characters. The text must be between double quotes |

Print `Hello World!`
```bash
echo "Hello World!"
```

Print `Hello World!` without line break
```bash
echo -n "Hello World!"
```

Print `Hello World!\nHello Again!` **without** backslash characters interpretation
```bash
echo "Hello World! \nHello Again!"

Hello World! \nHello Again!
```

Print `Hello World!\nHello Again!` **with** backslash characters interpretation
```bash
echo -e "Hello World! \nHello Again!"

Hello World! 
Hello Again!

```


### who

* Shows the users logged in the system and the time they logged in

Syntax: `who [am i] [-q]`

| Option | Description |
|-|-|
| `am i` | Shows the current user connected to the terminal|
| `-q` | Shows the number of current users and their names|

```bash
who
```


### cal

* Shows a calendar

Syntax: `cal [ [<month>] <year>]`

| Option | Description |
|-|-|
| `<month>` | Month to show |
| `<year>` | Year to show |

Calendar of the current month
```bash
cal
```

Calendar of the year 2013
```bash
cal 2013
```

Calendar of the month of september of 2013
```bash
cal 9 2013
```


### clear

* Clears the terminal

```bash
clear
```



### Visualize the number of words, lines and bytes of a file or of the standard input

* Syntax: `wc [-cwlL] <files_list>`

| Option | Description |
|-|-|
| `-c` | Number of bytes |
| `-w` | Number of words |
| `-l` | Number of lines |
| `-L` | Length of the longest line in each file |

```bash
wc file1
```



### id

* Shows the user's UID (User ID) and GID (Group ID)

```bash
id
```



### passwd

* Changes the user's password to a new one

```bash
passwd
```



### date

* Shows the current date and time

```bash
date
```
