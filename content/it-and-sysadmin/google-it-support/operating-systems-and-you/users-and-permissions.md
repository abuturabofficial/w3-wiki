---
title: Users and Permissions
date: 2022-10-07 16:57:00 +0500
weight: 2
collapsibleMenu: true
alwaysOpen: false
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
---

## **Users and Groups**

### User, Administrators, and Groups

- Two different types of users
  + Standard user
  + Admin
- Users are put into different groups, according to level of permissions and ability to do certain tasks.

### 1) Standard user
  
  One who is given access to a machine but has restricted access to do things like install software or change certain settings.

### 2) Administrator (Admin)
  
  A user that has complete control over a machine.

### **Windows: View User and Group Information**

- To view user and groups information, **Computer management** application is used.
  + In an Enterprise environment, you can manage multiple machines in something called a domain.
- You can manage admin tasks while being logged in as a normal user. This is done through **User Access Control (UAC)** prompt.

#### Windows domain
  
  A network of computers, users, files, etc. that are added to a central database.

#### User Access Control (UAC)
  
  A feature on Windows that prevents unauthorized changes to a system.

### Windows: View User and Group Information using CLI

- To check all users on the system and either admin access enabled or not.
  
  ```terminal
  Get-LocalUser
  ```

- To get all the groups present on a local machine
  
  ```terminal
  Get-LocalGroup
  ```

- To check members of an individual group
  
  ```terminal
  Get-LocalGroupMember Administrator
  ```

### Linux: Users, Superuser and Beyond

- To see all groups, who are their members
  
  ```terminal
  cat /etc/group
  ```
  
  + It shows information something like this
  
  ```console
  sudo:x:27:user1, user2, user3
  ```
  
  + First field is a group name
  + 2nd is password but redacted
  + 3rd is a group id
  + 4th is a list of users in a group
	- To view all users on a machine

```terminal
cat /etc/passwd
```

  + Most of these accounts are system processes running the computer.

### Windows: Passwords

- An admin shouldn't know the password of the user using it.
- But as an admin to manage users passwords, **computer management** application is used.
- To change user's password from CLI
  
  ```terminal
  net user <username> <password>
  ```

- To interactively change the password
  
  ```terminal
  net user <username> *
  ```

- To force user itself to change its password on next logon
  
  ```terminal
  net user <username> /logonpasswordchg:yes
  ```

### Linux: Passwords

- To change a password on Linux
  
  ```terminal
  sudo passwd <username>
  ```

- To force a user to change his/her password
  
  ```terminal
  sudo passwd -e <username>
  ```

### Windows: Adding and Removing Users

- To add users
  
  ```terminal
  net user <username> * /add
  ```

- To add a new user and forcing him/her to change its password on new logon
  
  ```terminal
  net user <username> password /add /logonpasswordchg:yes
  ```

- To remove a local user
  
  ```terminal
  net user <username> /del
  ```
  
  OR
  
  ```terminal
  Remove-LocalUser <username>
  ```

### Linux: Adding and Removing Users

- To add a user
  
  ```terminal
  sudo useradd <username>
  ```

- To remove a user
  
  ```terminal
  sudo userdel <username>
  ```

## **Permissions**

### Windows: File Permissions
  
On Windows, files and directory permissions assigned using Access Control Lists or **ACLs**. Specifically, we're going to be working with Discretionary Access Control Lists or **DACLs**.
- Windows files and folders can also have **System Access Control Lists or SACLs** assigned to them.
  + SACLs are used to tell Windows that it should use an event log to make a note of every time someone accesses a file or folder.
- Windows allow certain permissions to be set for files and folders.
  + Read
  > The Read permission lets you see that a file exists, and allow you to read its contents. It also lets you read the files and directories in a directory.
  + Read & Execute
  > The Read & Execute permission lets you read files, and if the file is an executable, you can run the file. Read & Execute includes Read, so if you select Read & Execute, Read will be automatically selected.
  + List folder contents
  > List folder contents is an alias for Read & Execute on a directory. Checking one will check the other. It means that you can read and execute files in that directory.
  + Write
  > The Write permission lets you make changes to a file. It might be surprising to you, but you can have write access to a file without having read permission to that file!
  + The Write permission also lets you create subdirectories, and write to files in the directory.
  + Modify
  > The Modify permission is an umbrella permission that includes read, execute, and write.
  + Full control
  > A user or group with full control can do anything they want to the file! It includes all the permissions to Modify, and adds the ability to take ownership of a file and change its **ALCs**
- To view file permissions in a CLI, **Improved change ACLs** command `icacls` is used
  + To view more options and their explanation
  
  ```terminal
  icacls /? #icacls is a old dos command
  ```
  
  ```terminal
  icacls <filepath>
  ```

### Linux: File Permissions

- There are three different permissions you can have on Linux
  + Read – This allows someone to read the contents of a file or folder.
  + Write – This allows someone to write information to a file or folder.
  + Execute – This allows someone to execute a program.

- To see file permissions
  
  ```terminal
  ls -l <filepath>
  ```

## **Windows: Modifying Permissions**

- To modify permissions
  
  ```terminal
  icacls <filepath> /grant 'Everyone:(OI)(CI)(R)'
  ```

- Everyone gives permissions to literally everyone of the computer including guest users, to avoid this
  
  ```terminal
  icacls <filepath> /grant 'Authenticated Users:(OI)(CI)(R)'
  ```

- To remove permissions to everyone group
  
  ```terminal
  icacls <filepath> /remove Everyone
  ```

- To see the given permissions
  
  ```terminal
  icacls <filepath>
  ```

#### Guest users
  
  This is a special type of user that's allowed to use the computer without a password. Guest users are disabled by default. You might enable them in very specific situations.

### Linux: Modifying Permissions

- The permissions are changed by `chmod` command
  
  + The owner, which is denoted by a “u”
  
  + The group the file belongs to, which is denoted a “g”
  
  + Or other users, which is denoted by an “o”

- To change execute permission
  
  ```terminal
  chmod u+x <filepath>
  ```
  
  ```terminal
  chmod u-x <filepath>
  ```

- To add/remove multiple permissions to file
  
  ```terminal
  chmod u+rx <filepath>
  ```

- To change permissions for owner, the group, and others
  
  ```terminal
  chmod ugo+r <filepath>
  ```

- This format of changing permissions is called **symbolic format**.
- Other method is changing permissions numerically, which is faster.
- The numerical equivalent of **rwx** is:
  + 4 for read or r
  + 2 for write or w
  + 1 for execute or x

- To change permissions numerically
  
  ```terminal
  chmod 745 <filepath>
  ```
  
  + 1st is for user
  + 2nd is for group
  + 3rd is for other

- To change ownership of a file
  
  ```terminal
  sudo chown <username> <filepath>
  ```

- To change group of a file
  
  ```terminal
  sudo chgrp <username> <filepath>
  ```

### **Windows: Special Permissions**

- The permissions we looked so far are called **simple permissions**.

#### Simple Permissions
  
  Simple permissions are actually sets of special, or specific permissions.
- When you set the **Read** permission on a file, you're actually setting multiple special permissions.
- To see special permissions, `icacls` command is used
  
  ```terminal
  icacls <filepath>
  ```

### Linux: SetUID, SetGID, Sticky Bit

- SetUID is a special permission, use to allow a file to be run as the owner of the file.
- To apply SetUID
  
  ```terminal
  sudo chmod u+s <filepath>
  ```

- The numerical value for SetUID is **4**
  
  ```terminal
  sudo chmod 4755 <filepath>
  ```

- SetGID is a special permission which allow a user to run a particular file in a group member though the user isn't part of that group.
  
  ```terminal
  sudo chmod g+s <filepath>
  ```

- The numerical value for SetGID is **2**.
  
  ```terminal
  sudo chmod 2755 <filepath>
  ```

- Sticky Bit is a special permission, use to allow anyone to write to a file or folder but can't delete it.
  
  ```terminal
  sudo chmod +t <filepath>
  ```

- The numerical value for Sticky bit is **1**.
  
  ```terminal
  sudo chmod 1755 <filepath>
  ```
