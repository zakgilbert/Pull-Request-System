# Pull-Request-System
A great pull request system 
## Github Workflow
#### A useful walkthrough for getting familiar with how to contirbute using pull requests!

### Phase 1
#### Set up
- Fork the "Main" repository (i.e. UHBazaar) to your personal Github account
  *You can do this by going to your organization's GitHub repository and clicking on fork (top right corner)*
- Clone that repo to a local directory.
- Open your command-line and cd into the local repo.
- Now add your organizations main repo as a remote called "upstream."
```bash
git remote add upstream "url of where you forked from"
```
- Now set the remote url as origin to your forked version of upstream.
```bash
git remote set-url origin "url of your forked repo"
```
- Type this
```bash
git remote -v
```
- You should see something like this
```bash
origin	https://github.com/username/repo-name.git (fetch)     /* url is your forked repo */
origin	https://github.com/username/repo-name.git (push)
upstream	https://github.com/repo-you-forked-from/repo-name.git (fetch)   /* url of where you forked from */
upstream	https://github.com/repo-you-forked-from/repo-name.git (push)
```
- Notice the main repo is named upstream and your personal forked repo is named origin.

### Phase  2
#### Keeping your master Current
- Open your command line and cd into your personal forked directory.
- We have to pull from the upstream master branch and push it to your personal origin master branch.  Otherwise you won't be working with the most current version of upstream master. This must be done evey time before making a new branch. Also you should only enter these next two commands when in your local master branch.
```bash
git checkout master     //switch to master branch
git pull --rebase upstream master
git push -f origin master
```

#### Create a branch
- Make the branch, name it what you like, but including the issue number would be a good idea. Using the syntax as follows will open up new options for your pull request in github "Issue-#23".
```bash
git branch "choosen-name"
```
- Now switch to that branch
```bash
git checkout "choosen-name"
```

### Phase 3
#### Commiting and creating a pull request
- When you are ready...
```bash
git add .
git commit -m "message"  /* including issue number is a good idea */
git push origin "branch name"
```
- I Suggest doing this on your first commit, that way very commit after that will be added to the pull request where it can be viewed by others who are contributing.
- Now access your organizations main repo and create a pull request.
- This option should be advertised as soon as you access the repo, if do as follows...
  - Click on create pull request.
  - Click on the compare across forks option.
  - Your base fork should be the main project repo and the head fork should be your personal fork.
- Yes, your team can review what you've been up to, you will also be notified if there are merge conflicts before a  merge has happened which saves a lot of trouble.
- When you are ready to merge do it from github in your pull request.
