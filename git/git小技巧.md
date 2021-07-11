### remote/local branch operation

#### pull all branches

    git branch -r | grep -v '\->' | while read remote; do git branch --track "${remote#origin/}" "$remote"; done
    git fetch --all
    git pull --all

#### push local branch to remote

    git push origin zx:zx

#### pull the remote branch to the local branch (the branch does not exist locally)

    git checkout -b zx origin/zx
