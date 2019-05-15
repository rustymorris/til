##Caching your Github password

To cache your Github password on git, do the following:

`git config --global credential.helper cache`

This will cache the password to memory for 15 minutes.

To delete your passwod from cache, use this:
```
git config credential.helper cache erase
```
