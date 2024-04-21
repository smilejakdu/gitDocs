# merge 와 rebase

<figure><img src=".gitbook/assets/스크린샷 2024-04-21 오후 2.25.38.png" alt=""><figcaption></figcaption></figure>

merge 와 rebase 의 차이점을 알고 알맞게 사용하면 된다.

git branch 가 feature/login , dev, main 이 존재한다고 했을때



The image you've provided illustrates the difference between `git merge` and `git rebase`. Here's how each command would work in the terminal given the branches you mentioned: `feature/login`, `dev`, and `main`.

#### Git Merge

`git merge` is used to integrate changes from one branch into another. It combines the end points of two branches and creates a new merge commit if there are no conflicts.

Assuming you are on the `dev` branch and want to merge changes from the `feature/login` branch into `dev`, you would:

1.  Switch to the `dev` branch:

    ```
    git checkout dev
    ```
2.  Merge the `feature/login` branch into `dev`:

    ```
    git merge feature/login
    ```

This will create a new merge commit in the `dev` branch that includes all the changes from `feature/login`.

#### Git Rebase

`git rebase` is used to move or combine a sequence of commits to a new base commit. It's a way to reapply commits on top of another base tip.

Assuming you are on the `feature/login` branch and you want to rebase it onto the `dev` branch, you would:

1.  Switch to the `feature/login` branch:

    ```
    git checkout feature/login
    ```
2.  Rebase the current branch onto `dev`:

    ```
    git rebase dev
    ```

This will take all the commits from the `feature/login` branch and reapply them on top of the latest commit on `dev`. If there are no conflicts, your `feature/login` branch history will now start from the tip of `dev`.

#### Best Practices

* Use `merge` when you want to preserve the complete history and timeline of changes, typically in a public branch like `main`.
* Use `rebase` to streamline a complex history, avoid merge commits, and keep your history clean before integrating your changes into a public branch. This is often done on a feature branch before merging it into `main` or `dev`.

**Note:** Rebasing rewrites the commit history, which can be problematic for shared branches. It’s best used for cleaning up local commits before sharing them with others. Always pull with rebase (`git pull --rebase`) on branches where you need to keep a linear history.

In your case, if you need to update the `feature/login` branch with the latest changes from `dev` and maintain a linear history, you would use `git rebase`. If you are ready to integrate the completed feature into `dev`, and you want to maintain the context of a merge, you would use `git`&#x20;



`merge`.

