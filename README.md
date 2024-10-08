VERSION CONTROL SYSTEM
----------------------

1. version is the particular state of the application. From building phase to maintainence phase you keep on adding/removing features delivering a new particular state of a software -> version of the S/W.

2. VCS -> it is a tool to manange versions & changes in a software.

3. It helps us to track changes.

4. manage version and their rollback.

5. compare the changes in versions.

6. log the changes.

7. collaboration -> allows multiple people to work on the same project efficiently.

8. VCS is also called Source Control Management Tool.

9. Features of Git:
	1. Git is different than Github.
	2. Open Source.
	3. Easily maintains code integrity -> if two people are working on the same version -> they will see the same piece of the code.
	4. Secure -> changes that you are making in the project are secure -> they are not going to be lost untill you delete them specifically.
	5. Gives you a lot of flexibility.



---------------------------------------------------------------------------------------------------------------

VERSION CONTROL SYSTEM -> Commands -> USE GIT BASH
----------------------

1. `git init` -> first command that you execute to initialize empty git repository/folder that will be managed by git.
								#Repository -> folder that will be managed by git to track any change that you make in the repository.

2. `ls` -> to see the files

3. `ls -a` -> to see  the all files including the hidden files also.

4. `ls -l` -> to see the file/folder with descriptions/permissions

5. `pwd` -> present working directory

6. `whoami` -> to display the name of the user.

7. `touch fileName` -> to create an empty file in the folder.

8. `mkdir folderName` -> to create a new folder.

9. `cd /path` -> to change the directory or directory path

##########################################################################################

In a folder structure, `.` and `..` are shorthand representations of directories that help with navigating the filesystem:

1. **`.` (Single dot)**: Refers to the **current directory**.
   - It represents the directory you are currently in.
   - Example usage:  
     - `./file.txt`: Refers to a file named `file.txt` in the current directory.
     - `./script.sh`: Runs a script located in the current directory.

2. **`..` (Double dots)**: Refers to the **parent directory**.
   - It allows you to move up one level in the directory hierarchy.
   - Example usage:
     - `cd ..`: Moves you to the parent directory of your current location.
     - `../file.txt`: Refers to a file named `file.txt` in the parent directory.

### Example:

Let's say you're in the directory `/home/user/docs`:

- `.` would refer to `/home/user/docs`.
- `..` would refer to `/home/user`.

These shortcuts are extremely useful in navigating and manipulating files within a file system without needing to type the full directory path every time.



##############################################################################################

10. `New Version` -> means a new commit. If we have to create a new version, we have to create a new commit.

11. `Untracked (U)` -> means git is not tracking it and git has no knowledge of the changes that that you made in that untracked file and folder.

12. `git add <fileName>` -> You say to git to add the file to the next version. Now git will start trackig the changes in the file if you make. It is no longer untracked now.

13. `git status` -> to see status of all the untracked(U), added(A), and modified(M) files.

##########################################################################################
The `git status -s` (or `git status --short`) command provides a **concise summary** of the status of your working directory and staging area in Git. It shows changes in a **shortened format** compared to the usual verbose output of `git status`. Here's how the output is formatted:

### Output Format:
The output consists of two columns:
- The **left column** represents the **staging area** (whether the changes have been added with `git add`).
- The **right column** represents the **working directory** (whether the changes have been made but not yet staged).

### Key Symbols:
- **`??`**: Untracked files (files that are not yet tracked by Git).
- **`A`**: A file has been added to the staging area (staged for commit).
- **`M`**: Modified file.
  - **Left column (`M`)**: The file is modified and staged for commit.
  - **Right column (`M`)**: The file is modified but not yet staged.
- **`D`**: File deleted.
  - **Left column (`D`)**: The file is staged for removal.
  - **Right column (`D`)**: The file has been deleted but not yet staged.
- **`R`**: Renamed file (shows the old file name).
- **`C`**: Copied file (shows the original file it was copied from).

### Example:
```bash
$ git status -s
 M file1.txt
M  file2.txt
A  newfile.txt
?? untrackedfile.txt
 D deletedfile.txt
```

**Explanation**:
- ` M file1.txt`: File `file1.txt` is **modified** but not staged.
- `M  file2.txt`: File `file2.txt` is **modified** and staged for commit.
- `A  newfile.txt`: File `newfile.txt` is **staged** for commit as a new file.
- `?? untrackedfile.txt`: File `untrackedfile.txt` is **untracked** (not added to the Git repository yet).
- ` D deletedfile.txt`: File `deletedfile.txt` is staged for **deletion**.

This short format is useful for quickly seeing the current state of your working directory.

###############################################################################################


14. `git add .` -> to add all the files to the staging area of the git i.e. tracked and ready to be commited.

15. `git commit -m "message"` -> to create the version of the code by committing it.
					-m -> stands for the "message"

16. `git config --global --list` -> to list the global config.
			user.name=John Doe
			user.email=johndoe@example.com
			core.editor=code
			color.ui=true
			git config --global user.name
			git config --global user.email
#######################################################################################################

The `git log` command is used to view the **commit history** in a Git repository. It displays a list of commits made to the repository, along with details such as the commit hash, author, date, and commit message.

### Basic Command:
```bash
git log
```

### Information Displayed:
Each commit entry typically shows the following details:
- **Commit hash**: A unique SHA-1 identifier for the commit.
- **Author**: The person who made the commit.
- **Date**: When the commit was made.
- **Commit message**: A brief message describing the commit.

### Example Output:
```bash
commit e5d13a37879dbb23cd8b1c6b46aeabc453af74ef
Author: John Doe <john.doe@example.com>
Date:   Fri Sep 8 14:56:21 2023 +0530

    Fixed bug in the payment gateway module.

commit 8a35ac369b4b1a489d3895c23781fdfa6b5de8ef
Author: Jane Smith <jane.smith@example.com>
Date:   Thu Sep 7 09:42:11 2023 +0530

    Added new feature for user authentication.
```

### Common Options:
- **`--oneline`**: Shows each commit on a single line, displaying the abbreviated commit hash and the commit message.
  ```bash
  git log --oneline
  ```

  Example output:
  ```bash
  e5d13a3 Fixed bug in the payment gateway module
  8a35ac3 Added new feature for user authentication
  ```

- **`--graph`**: Displays a text-based graphical representation of the commit history, which is useful for understanding branching and merging.
  ```bash
  git log --graph
  ```

- **`--stat`**: Shows a summary of changes made in each commit (number of files changed, insertions, deletions).
  ```bash
  git log --stat
  ```

- **`-p`**: Shows the full diff (changes) introduced in each commit.
  ```bash
  git log -p
  ```

- **`--author="name"`**: Filters commits by a specific author.
  ```bash
  git log --author="John Doe"
  ```

- **`--since` and `--until`**: Filters commits based on time.
  ```bash
  git log --since="2 weeks ago"
  git log --until="2023-09-01"
  ```

These options can be combined to refine the log output. For example:
```bash
git log --oneline --graph --since="1 month ago"
```
q: Quit and return to the terminal.

###########################################################################################################################################

17. `git add file1 file2 file3...` -> to stage the specific files.

18. `cat fileName` -> to see the content of the file.

19. `cat > fileName` -> to create file and write the content in the file.
												$ cat > file.txt
												This is the first line.
												This is the second line.
												Ctrl + D   # This saves and exits
												cat >> fileName -> to append the content of the file.

20. `git remote add origin https://github.com/Adarsh097/version-control-sanket.git` -> we are adding our local repository to remote location & origin: as shorthand reference of the repository weblink

21. `git push origin master` -> to push the changes to github remote repository.

22. `cd ..` -> to go to the parent directory of he current directory.


- GitHub is online platform having  the power of git (version control system) allows to user collaborate, bug fixing and managing the project online.
- GitHub, GitLab, Git Bucket are online hosting/uploading platform for the project management and collaboration.


# Part-2

Q1. `How exactyly internally git store data?`
		- internally git is a <key,value> data store.
		- key -> hash of the data we want to store.
			- key -> 40 digits hexadecimal value. (SHA-1) HASHCODE
			- for same data, this hash will be same.
		- value -> actual data
			- value -> git stores the compressed data in a blob and some more metadata in  the header
			- BLOB -> Big Large Object data type.
			
2. `rm -rf` -> recursively and forcefully remove the non-empty folder and its sub-directories.

3. LEARN HOW TO INSTALL TREE TO VIEW THE FOLDER STRUCTURE IN BETER WAY.

4. when we do git add filename -> git stores the BLOB of the file in the /object folder inside
	 the /.git folder where: key-> first two hex-value of the hashcode and remaining 38-values
	 stores the actual data of the file.
	
5. Inside Git, content is stored only once. If you have to files with the same content then,
	 both the files refer to only single BLOB for the content. There will be only one KEY-VALUE
	 BLOB for both the files.

Q6. `HOW GIT HANDLES THE DIRECTORIES?`
		 - Git use Tree object to store infomation about directories and their content.
		 - Tree are directed Graph.
		 - Tree contains pointers to other blobs and trees.
		 
7. Git internally does a lot of optimisation, the objects are store in compressed form.

8. Git mainly stores data about the changes & algorithmically shows us the file content with that change.

9. `git cat-file <flag> <hash>`
		flag: -t -> type of the object.
					-p -> print the content of the object.
		hash: 5-6 characters to identify objects.

10. Commits -> object -> commit object.
		- every commit object points to a tree.
		- The commit object has data of -> Author & Committer
																		-> date
																		-> message
																		-> parent commit
																		-> folders -> as the tree 

##########################################################################################
11. SHA-1 (Secure Hash Algorithm 1) is a cryptographic hash function used in Git to uniquely identify objects like commits, blobs, trees, and tags. Git uses SHA-1 to ensure data integrity and track changes efficiently by representing the state of a file or the entire project as a unique 40-character hexadecimal string.

### How Git Uses SHA-1:
1. **Object Storage:**
   - Git stores four types of objects: commits, blobs (file contents), trees (directories), and tags. Each object is stored in a key-value database where the key is the SHA-1 hash of the object's content.

2. **Object Hashing Process:**
   - When Git creates an object (e.g., a commit), it calculates a SHA-1 hash from the contents of the object. The hash becomes the object's ID in the repository.

3. **Example:**
   - Let’s say a file contains "Hello, Git!". When Git stores this file, it creates a blob object with the file's contents. Git then calculates the SHA-1 hash of the file to identify it uniquely.
   - The command:
     ```bash
     echo "Hello, Git!" | git hash-object --stdin
     ```
     This produces a hash like:
     ```
     d95f3e35f0dfd3b20bc8215442ba8139d6cb1b98
     ```

4. **Commit Hashes:**
   - Commits are also hashed using SHA-1, and the hash of a commit includes information such as the parent commit, commit message, tree object (representing the project state), author, and timestamp.
   - This ensures that even a slight change in any of these elements (e.g., a file change or message change) will result in a completely different commit hash, making each commit uniquely identifiable.

5. **Data Integrity:**
   - By using SHA-1, Git ensures that the content hasn't been tampered with. If the content changes (even by a single bit), the SHA-1 hash will change, making it easy to detect discrepancies.

### Key Points:
- SHA-1 in Git is not used for encryption but for creating unique identifiers for content.
- The 40-character hexadecimal SHA-1 hash serves as a fingerprint for each object.
- Any change in file content, commit data, or metadata results in a new SHA-1 hash, ensuring robust version control.

If you'd like to explore further with code examples, feel free to ask!
##########################################################################################	

12. Every commit point to the parent commit. This means you can go from one version to other 
		version or the previous version.
		
13. DS like tree, ll, hashing are used in git to manage the data.

14. When you create a commit -> it leads to the creation of tree,blob,commit object in the
		/object of /.git.
15. After making commit if you want to change the content and don't want to do extra commit
		you can ammend this to the previous commit. 

16. Make changes -> git add . -> `git commit --amend` -> this will update the changes in the 
		previous commit only.
17. Even if you have made ammendment in the previous commit only, but it will create new commit
		object. Because commit object can't be changed -> every commit object stores the time-stamp.
		
18. This will make the commit history clean.

19. HEAD pointer points to the latest commit that you have made.

20. Whenever we code, it can be in one of the following area:
		1. `working area` -> the files/changes which are not in your staging area and may be
					currently not handled by git are in the WORKING AREA. The files/changes are
					also called as UNTRACKED files/changes. After modification the changes that are 
					modified are also in the working area.
				
	  2. `staging area` -> files and changes which are surely going to be part of the commit
	  are in the staging area. i.e. files/changes when we do (git add).
	  Staging area is the palce where git knows what will change b/w the current and next commit.
	  
		 
		
		3. repo -> When you make the commit, the files/changes go to the repo area.
		
21. $ git restore --staged fileName -> to make staged file to come back to the untracked
		status i.e. unstaged area and also store the previous commits.
		
		git rm --cached fileName -> to bring complete file to the working area. -> git is not
		tracking the file completely. This will make the file to be deleted from the staging
		area but not from the memory.
		
22. `git restore fileName` -> to restore the changes of the working directory.

23. If you make the change and revert it manually then, it will not show modified.


--------------------------------------------------------------------------------------------------------------
                                                    Part-3

1. For example, to rename oldfile.txt to newfile.txt, you would run:
``git mv oldfile.txt newfile.txt``

2.`cp <source_file> <destination_file>` -> to copy content of source file to destination file.

3. ` nano ~/.gitconfig` -> to open the git configuration in editor-nano.

##########################################################################################

																    	BRANCHING

1. When you do git init you are assigned with the main/master branch i.e. the main 
	branch.

2. Branches means you can maintain multiple state of a project. When you want to 
	 create two or more features to the project and you are not sure where they should be
	 in the final project then, you can create branch of the main/master branch -> you can make 
	 changes in that branch and once you are sure that you want the changes -> you can merge 
	 the /featureBranch with the main-branch.

3. `git checkout -b branchName` -> to create a new branch and switch to that branch.

4. `git checkout branchName` -> to switch to a particular branch.

5. `git branch` -> to see all the branches.

6. `git switch -C branchName` -> to create a branch and switch to that branch.

7. `git switch branchName` -> to switch to a particular branch.

8. When you do commit in the master branch, these commit will not be reflected in the 
	new branch that you create and vice-versa(you can merge to reflect the changes).

9. production branch , pre-prod/testing branch.

10. Go to the master and do -> `git merge branchFeatureName` -> to merge the feature
		branch with main/master branch.

11. you can do merging with any branch to any other branch by going in that branch ->
		then, merge the branch that you want to merge.

50:00
