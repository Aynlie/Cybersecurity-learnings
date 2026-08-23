 # Linux File Permissions

 File permissions control who can read, modify, or execute a file. Linux
 permissions are checked for three classes of users:

 - **Owner** — the user who owns the file
 - **Group** — users assigned to the file's group
 - **Others** — everyone else

 ## Reading Permission Output

 ```bash
 ls -l filename
 ```

 A result beginning with `-rwxr-x---` contains one file-type character followed
 by three permission groups:

 ```text
 - rwx r-x ---
	 |   |   |
	 |   |   +-- others: no permissions
	 |   +------ group: read and execute
	 +---------- owner: read, write, and execute
 ```

 For regular files, `r` means read, `w` means write, and `x` means execute.
 A dash means that permission is not granted.

 ## Changing Permissions with chmod

 Symbolic mode makes the intended change explicit:

 ```bash
 chmod u+x script.sh
 chmod g-w shared.txt
 chmod o-r private.txt
 ```

 Here, `u`, `g`, and `o` mean owner, group, and others. The operators `+` and
 `-` add or remove a permission.

 Numeric mode represents read, write, and execute as `4`, `2`, and `1`:

 ```bash
 chmod 750 script.sh
 ```

 This gives the owner `rwx` (`7`), the group `r-x` (`5`), and others no access
 (`0`). I verify a permission change with `ls -l` instead of assuming it
 worked.

 ## Changing Ownership with chown

 ```bash
 sudo chown username filename
 sudo chown username:groupname filename
 ```

 `chown` changes the owner, and the `username:groupname` form changes both the
 owner and group. Changing ownership usually requires `sudo`, especially for
 files outside the current user's home directory.

 ## Lab Safety Notes

 I should make permission changes on a test file first and inspect the result
 with `ls -l`. Broad commands such as `chmod -R` can change an entire
 directory tree, so they should only be used when the target and intended
 permissions are understood.
