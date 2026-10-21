# Linux for Cloud & DevOps — Day 1

## Objective

Learn Linux filesystem navigation, directory structure, paths, and basic file management.

## Commands Practiced

| Command        | Purpose                                   |
| -------------- | ----------------------------------------- |
| `pwd`          | Display the current working directory     |
| `ls`           | List directory contents                   |
| `ls -l`        | Display a detailed listing                |
| `ls -a`        | Show hidden entries                       |
| `ls -la`       | Show hidden entries in long format        |
| `ls /`         | List entries in the root directory        |
| `ls -ld /root` | Display the directory's own details       |
| `cd`           | Change the working directory              |
| `cd ..`        | Move to the parent directory              |
| `cd ~`         | Go to the current user's home directory   |
| `cd -`         | Return to the previous working directory  |
| `file`         | Identify a file's type                    |
| `mkdir`        | Create a directory                        |
| `mkdir -p`     | Create nested directories                 |
| `touch`        | Create an empty file if it does not exist |
| `find`         | Search for files and directories          |

## Practical Exercises

* Explored the Linux root directory `/`.
* Inspected home directories and directory permissions.
* Practiced absolute and relative paths.
* Created a `linux-day1` practice directory.
* Created nested directories using `mkdir -p`.
* Created files and practiced searching with `find`.

## Key Learnings

* `/` is the top-level directory of the Linux filesystem.
* `/root` is the root user's home directory.
* `/home/nishant` is the normal user's home directory.
* File ownership depends on the user that creates the file, not simply the directory where it is created.
* Root privileges provide broad administrative access; normal users have access according to permissions.

## Next Steps

Continue practicing Linux commands, permissions, users, processes, and Bash scripting.

---

Learning in public: building practical Linux skills for a Cloud & DevOps career.


## Day 2 — File Operations and Permissions

### Commands Practiced
- cat, echo, >, >>
- head, tail, less
- cp — copy files
- mv — move or rename files
- rm — delete files
- chmod — change permissions
- ls -l — inspect file permissions

### Key Learnings
- `>` replaces file content; `>>` appends content.
- `cp` creates an independent copy.
- `mv` moves or renames files.
- `chmod 600` gives the owner read/write access only.
- `chmod 644` gives the owner read/write access and others read-only access.


# Day 4 — Linux Users and Groups

## Objective

Learn how Linux manages users, groups, user information, and administrative permissions.

## 1. Identifying the Current User

```bash
whoami
id
groups
```

* `whoami` — Displays the current username.
* `id` — Displays the current user's UID, GID, and group memberships.
* `groups` — Displays the groups to which a user belongs.

## 2. Reading User Information

```bash
getent passwd
getent passwd "$USER"
cat /etc/passwd
```

* `getent passwd` — Retrieves user entries from configured system databases.
* `getent passwd "$USER"` — Retrieves the current user's entry.
* `cat /etc/passwd` — Displays the local user account database.

### Fields in `/etc/passwd`

A typical entry looks like this:

`username:x:1000:1000:User Info:/home/username:/bin/bash`

The fields represent:

1. Username
2. Password placeholder (`x`)
3. User ID (UID)
4. Primary Group ID (GID)
5. User information (GECOS)
6. Home directory
7. Login shell

## 3. Reading Group Information

```bash
getent group
getent group sudo
cat /etc/group
groups "$USER"
```

* `getent group` — Retrieves group entries from configured system databases.
* `getent group sudo` — Checks the sudo group's entry.
* `cat /etc/group` — Displays the local group database.
* `groups "$USER"` — Displays the specified user's group memberships.

## 4. Checking Sudo Permissions

```bash
sudo -l
```

This displays the sudo privileges available to the current user.

**Important:** Membership in the `sudo` group is one way to receive administrative privileges. Sudo permissions may also be configured through sudoers rules.

## 5. User Management Commands

```bash
sudo useradd batman
sudo passwd batman
sudo usermod -aG sudo batman
```

* `useradd` — Creates a user account.
* `passwd` — Sets or changes a user's password.
* `usermod -aG` — Adds a user to a supplementary group.

**Important:** The commands above can modify your system. Do not run them on your main system merely for practice. Use a disposable virtual machine or a controlled lab environment.

## 6. Group Management Commands

```bash
sudo groupadd developers
sudo gpasswd -a batman developers
sudo gpasswd -d batman developers
```

* `groupadd` — Creates a group.
* `gpasswd -a` — Adds a user to a group.
* `gpasswd -d` — Removes a user from a group.

Run these only in an appropriate practice environment, and only after confirming the intended user and group.

## 7. Searching for Specific Entries

```bash
grep '^developers:' /etc/group
getent group developers
```

* `grep` — Searches text for matching patterns.
* `getent group developers` — Retrieves the specified group's entry.

## 8. Key Concepts Learned

* Linux users are identified by UIDs.
* Groups are identified by GIDs.
* Every user has a primary group and may have supplementary groups.
* `/etc/passwd` stores local user account information.
* `/etc/group` stores local group information.
* `getent` queries system databases through the configured Name Service Switch (NSS).
* `sudo` allows authorized users to execute commands with elevated privileges.
* The `-a` option in `usermod -aG` preserves existing supplementary group memberships while adding another group.

## 9. Practice Tasks

Complete these tasks in your Linux lab:

* [ ] Display the current username.
* [ ] Display the current user's UID and GID.
* [ ] Find your user entry using `getent passwd`.
* [ ] Identify your primary group.
* [ ] Check whether your user belongs to the `sudo` group.
* [ ] Display the local group database.
* [ ] Check your available sudo permissions.
* [ ] Explain the seven fields in a `/etc/passwd` entry.
* [ ] Explain the difference between `getent passwd` and `cat /etc/passwd`.
* [ ] Explain the difference between a primary group and a supplementary group.

## 10. Day 4 Summary

Today, I studied Linux user accounts, group memberships, user and group databases, and sudo permissions. I practised commands for inspecting account information and learned how Linux identifies users and groups.

**Next:** Review the commands, complete the practice tasks, and commit the Day 4 progress to GitHub.

