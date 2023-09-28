# 💥:Github Basics Workflow 

## I. Create & Connect Local Branch to Remote Repository

Here are the steps to create a new branch on GitHub after cloning a repository:

1. Clone the repository to your local machine using `git clone <repo-url>`. This will create a copy of the repository on your computer.
   ```
   git clone <repo-url>
   ```
3. Checkout the main branch using `git checkout main`. This will switch you to the main branch.
   ```
   git checkout main
   ```
5. Fetch the latest changes from the remote repository using `git fetch`. This will pull any new commits on the main branch that you don't have locally.
   ```
   git fetch
   ```
7. Create a new branch using `git branch <branch-name>`. This will create a new branch locally based off the main branch.
   ```
   git branch <branch-name>
   ```
9. Switch to the new branch using `git checkout <branch-name>`. This will move you onto the new branch.
   ```
   git checkout <branch-name>
   ```
10. Make changes and commit them on the new branch.

11. Push the new branch to GitHub using `git push -u origin <branch-name>`. This will push the branch to the remote repository and set it to track the remote branch.
   ```
   git push -u origin <branch-name>
   ```

## II. Create Pull Requests After Making Commits to Branch

1. Push your changes to your branch on GitHub:
    ```
    git push origin your-branch-name
    ```
3. On GitHub, navigate to the main page of the repository.

4. Click on the "Pull requests" tab. 

5. Click on the green "New pull request" button.

6. In the "base:" dropdown, select the branch you want to merge your changes into (usually the main branch). 

7. In the "compare:" branch, select your branch.

8. Review the changes that will be merged if you create a pull request.

9. Write a title and description for your pull request explaining your changes.

10. Click "Create pull request". 

11. A reviewer will review, approve, and merge your pull request. You may need to make more commits to your branch to address any feedback.

**Once your pull request is approved and merged, the branch is no longer needes so you can delete your branch.**

## III. Delete Branch After PR Approval
- Follow these steps to delete a branch on GitHub after its pull request has been merged:
1. Locally, switch to the main branch:
    ```
    git checkout main
    ```
2. Delete the local branch:
    ``` 
    git branch -d branch-to-delete
    ```
3. Update your local main branch:
    ```
    git pull
    ```
4. Delete the remote branch on GitHub:
    ```
    git push origin --delete branch-to-delete
    ```
5. Verify the branch no longer exists on GitHub under the "Branches" tab.

That's it! Once a pull request from a branch has been approved and merged to main, it's best practice to delete the now obsolete branch from both your local repository and GitHub.
Keeping your branches list clean makes it easier to stay organized and know which branches are active.


## IV. If Other PRs Are Approved Before Yours and/or the Main Branch Diverges from the Branch
> Your pull request will end up with a merge conflict. This is because the main branch has progressed while your branch has not incorporated those new changes.
> 
> GitHub will mark the pull request as having conflicts that need to be resolved before merging.
> 
> To resolve the conflict, you will need to rebase your branch onto the current main branch:

```
git checkout main
```
```
git pull origin main
```
```
git checkout your-branch
```
```
git rebase main
```

> This will replay your commits on top of the new main branch commits and force you to resolve any conflicts between your code and the new main branch code.
> 
> After resolving conflicts and completing the rebase, force push your branch to update the pull request `git push -f origin your-branch`
```
git push -f origin your-branch
```
> Now your pull request will show as up-to-date and the new commits from main. A reviewer can re-approve it and complete the merge.
>
>So in summary, if the main branch progresses, you need to rebase and resolve conflicts before your outdated branch can be merged. Let me know if this helps explain the workflow!
