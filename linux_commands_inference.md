# Linux System Administration: Lab Assignment

**Name:** Razal  
**Roll No:** 42  
**Username:** razal  

---

## Part 1: Directory Navigation and Basic Commands

**Command: `mkdir ev4`** **Path: `~/`** > **Inference:** Creates a new directory named `ev4` in your home folder. This initializes the project workspace.

**Command: `cd ev4`** **Path: `~/ev4`** > **Inference:** Changes the working directory to `ev4`. All subsequent relative commands will now occur inside this folder.

**Command: `mkdir 42`** **Path: `~/ev4`** > **Inference:** Creates a sub-directory named after your roll number (42) to keep your specific lab work isolated.

**Command: `cd 42`** **Path: `~/ev4/42`** > **Inference:** Navigates into the `42` directory. This is now the primary active directory for the session.

**Command: `cd -`** **Path: `~/ev4`** > **Inference:** The `-` (hyphen) is a shortcut that returns you to the **previous** directory you were in before the current one.

**Command: `cd -`** **Path: `~/ev4/42`** > **Inference:** Toggles back again. Using `cd -` repeatedly allows you to jump back and forth between two locations easily.

**Command: `cd .`** **Path: `~/ev4/42`** > **Inference:** The single dot `.` represents the **current directory**. This command effectively keeps you exactly where you are.

**Command: `cd ..`** **Path: `~/ev4`** > **Inference:** The double dot `..` represents the **parent directory**. This moves you one level up in the folder hierarchy.

**Command: `cd ~`** **Path: `/home/razal`** > **Inference:** The tilde `~` is a shell shortcut for the current user's **Home Directory**.

**Command: `cd /`** **Path: `/`** > **Inference:** Navigates to the **Root Directory**, which is the top-most level of the entire Linux filesystem.

**Command: `ls -l`** **Path: `/`** > **Inference:** Lists the contents of the root directory in **long format**, showing permissions, owners, and file sizes.

**Command: `cd media`** **Path: `/media`** > **Inference:** Moves into the `media` directory, typically used by the system to mount external drives like USB sticks.

**Command: `cd`** **Path: `/home/razal`** > **Inference:** Running `cd` without any arguments is a quick way to jump back to your **Home Directory** from anywhere in the system.

**Command: `pwd`** **Path: `/home/razal`** > **Inference:** **Print Working Directory** outputs the absolute path of your current location to the terminal.

**Command: `cd media`** **Path: `/home/razal`** > **Inference:** This command will likely fail with "No such file or directory" because there is no `media` folder inside your home; it exists at the root level.

**Command: `cd /media`** **Path: `/media`** > **Inference:** By adding the leading forward slash `/`, you are providing an **absolute path**, allowing you to jump straight to the system's media folder.

**Command: `ls -l`** **Path: `/media`** > **Inference:** Displays the long-format list of files/folders within the media directory.

**Command: `ls -al`** **Path: `/media`** > **Inference:** The `-a` flag stands for **all**. This reveals hidden files (those starting with a dot `.`) alongside regular files in long format.

---

## Part 2: File Operations and Cleanup

**Command: `cd ~/ev4/42`** **Path: `~/ev4/42`** > **Inference:** Returns to the roll number workspace to perform file tasks.

**Command: `mkdir emptydummy`** **Path: `~/ev4/42`** > **Inference:** Creates a directory named `emptydummy`.

**Command: `mkdir dummy`** **Path: `~/ev4/42`** > **Inference:** Creates a second directory named `dummy`.

**Command: `cd dummy`** **Path: `~/ev4/42/dummy`** > **Inference:** Enters the `dummy` folder.

**Command: `touch file1`** **Path: `~/ev4/42/dummy`** > **Inference:** Creates an empty file named `file1`. `touch` is commonly used to create new, empty files quickly.

**Command: `touch file2`** **Path: `~/ev4/42/dummy`** > **Inference:** Creates a second empty file named `file2`.

**Command: `ls -l`** **Path: `~/ev4/42/dummy`** > **Inference:** Confirms the creation of both files.

**Command: `rm -i file2`** **Path: `~/ev4/42/dummy`** > **Inference:** The `-i` flag enables **interactive mode**, asking the user for confirmation before deleting `file2`. This prevents accidental data loss.

**Command: `ls -l`** **Path: `~/ev4/42/dummy`** > **Inference:** Verifies that `file2` has been removed.

**Command: `cd ..`** **Path: `~/ev4/42`** > **Inference:** Moves back to the parent directory to test directory removal.

**Command: `rm emptydummy`** **Path: `~/ev4/42`** > **Inference:** **Error:** "cannot remove 'emptydummy': Is a directory". The `rm` command by itself is only intended for files.

**Command: `rmdir emptydummy`** **Path: `~/ev4/42`** > **Inference:** Successfully removes the folder because `rmdir` is specifically built to remove **empty** directories.

**Command: `rmdir dummy`** **Path: `~/ev4/42`** > **Inference:** **Error:** "failed to remove 'dummy': Directory not empty". `rmdir` will not delete a directory that contains files (like `file1`) as a safety precaution.

**Command: `rm -r dummy`** **Path: `~/ev4/42`** > **Inference:** The `-r` (recursive) flag tells the system to delete the directory **and** all of its contents (files and subfolders).

---

## Part 3: Redirection and Search

**Command: `cat >file1.txt`** (Input: My first line)  
**Path: `~/ev4/42`** > **Inference:** Uses `>` to redirect standard input into a new file. This creates `file1.txt` with the text you type. (Press `Ctrl+D` to save).

**Command: `cat >file2.txt`** (Input: Hello Second line)  
**Path: `~/ev4/42`** > **Inference:** Creates `file2.txt` with new content.

**Command: `cat >file3.txt`** (Input: Hello line)  
**Path: `~/ev4/42`** > **Inference:** Creates `file3.txt` for the next concatenation step.

**Command: `cat file1.txt file2.txt > file_combined.txt`** **Path: `~/ev4/42`** > **Inference:** Concatenates (joins) the contents of `file1` and `file2` and redirects the combined output into a new file named `file_combined.txt`.

**Command: `cat file_combined.txt`** **Path: `~/ev4/42`** > **Inference:** Displays the combined text. **Pro Tip:** Use **Tab Autocomplete** by typing `cat file_c` and pressing `Tab` to finish the filename automatically.

**Command: `cat file3.txt >> file_combined.txt`** **Path: `~/ev4/42`** > **Inference:** The `>>` operator **appends** data. Instead of overwriting `file_combined.txt`, it adds the content of `file3.txt` to the end of the existing file.

**Command: `grep -i hello file*`** **Path: `~/ev4/42`** > **Inference:** Searches for the string "hello" inside all files starting with "file". The `-i` flag makes the search **case-insensitive**.

**Command: `cp file1.txt ~/ev4`** **Path: `~/ev4/42`** > **Inference:** Copies `file1.txt` to the parent folder `ev4`. The original file remains in the current directory.

**Command: `mv file_combined.txt combined`** **Path: `~/ev4/42`** > **Inference:** Renames `file_combined.txt` to `combined`. The `mv` command is used for both moving files to new locations and renaming them.

---

## Part 4: Permissions and User Management



**Command: `chmod u+x combined`** **Path: `~/ev4/42`** > **Inference:** Modifies permissions to add **eXecute** (x) rights for the **User** (u) who owns the file.

**Command: `chmod g-r combined`** **Path: `~/ev4/42`** > **Inference:** Modifies permissions to remove **Read** (r) rights from the **Group** (g). Members of the same group can no longer read the file.

**Command: `chmod 777 combined`** **Path: `~/ev4/42`** > **Inference:** Grants full Read, Write, and Execute permissions to the User, Group, and Others.  
> **The 421 Numeric Logic:** > * **4** = Read | **2** = Write | **1** = Execute.  
> * **7** (4+2+1) = Full Access.  
> * Position 1: User | Position 2: Group | Position 3: Others.

**Command: `sudo useradd alice`** **Path: `~/ev4/42`** > **Inference:** Adds a new user named `alice` to the system. Requires `sudo` (SuperUser Do) for administrative access.

**Command: `sudo passwd alice`** **Path: `~/ev4/42`** > **Inference:** Sets the password for the newly created user `alice`.

**Command: `sudo userdel alice`** **Path: `~/ev4/42`** > **Inference:** Deletes the user `alice` from the system.

---

## Part 5: Messaging Functionality

**Functionality: `write username`** > **Inference:** The `write` command allows you to send a message to another user's terminal in real-time. Once the command is run, everything you type is sent to that user until you terminate the session with `Ctrl+D`.

**Functionality: `mesg y/n`** > **Inference:** This command controls your terminal's "write" access.  
> * `mesg y` (Yes) allows other users to send you messages via `write`.  
> * `mesg n` (No) blocks other users from writing to your terminal, essentially acting as a "Do Not Disturb" mode.

---
Would you like me to explain how to manage these permissions using symbolic notation (like `a+rwx`) instead of numeric?
