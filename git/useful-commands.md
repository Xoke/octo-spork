#Useful commands for git

- Grab a copy of a remote git repository into current directory
`git clone https://www.github.com/xoke/octo-spork`

- Set up things like git usernames are under
`git config user.name "Xoke"`

- Set up caching username (so you don't have to enter every single time)
`git config --global credential.helper cache`
	- That saves for 15 minutes by default but you can change that easily with
`git config --global credential.helper 'cache --timeout=3600'`
	- This is 3600 seconds, or one hour

- Push the latest changes up to github
```
git commit -m "Descriptive commit message here"
git push --all
```

