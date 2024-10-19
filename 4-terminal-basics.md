# Terminal basics

## ls (List)

`ls` lists the contents of your current directory
** Home directory is indicated with `~` **

`ls [foldername] or ls [foldername]/`

lists the contents of foldername directory

```
> ls Desktop or ls Desktop/
```

`ls [foldername]/[subfolder]`

lists the contents of subfolder in foldername

```
> ls Desktop/Basics
```

## open .

`open .` opens the current directory in Finder (Mac).

```
 > open .
```

## start .

`start .` opens the current directory in File Explorer (Windows).

```
 > start .
```

## pwd - (Print Working Directory)

`pwd` displays the full path to your current working directory.

```
> pwd
# Example Output:
# /Users/jennycho/Desktop (on Mac)
# /c/Users/jennycho (on Windows for c drive)
```

## cd [directory] - (change directory)

`cd [directory]` moves you to a different directory.

```
    > cd Desktop
    > cd Basics
    > pwd
    # Example Output:
    # /Users/jennycho/Desktop/Basics **
```

## cd ..

`cd ..` moves you up one directory level.

```
    > pwd
    > /Users/jennycho/Desktop/Basics
    > cd ..
    > pwd
    > /Users/jennycho/Desktop
```

# touch [filename].txt (Touch)

`touch [filename].[filetype]` creates a file (or multiple files)

```
    > touch git-basics.txt # One file
    > touch terminal-basics.txt read.pdf cs103.txt # Multiple files
    > touch Desktop/Basics/example.txt # File in a specific folder
```

## mkdir - (make directory)

`mkdir` creates a new directory (or multiple directories)

```
    > mkdir git-basics
    > mkdir cs103 cs104 # Multiple folders
```

## rm [filename]

`rm [filename]` deletes a file or files (permanently)

```
    > rm example.txt
    > rm example.txt second.txt etc
```

## rm -rf [foldername]

`rm -rf [foldername]` deletes a folder (or directory) permanently _(r = recursive f = force)_

```
> rm -rf cs103
```

**Note:** Make sure important folders are saved somewhere in case you delete them!
