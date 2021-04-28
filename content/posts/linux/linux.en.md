---
title: "Linux commands"
date: 2021-04-29T00:07:30+09:00
draft: false
---

## Basic Linux Commands

1.  ### Information

    - Commands that are applicable to both files and directories typically require additional options when attempting to apply to directories. Please check the options before you apply them.
    - Please refer to the table below for other notations.

    | Notation  | Meaning                             |
    | --------- | ----------------------------------- |
    | (-------) | Additional Options (Not required)   |
    | [------]  | Required Options                    |
    | usage     | Links to more detailed explanations |

2.  ### Linux filesystem

    | Command                     | Description                                             | Example             | Man page                                                   | Usage                         |
    | --------------------------- | :------------------------------------------------------ | ------------------- | ---------------------------------------------------------- | ----------------------------- |
    | ls (option) (directory)     | View the contents of (directory)                        | ls                  | [Link](https://man7.org/linux/man-pages/man1/ls.1.html)    | [Link](./LinuxCommand/ls.md)  |
    | cd (directory)              | Navigate through (directory)                            | cd Test/            | [Link](https://man7.org/linux/man-pages/man1/cd.1p.html)   | [Link](./LinuxCommand/cd.md)  |
    | mkdir [name]                | Make a new directory with the name [name]               | mkdir Test          | [Link](https://man7.org/linux/man-pages/man1/mkdir.1.html) |                               |
    | cp (option) [name1] [name2] | Copy name1 files/directories to name2 files/directories | cp test1 test2      | [Link](https://man7.org/linux/man-pages/man1/cp.1.html)    |                               |
    | mv (option) [name1] [name2] | Move name1 file to name2 file                           | mv file1 Test/file2 | [Link](https://man7.org/linux/man-pages/man1/mv.1.html)    |                               |
    | rm (option) [name]          | Delete files/directories called [name]                  | rm file1            | [Link](https://man7.org/linux/man-pages/man1/rm.1.html)    | [Link](./LinuxCommand/rm.md)  |
    | cat (option) (filename)     | List [filename] contents                                | cat file1           | [Link](https://man7.org/linux/man-pages/man1/cat.1.html)   | [Link](./LinuxCommand/cat.md) |

3.  ### Linux package manager

    1.  Before we start...

        1. Commands with the **CAUTION!** mark shows commands with a **risk of resetting the entire server**. If you are trying to execute these commands on a lab server or someone else's server, please get confirmation from the person in charge before you execute them!
        2. The Caution mark is a command that poses a risk of conflict with existing packages. If there is a problem after execution, consider whether this command was the cause of the problem.
        3. Typically, the warning signs above are commands you have to install to use. Just as you need to be careful when installing them on Windows, you need to be careful when installing them on Linux.

    2.  Ubuntu

             | Command                    | Description                                    | Example              | Caution      |
             | -------------------------- | ---------------------------------------------- | -------------------- | ------------ |
             | apt update                 | Check for updates of existing installed packages           | sudo apt update      |              |
             | apt upgrade                | Update if there is a package to update    | sudo apt upgrade     | **CAUTION!** |
             | apt install [package]      | install package and additional packages required by package

        | sudo apt install gcc | **CAUTION!** |
        | apt-cache policy [package] | Displays which versions of a package are available from which repo at which priority. | apt-cache policy gcc | |

4.  ### Others

    | command       | description                                                                   | example |
    | ------------- | ----------------------------------------------------------------------------- | ------- |
    | man [command] | Prints the manual such as the role, usage, and options the command has. RTFM! | man cat |

---

<h4> Contributor</h4>

| Name       | Contribution                                                            |
| ---------- | ----------------------------------------------------------------------- |
| raven724   | Create file, write information, Linux filesystem, Linux package manager |
| daniel2231 | Translation to english, minor fixes                                     |
