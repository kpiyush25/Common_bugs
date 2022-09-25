### 1) Permission issue
On cloning your own repository using the command "git clone <repo_url>", if the following error appears : 
```
$ git clone <repo_url>
Cloning into '<repo>'...
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

```
Then you need to authenticate that the repo is owned by you. One easy way to fix it is:
```
1) Go to Settings(overall settings of your profile and not the repo settings) --> Developer Settings --> Personal access tokens
2) Generate new token.
3) Note what the token is for.
4) Grant repo access.
5) Clone the repo using:
$ git clone https://<token>@github.com/<user>/<repo>.git

If you've already cloned the repo, you could just modify your remote setting:

$ git remote set-url origin https://<token>@github.com/<user>/<repo>.git
$ git pull
Already up to date.
```
PS : Source is stackoverflow.
