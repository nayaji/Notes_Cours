# Git Cheatsheet: Comprehensive Guide

## 1. **Setup and Configuration**
- **Install Git**: [Download here](https://git-scm.com/)
- **Initial Configuration**:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```
- **Check Configuration**:
  ```bash
  git config --list
  ```

---

## 2. **Basic Commands**
- **Initialize a Repository**:
  ```bash
  git init
  ```
- **Clone a Repository**:
  ```bash
  git clone <repository-url>
  ```
- **Check Status**:
  ```bash
  git status
  ```
- **Add Changes to Staging**:
  ```bash
  git add <file>
  git add . # Add all changes
  ```
- **Commit Changes**:
  ```bash
  git commit -m "Your commit message"
  ```

---

## 3. **Branching and Merging**
- **Create a Branch**:
  ```bash
  git branch <branch-name>
  ```
- **Switch to a Branch**:
  ```bash
  git checkout <branch-name>
  ```
- **Create and Switch to a Branch**:
  ```bash
  git checkout -b <branch-name>
  ```
- **Merge Branches**:
  ```bash
  git checkout main
  git merge <branch-name>
  ```
- **Delete a Branch**:
  ```bash
  git branch -d <branch-name>
  ```

---

## 4. **Remote Repositories**
- **Add a Remote**:
  ```bash
  git remote add origin <repository-url>
  ```
- **View Remotes**:
  ```bash
  git remote -v
  ```
- **Push to Remote**:
  ```bash
  git push -u origin main
  ```
- **Pull from Remote**:
  ```bash
  git pull
  ```
- **Fetch Updates**:
  ```bash
  git fetch
  ```

---

## 5. **Stashing**
- **Save Uncommitted Changes**:
  ```bash
  git stash
  ```
- **View Stashes**:
  ```bash
  git stash list
  ```
- **Apply a Stash**:
  ```bash
  git stash apply
  ```
- **Drop a Stash**:
  ```bash
  git stash drop
  ```

---

## 6. **Rebasing**
- **Rebase a Branch**:
  ```bash
  git checkout <branch-name>
  git rebase main
  ```
- **Abort a Rebase**:
  ```bash
  git rebase --abort
  ```

---

## 7. **Undoing Changes**
- **Unstage a File**:
  ```bash
  git reset <file>
  ```
- **Undo the Last Commit (Keep Changes)**:
  ```bash
  git reset --soft HEAD~1
  ```
- **Undo the Last Commit (Discard Changes)**:
  ```bash
  git reset --hard HEAD~1
  ```
- **Revert a Commit**:
  ```bash
  git revert <commit-hash>
  ```

---

## 8. **Viewing History**
- **View Commit History**:
  ```bash
  git log
  ```
- **View a Single Line Log**:
  ```bash
  git log --oneline
  ```
- **View Changes in a Commit**:
  ```bash
  git show <commit-hash>
  ```

---

## 9. **Tagging**
- **Create a Tag**:
  ```bash
  git tag <tag-name>
  ```
- **Push Tags to Remote**:
  ```bash
  git push origin --tags
  ```
- **Delete a Tag**:
  ```bash
  git tag -d <tag-name>
  ```

---

## 10. **Collaboration Tips**
- **Resolve Merge Conflicts**:
  - Edit conflicting files manually.
  - Mark conflicts with `<<<<`, `====`, and `>>>>`.
  - Add and commit resolved files.

- **Pull Request Workflow**:
  1. Push your branch to remote.
  2. Create a pull request on GitHub or GitLab.
  3. Merge after approval.

---

## 11. **Advanced Commands**
- **Blame**:
  ```bash
  git blame <file>
  ```
- **Cherry-pick a Commit**:
  ```bash
  git cherry-pick <commit-hash>
  ```
- **Squash Commits**:
  ```bash
  git rebase -i HEAD~<number-of-commits>
  ```

---

## 12. **Tips for a Clean Git Workflow**
- Always write descriptive commit messages.
- Use `.gitignore` to exclude unnecessary files.
- Regularly pull updates from the remote repository.
- Keep your branches organized and delete unused ones.

---

This cheatsheet covers the most important Git commands and workflows. Practice using them in your projects to gain fluency!

