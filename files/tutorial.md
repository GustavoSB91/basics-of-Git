# Tutorial GIT basic commands

## Accessing and creating a directory at Windows. Use this command to acces any directory by the command prompt
- CD command
    -               C:\Users\Windows>cd /
    -               C:\>
    -               C:\>cd workspace/
    -               C:\workspace>
    - USE "cd .." (2 dots) to return.

- DIR command. Use this command to look files into directories.
    -               C:\workspace>dir
    -               O volume na unidade C não tem nome.
    -               Número de Série do Volume é *********
    -               Pasta de C:\workspace

    -               01/08/2021  08:52    <DIR>          .
    -               01/08/2021  08:52    <DIR>          ..
    -               01/08/2021  09:04    <DIR>          livro-receitas
    -                0 arquivo(s)              0 bytes
    -                3 pasta(s)   814.384.943.104 bytes disponíveis

-  Creating a directory using command mkdir
    -               C:\>mkdir workspace

- Creating file txt
    -               C:\workspace>echo > tutorial.txt

-  Deleting files inside directories
    -           C:\workspace>del tutorial
    -           C:\workspace\tutorial\*, Tem certeza (S/N)? S

    - You can observe below that the directory "tutorial" stills existing, but the files witch 
were inside it has delected

    -           C:\workspace>dir
    -           O volume na unidade C não tem nome.
    -           O Número de Série do Volume é *******
    -           Pasta de C:\workspace
    -           01/08/2021  09:25    <DIR>          .
    -           01/08/2021  09:25    <DIR>          ..
    -           01/08/2021  09:24    <DIR>          livro-receitas
    -           01/08/2021  09:27    <DIR>          tutorial
    -                          0 arquivo(s)              0 bytes
    -                          4 pasta(s)   814.383.714.304 bytes disponíveis
    -           C:\workspace>cd tutorial
    -           C:\workspace\tutorial>dir
    -           O volume na unidade C não tem nome.
    -           O Número de Série do Volume é *******
    -           Pasta de C:\workspace\tutorial
    -           01/08/2021  09:27    <DIR>          .
    -           01/08/2021  09:27    <DIR>          ..
    -                          0 arquivo(s)              0 bytes
    -                          2 pasta(s)   814.383.644.672 bytes disponíveis

-  Removing directories and files inside it
    -           C:\workspace>rmdir tutorial /S /Q
    -           C:\workspace>
    -           C:\workspace>dir
    -            O volume na unidade C não tem nome.
    -            O Número de Série do Volume é ******

    -            Pasta de C:\workspace

    -           01/08/2021  09:33    <DIR>          .
    -           01/08/2021  09:33    <DIR>          ..
    -           01/08/2021  09:24    <DIR>          livro-receitas
    -                          0 arquivo(s)              0 bytes
    -                         3 pasta(s)   814.386.855.936 bytes disponíveis

## Using GIT

### SHA1 command. Used to creat a 40 char code to cripto our file. Every time we change our file or text the code will change as well.

- Open GIT inside the directory that we will work on
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace/tutorial (master)
    -           $ openssl sha1 tutorial.txt
    -           SHA1(tutorial.txt)= 7d5da79167132ddec285ef795e9694429e49e5bf

### Crating a commit

-  INIT GIT
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git init
    -           Initialized empty Git repository in C:/workspace/.git/

-  Use dir -a to see git hidden file
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ dir -a
    -           .  ..  .git  tutorial.txt

-  Configurating email and user name
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git config --global user.email "sb.gustavo91@gmail.com"

    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git config --global user.name GustavoSB91

-  Creating commit 

    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git add *

    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git commit -m "commit inicial"
    -           [master (root-commit) f85de8b] commit inicial
    -            1 files changed, 85 insertions(+)
    -            create mode 100644 tutorial.txt

### Organizing, adding to git and commiting our files
- Creating a repository inside our workspace to add our files
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace
    -           $ mkdir files
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace
    -           $ mv tutorial.txt ./files/
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace
    -           $ mv tutorial.md ./files/

- Initializating, adding and commiting our files to git
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace
    -           $ git init
    -           Initialized empty Git repository in C:/workspace/.git/

    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git add *

    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git status
    -           On branch master

    -           No commits yet

    -           Changes to be committed:
    -             (use "git rm --cached <file>..." to unstage)
    -                   new file:   README.md
    -                   new file:   files/tutorial.md
    -                   new file:   files/tutorial.txt


    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git commit -m "tutorial_files"
    -           [master (root-commit) c32be0c] tutorial_files
    -            3 files changed, 226 insertions(+)
    -            create mode 100644 README.md
    -            create mode 100644 files/tutorial.md
    -            create mode 100644 files/tutorial.txt

    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git status
    -           On branch master
    -           nothing to commit, working tree clean

- Uploading to Github

    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git remote add origin https://github.com/GustavoSB91/basics-of-Git.git
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git remote -v
    -           Windows@DESKTOP-UCLREO9 MINGW64 /c/workspace (master)
    -           $ git push origin master

### So by here we can see some commands and basic tools to use GIT, using our directories on working directory, staging area, local repository and sendind to remote repository. Thanks and I hope I have contributed to our community.







