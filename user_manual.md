\# How to Set Up a GitHub Repository and Make a First Commit



\## Prerequisites



Before starting, you need:



\* A GitHub account.

\* Git and Git Bash installed.

\* An internet connection.

\* A computer.

\* A text editor such as Notepad.



\## Steps



\### Step 1: Open Git Bash



\*\*Action:\*\* Open Git Bash.



\*\*Expected result:\*\* The Git Bash terminal opens.



\### Step 2: Create a project folder



\*\*Action:\*\* Type `mkdir my-first-repository` and press Enter.



\*\*Expected result:\*\* A folder named `my-first-repository` is created.



\### Step 3: Enter the project folder



\*\*Action:\*\* Type `cd my-first-repository` and press Enter.



\*\*Expected result:\*\* Git Bash moves into the project folder.



\### Step 4: Create a README file



\*\*Action:\*\* Type `echo "# My First Repository" > README.md` and press Enter.



\*\*Expected result:\*\* A `README.md` file is created.



\### Step 5: Initialize Git



\*\*Action:\*\* Type `git init` and press Enter.



\*\*Expected result:\*\* Git initializes the folder as a Git repository.



\### Step 6: Create a GitHub repository



\*\*Action:\*\* Create a new repository named `my-first-repository` on GitHub.



\*\*Expected result:\*\* The new repository appears on GitHub.



\### Step 7: Connect the local repository to GitHub



\*\*Action:\*\* Type `git remote add origin YOUR\_GITHUB\_REPOSITORY\_URL` and press Enter.



\*\*Expected result:\*\* The local repository is connected to GitHub.



\### Step 8: Stage the file



\*\*Action:\*\* Type `git add README.md` and press Enter.



\*\*Expected result:\*\* The README file is prepared for the commit.



\### Step 9: Make the first commit



\*\*Action:\*\* Type `git commit -m "Initial commit"` and press Enter.



\*\*Expected result:\*\* Git creates the first commit.



\### Step 10: Push the commit



\*\*Action:\*\* Type `git push -u origin master` and press Enter.



\*\*Expected result:\*\* The commit is uploaded to GitHub.



\## Screenshot Description



Take a screenshot of Git Bash after the successful `git push` command. The screenshot should show the message confirming that the `master` branch was pushed to GitHub.



Also take a screenshot of the GitHub repository page showing the `README.md` file.



\## Troubleshooting



\### Error: `remote origin already exists`



This error means that the repository is already connected to a GitHub remote.



\*\*Action:\*\* Type `git remote -v` and press Enter.



\*\*Expected result:\*\* Git shows the current GitHub repository URL.



If the URL is wrong, use:



`git remote set-url origin YOUR\_GITHUB\_REPOSITORY\_URL`



Then try the push command again.



