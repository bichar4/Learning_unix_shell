# Learning_unix_shell
This repo contains notes created during the learning of unix shell. This exercies is done on linux. 

The content are based on the Software Carpentry course https://swcarpentry.github.io/shell-novice/index.html

A unix shell is both a command-line interface and a scipting language which asllows to do repetitive tasks automatically and fast.The basic way to interact with unix shell would be to open up your terminal `(Alt+Ctrl+T)`. 


```
Note: Type `ls` command on the terminal to get list of all the content in current directory.
```

```
If the command cannot be found. It will print the error message `command not found` 
```

**Navigating Files and Directories** 
Data are organized into files (equivalent to paper files) and collection of files are handled by directories(similar to brief case). You can store not only files but also directories in directories. 
File system refers to the part of operating system that are responsible for managing files and directories. The files and directories are usually arranged as the following: 
```
project
│   README.md
│   file001.txt    
│
└───folder1
│   │   file011.txt
│   │   file012.txt
│   │
│   └───subfolder1
│       │   file111.txt
│       │   file112.txt
│       │   ...
│   
└───folder2
    │   file021.txt
    │   file022.txt
```
Here, the file111.txt is stored as `project/folder1/subfolder1/file111.txt`


| Command and options     | Usecase |
| ----------- | ----------- |
| **pwd**   | Get the current working directory      |
| **ls**   | See the content of the file system     |
| **ls -F**   | trailing '/' indicates directory <br /> @ indicates a link <br /> * indicates an executable      |
| **ls --help**   | displays more informaton on command usage <br /> --help is available for other commands as well     |
| **man ls**   | Read manual of given command <br /> Use uparrow and downarrow to navigate <br /> 'B' and spacebar to skip up and down by full page <br /> Use '/' followed by character to search <br/> If character found, use 'N' and Shift+N to hop words<br/>Press 'Q' to quit <br />**man** is available for other command in linux      |
| **clear**   | Clear existing content from terminal    |
| **ls Desktop/Bichar_projects/**   | Get the content in the directory /Desktop/Bichar_projects      |
| **cd Desktop/Bichar-projects**   | Change the working directory to Desktop/Bichar_projects  <br/> Same effect can be achived first changing directory to Desktop <br/> Then changing directory to Bichar_projects   |
| **cd**   | Change the working directory to home directory      |
| **cd ..**   | Go to one level directory up    |

**Tab Completion**: Usually, if you are typing a long file name, pressing tab will suggest/autocomplete the available directory/files which you can use as shortcut.

**Working With Files and Directories**

| Command and options     | Usecase |
| ----------- | ----------- |
| **mkdir thesis**   | Create a new directory called thesis in current working directoty     |
| **mkdir -p projects/data**   | Create a new directory called projects and subdirectory called data in current working directory     |
| **touch test.txt**   | Create a new file called test.txt in current working directory     |
| **nano test.txt**   | Opens up nano text editor with default name as test.txt for saving content      |
| **rm test.txt**   | deletes the file test.txt      |
| **rm i -test.txt**   | ask for confirmation before delete     |
| **rm -r testdir**   | If directory, use -r option      |
| **mv test/a.txt test/b.txt**   | move the file test/a.txt and name it test/b.txt giving effect of renaming   |
| **mv test/a.txt test/b.txt ./prod**   | move the file test/a.txt and  test/b.txt to the folder prod   |
| **cp test/a.txt b.txt**   | copies the file test/a.txt names it to b.txt in the current working directory  |
| **cp -r test test_backup**   | copies the directory test and names it to test-backup in the current working directory  |
**Wildcards** : Use `*` which represents zero or more characters. For example , Using *.jpg will select all the jpg files. `?` is the wildcard that is place holder for exactly one character.`[xyz]` matches any charecter within x,y,z on one character.


**Pipes and Filter**

A filter is a program that transforms a stream of input inro a stream of output. A pipe, `|` between two command provides output of the command on the left as the input to the command on the right.
| Command and options     | Usecase |
| ----------- | ----------- |
| **wc cubane.pdb**   | returns counts on no.of lines, words and characters from left to right |
| **wc \*.pdb**   | returns counts on no.of lines, words and characters on all the .pdb files|
| **wc -l \*.pdb**   | returns counts on no.of lines only |
| **wc \*.pdb > data.txt**   | saves the output to data.txt instead of displaying in terminal <br />  Files get overwritten if the number already presents|
| **cat data.txt**   | dumps all the content of data.txt on terminal|
| **less data.txt**   | displays only screenful content and stops|
| **sort numbers.txt**   | Sorts the content in numbers.txt in alphabetical order|
| **sort -n numbers.txt**   | Sorts the content in numbers.txt in numerical order|
| **head -n 3 data.txt**   | Display first 3 rows on data.txt|
| **echo hello > testfile01.txt**   |writes hello in testfile01.txt <br/> it replaces the content when called again|
| **echo hello >> testfile01.txt**   |writes hello in testfile01.txt <br/> it appends the content when called again|
| **tail -n 2 animals.csv**   | Display last  2 rows on data.txt|
| **sort -n data.txt \| head -n 1**   |Feeds the output of sort as input to head command|
| **cut -d , -f 2 animals.csv**   |cut the content in animals.csv by delimeter , and extract the second column|
| **uniq filename**   | filters out adjacent matching line in the file|
| **uniq -c filename**   | counts the number of adjacent matching line |

**Loops**

General syntax for for loop
```
# The word "for" indicated the start of a "For-loop" command
for thing in list_of_things 
#The word "do" indicates the start of job execution list
do 
    # Indentation within the loop is not required, but aids legibility
    #access the variable 'thing' using $thing or ${thing}
    operation_using/command $thing 
# The word "done" indicates the end of a loop
done  
```

Example of performing while loop: 
```
a=0

while [ $a -lt 10 ]
do
   echo $a
   if [ $a -eq 5 ]
   then
      break
   fi
   a=`expr $a + 1`
done
```

**Shell Scripting**

- Save the command in a file with .sh extension and run the command using `bash filename.sh`
- Pass the argument after the `bash filename.sh arg1 arg2 arg3` which can be accessed in the script using the special variables `"$1" "$2" "$3"`    
- Use `$@` sign to get all the command line arguments
- Use `#` sign as a comment 