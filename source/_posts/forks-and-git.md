---
title: "GitHub Forks and Git"
date: 2017-08-23 17:51:38
tags: 
git
open source
github
---

On my [last team](https://github.com/github/visualstudio), I had push access as a collaborator. I didn't have to worry too much about forks,as I wasn't really doing much open source outside of my job. The one thing that I can never remember how to do is deal with forks locally. Specifically, I always forget how to grab the latest commits from the parent repository. I like to `pull` (`fetch + merge`) as often as I can to incorporate new changes as quickly as possible because conflicts suck.

## Make sure your remote is set
We'll need to make sure we can access the parent fork. If you're working with a forked branch and want to keep it synced up with the parent repo, you'll need to set the remote of the repository you want to track, if it's not set already. 

Let's take a look at the remotes you have. With your favorite cli of choice, navigate to your local repository (`cd path/to/your/directory`)that contains the fork and type the following:
`git remote -v`

You should see a list similar to this:
```
origin https://github.com/me/myforkedrepo (fetch)
origin https://github.com/me/myforkedrepo (push)
maybe-a-remote-here https://github.com/parent/parent-repo (fetch)
maybe-a-remote-here https://github.com/parent/parent-repo (push)
```

This is your list of remotes with the url they are pointing to. The `-v` in this command is what displays the url, which might be helpful if you want to know where these remotes live. Origin is _probably_ yours, and it might be the only one in this list. If there is a remote that contains the url of the repo you've forked, you don't need to add one and you can stop here and pull down new changes. If not, let's add that remote.

Hopefully you've remembered where you forked the project from, but if you don't, GitHub makes it super easy for you to find out. Just navigate to your forked repo on github.com. From the repo name at the top, you should also see where it was forked from directly below that.

![example fork](/img/ghforkinfo.png)

Grab the url because you'll need it for the next step.

### Add parent as a remote




