---
title: "Syncing GitHub Forks with Git"
date: 2017-08-23 17:51:38
tags: 
- git
- open source
- github
---

On my [last team](https://github.com/github/visualstudio), I had push access as a collaborator. I didn't have to worry too much about forks,as I wasn't really doing much open source outside of my job. The one thing that I can never remember how to do is deal with forks locally. Specifically, I always forget how to grab the latest commits from the parent repository. I like to `pull` (`fetch + merge`) as often as I can to incorporate new changes as quickly as possible because conflicts suck.

# Make sure your remote is set
We'll need to make sure we can access the parent fork. If you're working with a forked branch and want to keep it synced up with the parent repo, you'll need to set the remote of the repository you want to track, if it's not set already. 

Let's take a look at the remotes you have. With your favorite cli of choice, navigate to your local repository `(cd path/to/your/directory)` that contains the fork and type the following:

`git remote -v`

You should see a list similar to this:
```
origin https://github.com/me/myforkedrepo (fetch)
origin https://github.com/me/myforkedrepo (push)
maybe-a-remote-here https://github.com/parent/parent-repo (fetch)
maybe-a-remote-here https://github.com/parent/parent-repo (push)
```

This is your list of remotes with the url they are pointing to. The `-v` in this command is what displays the url, which might be helpful if you want to know where these remotes live. Origin is _probably_ yours, and it might be the only one in this list. If there is a remote that contains the url of the repo you've forked, you don't need to add one and you can stop here and pull down new changes. If not, let's add that remote.

Hopefully you've remembered where you forked the project from, but if you don't, GitHub makes it super easy for you to find out. Just navigate to your forked repo on github.com. From the repo name at the top, you should also see where it was forked from directly below that. You can navigate to the parent link.

![example fork](/img/ghforkinfo.png)

Copy the parent url because you'll need it for the next step.

## Add parent as a remote
Let's add the parent repo url that we got in the last section as a remote. From the cli:

_`parent` is what I chose to name the remote, feel free to change it to whatever you'd like._


```
git remote add parent https://github.com/parent/parentrepo.git
```


If you do `git remote -v` again, you should see the remote you just added.

Ok! We're set to get some commits!

# Get the latest changes

If the parent repo is very active, chances are you might be out of sync with it, so let's grab the latest changes:

`git pull parent` or `git fetch parent` _[difference between pull and fetch](https://stackoverflow.com/questions/292357/what-is-the-difference-between-git-pull-and-git-fetch)_

This grabs all the history and branches from the parent repo. Now that we have recent changes locally let's merge things!

# Merge

For this example we'll assume `master` is the default branch of parent and that you want to get your forked `master` branch caught up with the parent. 

With the following commands in the cli we'll 
- Check out the forked master branch
- Merge forked master with parent master
- Push updates to GitHub

```
git checkout master
git merge parent/master
git push
```

After these commands you should see something similar to this on your forked repository (Microsoft:master = parent:master):
![fork is even with master](/img/evenfork.png)

What this means is that the commits in the parent repo match the commits in your forked repo. Note that if you've committed changes there might be something that says "x commits ahead of [the parent repo name]". That usually just means you've got some stuff you've been working on up in there. If you didn't do it, check the commit history and see what changed.

## Resources
[`git remote`](https://git-scm.com/docs/git-remote)
[`git push`](https://git-scm.com/docs/git-push)
[`git fetch`](https://git-scm.com/docs/git-fetch)
[GitHub: Fork a Repo](https://help.github.com/articles/fork-a-repo/)



