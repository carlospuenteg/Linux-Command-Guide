# Index
* [Create/modify](#createmodify)
  * [mkdir](#mkdir)
  * [tee](#tee)
  * [mv](#mv)

* [Open files](#open-files)
  * [cat](#cat)
  * [more](#more)
  * [tail](#tail)
  * [head](#head)

* [Paths](#paths)
  * [pwd](#pwd)
  * [cd](#cd)

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
Syntax: `mv [-i] <filename> <new_filename>`

```bash
mv file1 file2_newname
```

##### Move
Syntax: `mv [-i] <files_list> <directory>`

```bash
mv file1 file2 dir1
```



### cp
* Copy files

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
| `-n_lines` | return the last n_lines |
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
| `-n_lines` | return the first n_lines |
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
