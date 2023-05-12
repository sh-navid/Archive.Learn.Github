# GIT
- _**Disclaimer**: This section is not an official resource and is for educational purposes only. The codes may be wrong or not suitable for a non-educational environment._
## Concepts
- Log
    - `git log`
    - `git log --pretty=oneline`
    - `git log --pretty=oneline --abbrev-commit`
- Status
    - `git status`
- Add
    >> To update what will be committed
    - `git add .`
    - `git add <file>`
- Restore
    >> To discard changes in working directory
    - `git restore <file>`
- Pull
- Push
    >> Sends changes to remote repository
    - `git push`
    - `git push force`
- Clone
- Checkout to
- Fetch
- Commit
    >> Puts changes into local repository
    - Usual
        - Commit
        - Commit Staged
        - Commit All
    - Delete
        - Delete current commit
            - `git reset --soft HEAD~1`
        - Delete current commit and data
            - `git reset --hard HEAD~1`
        - Delete until specific commit
            ~~~git
                git log --pretty=oneline --abbrev-commit
                git reset --hard <commit hash>
            ~~~
    - Amend
        - Commit [link](https://stackoverflow.com/a/179147/2227070)
            >> Allowing you to change the commit message of the most recent commit
            - `git commit --amend -m "New Message"`
        - Commit Staged
        - Commit All 
    - Signed Off
        - Commit
            >> You can see `Signed-off-by <name>` under the commit
            - `git commit -s -m "New Message By Signer"`
            - `git log`
        - Commit Staged
        - Commit All
    - Undo Last Commit
    - Commit and Sync
        >> 1.Commit, 2.Pull, 3.Push
- Change
    - Stage All Changes
    - Unstage All Changes
    - Discard All Changes
- Stage...

<pre>
            Workspace          Index            Local            Remote
                                                 Repo             Repo
                |-----------`commit -a`---------->|                |
                |                |                |                |
                |-----`add`----->|----`commit`--->|-----`push`---->|
                |                |                |                |
                |<-------------------pull/rebase-------------------|
                |                |                |                |
                |                |                |<----`fetch`----|
                |                |                |                |
                |<-------`checkhout head`---------|                |
                |                |                |                |
                |<--`checkout`---|                |                |
                |                |                |                |
                |<----------`diff head`-----------|                |
                |                |                |                |
                |<----`diff`-----|                |                |

</pre>

[source](https://stackoverflow.com/a/30039242/2227070)

- Workspace (Working directory)
    >> Folder of our codes
- Local Repository
- Remote Repository

## More
### Add, Commit
~~~git
    git pull

    # Make changes
    git add File1 <file> <file>

    # Verify changes
    git commit -m 'Message'

    # Send to remote server
    git push
~~~
### Connect an offline folder 2 git repo
~~~git
    git init
    git add .
    git remote add origin <Remote repository URL>
    git pull origin master
~~~
### Merge 2 git repos
[link](https://medium.com/altcampus/how-to-merge-two-or-multiple-git-repositories-into-one-9f8a5209913f)
- [ ] TODO: check this link - Update content and use approporate format for sitation
~~~markdown
    git remote add -f repo2merge git@github.com:https://github.com/<USER>/<REPO>
    git merge repo2merge/master --allow-unrelated-histories
~~~
### Merge a subdirectory of another repository with git
--
### Add username and email to git
~~~markdown
    git config --global user.name "<USERNAME>"
    git config --global user.email "<EMAIL>"
~~~