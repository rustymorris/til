### Caching your github password


To cache your github password on git, do the following:

`git config --global credential.helper cache`

This will cache the password to memory for 15 minutes.

To delete your password from cache, use this:
```
git config credential.helper cache erase
```
