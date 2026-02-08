# Linux Basic Commands Inference

---

### 1. Setup and Directory Creation
* `mkdir ev4` : Created a new directory named ‘ev4’.
* `cd ev4` : Changed current directory to ‘ev4’.
    * **Resultant Path:** `/home/athul/ev4`
* `mkdir 16` : Created a directory named '16' (my roll number).
    * **Resultant Path:** `/home/athul/ev4`
* `cd 16` : Entered the directory '16'.
    * **Resultant Path:** `/home/athul/ev4/16`

### 2. Navigation Commands
* `cd -` : Switched back to the previous directory (`ev4`).
    * **Resultant Path:** `/home/athul/ev4`
* `cd -` : Toggled back to the directory I was just in (`16`).
    * **Resultant Path:** `/home/athul/ev4/16`
* `cd .` : No change occurred (represents current directory).
    * **Resultant Path:** `/home/athul/ev4/16`
* `cd ..` : Moved up one level to the parent directory (`ev4`).
    * **Resultant Path:** `/home/athul/ev4`
* `cd ~` : Moved immediately to my Home directory (`athul`).
    * **Resultant Path:** `/home/athul`
* `cd /` : Moved to the Root directory.
    * **Resultant Path:** `/`
* `ls -l` : Listed files in Root.
    * **Resultant Path:** `/`
* `cd media` : Entered the 'media' directory inside Root.
    * **Resultant Path:** `/media`
* `cd` : Returned to my Home directory.
    * **Resultant Path:** `/home/athul`
* `pwd` : Printed the absolute path of the current directory.
    * **Output:** `/home/athul`
* `cd media` : Error ("No such file"). I stayed in the current directory.
    * **Resultant Path:** `/home/athul`
* `cd /media` : Successfully entered media using absolute path.
    * **Resultant Path:** `/media`
* `ls -l` : Listed contents of media.
    * **Resultant Path:** `/media`
* `cd ~/ev4/16` : Navigated directly back to my work folder.
    * **Resultant Path:** `/home/athul/ev4/16`

### 3. File and Directory Management
*(Current Path: `/home/athul/ev4/16`)*

* `mkdir emptydummy` : Created folder 'emptydummy'.
* `mkdir dummy` : Created folder 'dummy'.
* `cd dummy` : Entered the dummy folder.
    * **Resultant Path:** `/home/athul/ev4/16/dummy`
* `touch file1` : Created empty file 'file1'.
* `touch file2` : Created empty file 'file2'.
* `ls -l` : Checked that files exist.
* `rm -i file2` : Deleted 'file2' after confirmation.
* `cd ..` : Moved back to parent directory (`16`).
    * **Resultant Path:** `/home/athul/ev4/16`
* `rm emptydummy` : Failed (Error: Is a directory).
* `rmdir emptydummy` : Successfully removed the directory because it was empty.
* `rmdir dummy` : Failed (Error: Directory not empty).
* `rm -r dummy` : Recursively removed the 'dummy' directory and the files inside it.

### 4. File Content and Redirection (I/O)
*(Current Path: `/home/athul/ev4/16`)*

* `cat > file1.txt` : Created file with text 'My first line'.
* `cat > file2.txt` : Created file with text 'Hello Second line'.
* `cat > file3.txt` : Created file with text 'Hello line'.
* `cat file1.txt file2.txt > file_combined.txt` : Combined file1 and file2 into a new file.
* `cat file_combined.txt` : Displayed combined content.
* `cat file3.txt >> file_combined.txt` : Appended file3 to the combined file.
* `cat file_combined.txt` : Displayed total content (File1 + File2 + File3).
* `grep -i hello file*` : Listed lines containing "hello" from all files.
* `cp file1.txt ~/ev4` : Copied file to the parent folder (`/home/athul/ev4`).
* `mv file_combined.txt combined` : Renamed file to 'combined'.

### 5. Permissions (chmod)
**Method A: Symbolic Mode Examples**
* `chmod u+x file.sh` : Added execute permission for the owner (user).
* `chmod g-w file.txt` : Removed write permission for the group.
* `chmod a+r file.txt` : Added read permission for everyone (all users).
* `chmod u=rwx,g=rx,o=r myfile` : Set exact permissions: Owner gets read/write/execute, Group gets read/execute, Others get read only.

**Method B: Numeric (Octal) Mode Examples**
* `chmod 754 file.txt` : Set permissions to Owner (7=rwx), Group (5=r-x), and Others (4=r--).
* `chmod 600 file.txt` : Set permissions to read/write for Owner only (6), with no permissions for Group or Others (00).

* `chmod u+x combined` : Added execute permission for the owner to the file 'combined'.
    * *Observation:* Checked with `ls -l`, the owner permissions changed to include 'x'.
* `chmod g-r combined` : Removed read permission for the group from 'combined'.
    * *Observation:* The 'r' was removed from the group section in the `ls -l` output.
* `chmod 777 combined` : Changed permissions to `rwxrwxrwx` (777).
    * *Observation:* This granted full read, write and execute access to User, Group and Others.

### 6. User Management (sudo)
* `sudo useradd alice` : Created a new user named 'alice' (required admin password).
* `sudo passwd alice` : Set a login password for the new user 'alice'.
* `sudo userdel alice` : Deleted the user account 'alice' from the system.

### 7. Communication
* `write alice` : Initiated a real-time message to user 'alice'.
    * *Observation:* If 'alice' is logged in, the message appears directly on their terminal.
* `mesg y` / `mesg n` : Enabled or disabled the ability to receive messages from other users.