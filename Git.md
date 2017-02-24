# Git Notes. 
* The reference for this note is the 2nd edition of ***Pro Git*** by ***Scott Checon*** and ***Ben Straub***

## Introduction
---
### Version Control System (VCS)
* records the changes that happened to your files
* allows you to revert back to previous state of your files
* allows you to compare the changes that happened to your time over time
* **Types:**
    - _Local VCS_
        + a localized simple database system for your files
        + by adding up the time patches, it can re-create a previous state of files
    - _Centralized VCS_
        + files are stored in a single server for multiple user access. This allows collaboration
        + Features User hierarchy. There can be admins to control user access over some files
        + **Downside:**Since all files are stored in a single server, anything that will happen on the server will affect all user. Some problems include down server (disables collaboration), disk corruption (all files may be lost if no proper backups exist). These cons also applies to LVCS.
    - _Distributed VCS_
        + has the same features of CVCS, but every user fully replicates the repository. This solves the issues found in the other VCS
        + easily allows user to collaborate on multiple repositories

---
## Git
* Unlike other VCS which conceptually stores data as file-based changes, Git handles its data by taking a *snapshot* of the current state of the all files the moment you *commit* your changes. A reference to this snapshot is stored.
* If a file isn't modified, it will not create a new reference for this file, but instead will just link to the previous ref of the file
* Almost every Git operation is local
* Everything in Git is check-summed (using SHA-1 hash) before it is stored. Files and directories are referred to by their checksums.
* Having everything check-summed means that Git will know if a file/directory is modified. Using checksum is found even at the lowest level of Git, and this feature is integral to its philosophy. In fact, everything in its database is stored by the hash value of its contents.

### Three States in Git
* **Committed**
    - data is safely stored in your local git database (note that the term git database, database, and db are the same)
* **Modified**
    - file has been changed but not yet committed to your database
* **Staged**
    - file has been marked as modified and is ready to be included to the next snapshot

### Three Main Sections of a Git Project
* **.git directory**
    - this where Git stores the metadata and object database for your project
    - most important part of Git
    - copied when you clone a repository from another computer
* **Working Directory**
    - a single checkout of one version of the project
    - from the compressed database, files are pulled out and placed on disks to be used and modified
* **Staging Area**
    - a file that contains the information about what will happen to your next commit
    - also called *index*

### Basic Git Workflow
    1. You modify the files in your working directory
    2. You stage the files, adding snapshots of them to the staging area
    3. You do a commit, 

### NOTES
* A file is considered **commited** if a particular version is in the Git directory
* A file is **staged** if it has been modified and added to the staging area
* A file is **modified** if it has been modified but not yet staged

---
## First time Git setup
* Installing Git depends on your operating system.
* Browse http://git-scm.com/download to download and see how to install Git

### You Identity
`$ git config --global user.name "John Doe"`
`$ git config --global user.email johndoe@example.com`
* The above code gives Git the information to be included in the commits you created. After installing Git, setting your user name and email is very important.
* The `--global` option tells Git to use the information you pass on a *key* for every Git project you have. For specific proj, remove the `--global` option to override the name and email

### Check your Settings
* use `git config -l` (or --list) to view your current Git settings.
* use `git help <verb>` if you need help for a particular setting/command