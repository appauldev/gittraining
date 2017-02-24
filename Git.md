# Git Notes

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
