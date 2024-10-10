#Investigate Kali Linux

## Objectives
In this lab, you will complete the following objectives:

- Familiarize yourself with the Kali Linux GUI.
- Familiarize yourself with the Kali Linux shell.

## Background / Scenario
Linux is open source, fast, reliable, and small. It requires very little hardware resources to run and is highly customizable. Unlike other operating systems such as Windows and Mac OS X, Linux was created and is currently maintained by a community of programmers. Linux is part of several platforms and can be found on devices anywhere from "wristwatches to supercomputers." Because Linux is open source, any person or company can get the kernel’s source code, inspect it, modify it, and re-compile it at will. They are also allowed to redistribute the program with or without charges.

Linux distributions are packages created by different organizations. Linux distributions (or distros) include the Linux kernel with customized tools and software packages. While some of these organizations may charge for their Linux distribution support (geared towards Linux-based businesses), most of them also offer their distribution for free without support. Debian, Red Hat, Ubuntu, CentOS, and SUSE are just a few examples of Linux distributions.

Kali Linux is a special version of Linux designed specifically for security auditing and penetration testing. Many changes have been implemented to ensure security, system integrity, and security-specific capabilities. It is not recommended to use Kali for standard uses, such as gaming, development, and other day-to-day uses. As a security and pentesting expert, it is very important for you to know how to get around in Kali, both in the GUI and at the terminal. You need to be able to find the tools that you need to perform your job and manipulate files in the file system.

## Required Resources
- Kali VM customized for Ethical Hacker course
- Internet access

## Instructions

### Part 1: Familiarize Yourself with the Kali Linux GUI.

#### Step 1: Start the VM and learn about the Kali GUI.
1. Log into the Kali system with the username `kali` and the password `kali`. You are presented with the Kali desktop.
2. Like the Windows desktop, Kali has icons representing things like the trash, file explorer, and other links. There are also several icons across the top, like the Windows taskbar. In addition, icons for running applications will appear there. This is called the panel. From here, you can launch the Firefox web browser, terminals, and also set up additional desktops using the numbered buttons. Each desktop can be configured differently with specific links and files on it. This is useful if you commonly have sets of tools and files that you use for specific tasks. You can switch to the desktop that has the items you need when you are working on a certain job.
3. Right-click the panel, click `Panel`, and then `+ Add New Items…`. Here you can add many items to the panel to help you get to the tools and configurations that you use the most. Close the Add New Items window.
4. Right-click the panel, click `Panel`, and then `Panel Preferences…`. Here you can modify many settings to customize how the panel works and what it looks like. Additional panels can be added as well to accommodate more items. Investigate the settings and change the settings if you desire. Close both configuration windows when you are finished.
5. The top-right corner shows some settings and information, such as network connection, audio, time and date, and the power button. You can add additional items to this area using the panel configuration if you wish. This is a good place to look for useful information.

#### Step 2: Navigate the Applications menu.
1. Click the first icon on the left side of the panel. This opens the Applications menu. Like the Start button in Windows, this menu contains shortcuts to the applications and settings in the operating system. From here, you can navigate to any of the tools that have been installed, find the operating system settings, and search for anything you are looking for. All the tools in this VM are arranged by type, such as wireless attacks or vulnerability analysis. These groups make it easier to find an application specific to a functionality.
2. Navigate through the folders and look at all the different tools. Open a few if you would like to see them. Note that some of the tools have GUIs, but most open in a terminal window.
3. Close any open windows and click the square black and white icon in the panel. This will open a terminal for the next part of the lab.

### Part 2: Familiarize Yourself with the Kali Linux Shell.
The shell is the term used to refer to the command interpreter in Linux. Also known as the terminal, command line, or command prompt, the shell is a very powerful way to interact with a Linux computer.

Linux commands are programs created to perform specific tasks. Use the `man` command (short for manual) to obtain detailed documentation about commands. As an example, `man ls` provides documentation about the `ls` command from the user manual.

#### Step 1: Command documentation
1. To learn more about the man page, open a terminal and type:
    ```bash
    man man
    ```
2. Scroll through the output and name a few sections that are included in a man page.
   **Answer Area**
   <!----><!---->
   
   Type `q` to exit the man page.

To invoke a command via the shell, simply type its name. The shell will try to find it in the system path and execute it.

The table lists some basic Linux commands and their functions.

| Command   | Description                                                           |
|-----------|-----------------------------------------------------------------------|
| mv        | Moves or renames files and directories.                               |
| chmod     | Modifies file permissions.                                            |
| chown     | Changes the ownership of a file.                                      |
| dd        | Copies data from an input to an output.                              |
| pwd       | Displays the name of the current directory.                          |
| ps        | Lists the processes that are currently running in the system.        |
| su        | Simulates a login as another user or to become a superuser.         |
| sudo      | Runs a command as a super user, by default, or another named user.  |
| grep      | Used to search for specific strings of characters within a file or other command outputs. |
| ifconfig  | Used to display or configure network card related information. If issued without parameters, ifconfig will display the current network card(s) configuration. Note: While still widely in use, this command is deprecated. Use `ip address` instead. |
| apt-get   | Used to install, configure, and remove packages on Debian and its derivatives. |
| iwconfig  | Used to display or configure wireless network card related information. |
| shutdown  | Shuts down the computer. shutdown can be instructed to perform several shutdown-related tasks, including restart, halt, put to sleep, or kick out all currently connected users. |
| passwd    | Used to change the password. If no parameters are provided, passwd changes the password for the current user. |
| cat       | Used to list the contents of a file and expects the file name as the parameter. |
| man       | Used to display the documentation for a specific command.            |

Many command line tools are included in Linux by default. To adjust the command operation, users can pass parameters and switches along with the command. The table lists a few of the most common commands related to files and directories.

| Command   | Description                                               |
|-----------|-----------------------------------------------------------|
| ls        | Displays the files inside a directory.                    |
| cd        | Changes the current directory.                             |
| mkdir     | Creates directories.                                      |
| cp        | Copies files and directories from source to destination.  |
| mv        | Moves or renames files and directories.                   |
| rm        | Removes files or directories.                              |
| grep      | Searches for specific strings of characters within a file or other commands outputs. |
| cat       | Lists the contents of a file and expects the file name as the parameter. |

For complete help on everything Kali Linux, open the Firefox web browser and go to [Kali Linux Documentation](https://www.kali.org/docs/). Here, you can perform a search by typing keywords in the search box or use the categories to find an answer by subject.

#### Step 2: Create and change directories.
In this step, you will use the `change directory (cd)`, `make directory (mkdir)`, and `list directory (ls)` commands.

**Note:** A directory is another word for a folder. The terms directory and folder are used interchangeably throughout this lab.

**Note:** There may be times when a command will not work because the user that is currently logged on does not have permission to perform it. To temporarily gain permission for the command, precede the command with `sudo`, which stands for super user "do". You may need to provide the password of a user that has permission to perform the command. Alternatively, you can use a terminal that has a higher permission level. This terminal is called Root Terminal Emulator and can be found in the panel by using the drop-down menu next to the terminal icon.

1. In a terminal, enter `pwd` at the prompt. This command will print the current working directory to the terminal.
   ```bash
   pwd
    ```


What is the current directory?

# Navigating the Kali Linux File System

## Changing Directories

Navigate to the `/home/kali` directory if it is not your current directory. Type:

```bash
cd /home/kali
 ```
to change the working directory.
```bash
cd /home/kali
 ```
Type ls -l at the command prompt to list the files and folders that are in the current working directory. The ls command stands for list. The -l option displays the file size, permissions, ownership, date of creation, and more for the files and folders.
```bash
 ls -l
  ```


## Understanding File Permissions
The output shows file and folder permissions in the leftmost column. The first character indicates if the item is a directory (d) or a file (-). The next nine characters represent permissions for the owner, group, and others in three sets of three characters.

The first set of three (rwx) represents the owner's permissions: r for read, w for write, and x for execute.
The second set of three represents the group's permissions.
The third set of three represents others' permissions.
Creating and Removing Directories
## To create a new directory called Test, use the mkdir command:
```bash
mkdir Test
 ```

To verify that the directory was created, use the ls command:
```bash
 ls
 ```
Test
To remove the directory, use the rmdir command:
```bash
 rmdir Test
  ```
To verify that the directory was removed, use the ls command again:
```bash
 ls
  ```
## Copying and Moving Files
To copy a file, use the cp command. For example, to copy gvm_admin_passwd.txt to a new file called backup_gvm_passwd.txt, use:

```bash
 cp gvm_admin_passwd.txt backup_gvm_passwd.txt
  ```
To verify the copy, list the files in the current directory:
```bash
 ls
  ```
gvm_admin_passwd.txt  backup_gvm_passwd.txt
To move a file, use the mv command. For example, to move gvm_admin_passwd.txt to the Documents directory, use:
```bash
 mv gvm_admin_passwd.txt Documents/
  ```
To verify the move, check the contents of the Documents directory:
```bash
 ls Documents/
  ```
gvm_admin_passwd.txt
Deleting Files
To delete a file, use the rm command. For example, to delete backup_gvm_passwd.txt, use:
```bash
 rm backup_gvm_passwd.txt
 ```
To verify that the file has been deleted, list the files in the current directory:
## Viewing File Content
To view the contents of a file, use the cat command. For example, to view gvm_admin_passwd.txt, use:
```bash
 ```
 cat gvm_admin_passwd.txt
If the file is long, consider using less or more for paginated viewing:
```bash
 less gvm_admin_passwd.txt
  ```
## Conclusion
Navigating the Kali Linux file system is essential for effective system management. By mastering basic commands such as cd, ls, mkdir, cp, mv, rm, and cat, you can efficiently manage files and directories in your environment.


