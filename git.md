# Git commands

### Sync repo

`git remote add origin1 https://<link>/kk-121/tr-121.git`

* Override ssl verification

`git -c http.sslVerify=false push -u origin1 main`

### Branch from previous commit:

`git branch 210302_name 6f257827535d7cd94b78dc4b740c9b2ce08481d9`

`git checkout 210302_name`

`git push --set-upstream origin 210302_name`

### Git submodules
* Helpful: https://git-scm.com/book/en/v2/Git-Tools-Submodules

### Git server
* Local git is setup as in: https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server
* Git book at: https://git-scm.com/book/en/v2
