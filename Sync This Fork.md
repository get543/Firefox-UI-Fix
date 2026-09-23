When you clone your fork to your computer, Git automatically sets up a single remote named `origin` that points to your fork. It does not automatically configure a link to the original project repository (referred to as `upstream`). To sync your fork, you must add the upstream repository once as a remote, then fetch and merge its commits.

1. **Add the upstream repository as a remote:** One-time setup.
Run `git remote add` followed by the name `upstream` and the URL of the original project repository:

```bash
git remote add upstream https://github.com/black7375/Firefox-UI-Fix.git

```

**Verification:** Run `git remote -v`. You should now see two remotes listed: `origin` (your fork) and `upstream` (the original owner's repository).


2. **Fetch changes from the upstream repository:**
Download the latest commits, branches, and tag history from the original project without modifying your local code:

```bash
git fetch upstream

```

**Verification:** Git will output a list of updated references, such as `* [new branch] main -> upstream/main`.


3. **Switch to your local default branch:**
Ensure you are on the local branch you want to update (usually `main` or `master`):

```bash
git checkout master
# Or: git switch main

```

**Verification:** Run `git branch`. An asterisk (`*`) will appear next to `master`.


4. **Merge upstream changes into your local branch:**
Integrate the latest commits from `upstream/master` into your local `master` branch:

```bash
git merge upstream/master

```

**Verification:** Git will report a `Fast-forward` update or details of merged commits. Running `git status` will show that your local branch is now ahead of `origin/main`.


5. **Push updated local commits to your GitHub fork:**
Push your updated local branch back up to your fork on GitHub (`origin`):

```bash
git push origin master

```

**Verification:** Run `git status`—it will report `Your branch is up to date with 'origin/main'`.


---

### Alternative: GitHub CLI

If you have the GitHub CLI installed, you can skip adding remotes manually and sync your fork in a single command:

```bash
gh repo sync

```

---

For a visual walk-through explaining how upstream remotes work during synchronization, check out [How to Sync Your Fork with an Upstream Repository in Git](https://www.youtube.com/watch?v=wm729442UzA&utm_source=gemini). This video visually breaks down the distinction between `origin` and `upstream` and demonstrates these exact commands step-by-step.