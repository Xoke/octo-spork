# Useful commands for git

- Grab a copy of a remote git repository into current directory

`git clone https://www.github.com/xoke/octo-spork`

- Set up things like git usernames are under

`git config user.name "Xoke"`

- Set up caching username (so you don't have to enter every single time), defaults to caching credentials for 15 minutes

`git config --global credential.helper cache`

- Set cache to an hour (3600 seconds)

`git config --global credential.helper 'cache --timeout=3600'`

- Push the latest changes up to github

```
git add .
git commit -m "Descriptive commit message here"
git push --all
```

- add . adds all files
- commit commits the files, -m sets the commit message
- push --all pushes the changes to github

Or use git-desktop because GUI...