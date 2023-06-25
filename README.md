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