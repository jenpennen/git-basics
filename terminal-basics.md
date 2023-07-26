# Terminal basics

## ls (List)
lists the contents of your current directory
** Home directory is indicated with ~ ***

## ls [foldername] or ls [foldername]/ 
lists the contents of foldername directory
** ex. > ls Desktop or ls Desktop/ **

## ls [foldername]/[subfolder]
lists the contents of subfolder in foldername
** ex. > ls Desktop/Basics **

## open .
will open up in Finder (on Mac) the same directory where you currently are
** ex. ~ > open . **

## start .
will open up in Windows the same directory where you currently are
** ex. ~ > start . **

## pwd - (Print Working Directory) 
prints out the path to the working directory ( where you currently are)
** ex. > pwd
    > /Users/jennycho/Desktop (on Mac) and /c/Users/jennycho (on Windows for c drive) **

## cd [directory] - (change directory)
changes directories
** ex. > cd Desktop
    > cd Basics
    > pwd
    > /Users/jennycho/Desktop/Basics **

## cd .. 
takes us back one level (one folder) 
** ex. > pwd
    > /Users/jennycho/Desktop/Basics
    > cd ..
    > pwd
    > /Users/jennycho/Desktop **

# touch [filename].txt (Touch)
creates a file (or multiple) 
** ex. > touch git-basics.txt (for one file)
    > touch terminal-basics.txt read.pdf cs103.txt etc... (multiple files)
    > touch Desktop/Basics/example.txt **

## mkdir - (make directory) 
will create a new directory or directories
** ex. > mkdir git-basics
    > mkdir cs103 cs104 etc (multiple folders) **

## rm [filename] 
deletes a file or files (permanently removes them)
** ex. > rm example.txt
    > rm example.txt second.txt etc **

## rm -rf [foldername]
deletes a folder (or directory) permanently *(r = recursive f = force)
** ex. > rm -rf cs103 **

*** make sure important folders are saved somewhere in case you delete them ***









