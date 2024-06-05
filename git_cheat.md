<style>
    r { color: #c4454b }
    o { color: #f27d29 }
    g { color: #409945 }
    bl { color: #4378d9 }
</style>

# <r>Git Cheat Sheet

## <o>Config

### <g>sslVerify
- git config --global http.sslVerify false

### <g>Always new folder for the new .crt
- git config --global http.sslCAInfo
- https://mattferderer.com/fix-git-self-signed-certificate-in-certificate-chain-on-windows



### <g>Config user
- git config user.email ext.anastasios.arvanitis@sncf.fr
- git config user.name anastasios-arvanitis

- git config --list
- git config --unset user.name
- git config --unset-all

- .git\info\exclude

## <o>Branches

### <g>create a new branch
- git branch branch-name

### <g>change to the new branch
- git checkout branch-name

### <g>Get remote branches
- git fetch origin

- git show commit-id
- git show HEAD

### <g>compare commits between two branches
- git log --oneline TESTBRANCH ^main

### <g>get the number of commits between parent and feature
- git rev-list --count --first-parent CRMMC_int..CRMMC_int_test3

### <g>check if branch exists on the remote
- git ls-remote --heads origin ${TARGET_BRANCH}

### <g>delete branch locally
- git branch -d localBranchName

### <g>delete local branch that is unmerged
- git branch -D localBranchName CRMMC-3074

### <g>delete branch remotely
- git push origin --delete remoteBranchName

### <g>publish a local branch
- git push –u origin <branch name>

## <o>Cherry-Pick
- git cherry-pick <hash>
- git cherry-pick --continue
- git cherry-pick --skip
- git cherry-pick --abort 

## <o>History
### <g>DOES CHANGE HISTORY
- git reset --flag HEAD~1 
- --soft: uncommit changes, changes are left staged (index).
- --mixed (default): uncommit + unstage changes, changes are left in working tree.
- --hard: uncommit + unstage + delete changes, nothing left.
- --merge ORIG_HEAD - It's just like git reset --hard ORIG_HEAD, doesn't touch uncommitted changes, goes to state after merge)

### <g>DOES NOT CHANGE HISTORY
### <g>will create a new commit that is the opposite - 
- git revert HEAD

### <g>removes files from the staging index and doesn't affect files in the working directory.
- git rm --cached: 

## <o>
### <g>oneline
- git log --oneline
### <g>retourn: 3caf38c1
- git log -1 --abbrev-commit => retourne: 3caf38c1
### <g>pretty
- git log -1 --pretty=format:%h 
### <g>pretty oneline
- git show --abbrev-commit --pretty='oneline'

## <o>Links - Paths
### <g>settings.json
- C:\Users\AnastasiosARVANITIS\AppData\Roaming\Code\User\settings.json
### <g>ca-bundle.crt
- C:\Users\AnastasiosARVANITIS\work\git_cert\ca-bundle.crt
### <g>sncf-remote
- https://github.com/DSI-GARES/gare.salesforce.git
### <g> Repo Flo
- https://github.com/floacker/TestAction/tree/main/.github/actions
