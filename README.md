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

