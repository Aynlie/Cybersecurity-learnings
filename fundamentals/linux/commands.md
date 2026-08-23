 # Linux Commands I Used in My Lab

 These are the commands I used while setting up and troubleshooting my
 Ubuntu Server and Kali Linux virtual machines. I use them to understand
 where I am, inspect the filesystem, and manage packages.

 ## Confirming My Session

 ```bash
 whoami
 pwd
 ls -la
 ```

 - `whoami` shows the account currently running the shell.
 - `pwd` prints the current working directory.
 - `ls -la` lists files, including hidden files, with detailed metadata.

 ## Moving Around the Filesystem

 ```bash
 ls
 cd /path/to/directory
 cd ..
 cd ~
 ```

 `cd ..` moves to the parent directory, while `cd ~` returns to the current
 user's home directory. I use `pwd` after changing directories when I need to
 verify the location before running another command.

 ## Package Management with APT

 ```bash
 sudo apt update
 sudo apt upgrade -y
 ```

 `apt update` refreshes package metadata. `apt upgrade -y` installs available
 updates and automatically answers yes to the confirmation prompt.

 On my Ubuntu Server VM, the regional Philippines mirror returned a `403
 Forbidden` error. Modern Ubuntu installs commonly keep the mirror
 configuration in `/etc/apt/sources.list.d/ubuntu.sources`, so I replaced the
 regional hostname with the global archive mirror:

 ```bash
 sudo sed -i 's/ph.archive.ubuntu.com/archive.ubuntu.com/g' /etc/apt/sources.list.d/ubuntu.sources
 sudo apt update
 sudo apt upgrade -y
 ```

 `sed -i` edits the file in place. In this substitution, `s` means substitute
 and `g` means replace every matching occurrence on a line.

 ## Inspecting APT Sources

 ```bash
 cat /etc/apt/sources.list.d/ubuntu.sources
 ```

 On newer Ubuntu versions, `/etc/apt/sources.list` may be empty because the
 active sources use deb822 format in `ubuntu.sources` instead.

 ## What I Am Practicing

 My next goal is to become comfortable combining these small commands: check
 the current user and directory, inspect files with `ls -la`, then make a
 targeted change and verify the result.
