## Path Traversal Attack

Path Traversal (also known as directory traversal) is a type of attack that involves gaining access to files and directories outside the root web directory. An attacker, using *dot-dot-slash (../)* characters or specifying an absolute path, can access arbitrary files or directories on the file system, including the application's code, configuration files, secrets, and critical system files.

### Protective Controls

* Where possible, avoid constructing file paths using data that comes from the user.
* Check user-input data against a whitelist.
* Normalize data before using it.

### Task

This code is vulnerable to a Path Traversal attack. Fix the vulnerability without changing the program's behavior.

### Additional Information
* https://owasp.org/www-community/attacks/Path_Traversal