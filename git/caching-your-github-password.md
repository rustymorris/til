##Caching your Github password
To cache your Github password on git, do the following:

`git config --global credential.helper osxkeychain`

To delete your passwod from cache, use this:
```
git credential-osxkeychain erase
host=github.com
protocol=https
```
