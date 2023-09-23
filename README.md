# Github Basics

## Workflow

1. # Create a New Branch on GitHub after Cloning

Here are the steps to create a new branch on GitHub after cloning a repository:

1. Clone the repository to your local machine using `git clone <repo-url>`. This will create a copy of the repository on your computer.

2. Checkout the main branch using `git checkout main`. This will switch you to the main branch. 

3. Fetch the latest changes from the remote repository using `git fetch`. This will pull any new commits on the main branch that you don't have locally.

4. Create a new branch using `git branch <branch-name>`. This will create a new branch locally based off the main branch.

5. Switch to the new branch using `git checkout <branch-name>`. This will move you onto the new branch.

6. Make changes and commit them on the new branch.

7. Push the new branch to GitHub using `git push -u origin <branch-name>`. This will push the branch to the remote repository and set it to track the remote branch.
