---
layout: post
date: 2016-02-11 08:27:25 -0500
title: how i learned to stop worrying and love to squash
---

i had heard for a long time that pull requests [should only have a single commit](http://ndlib.github.io/practices/one-commit-per-pull-request/).  that you could be however freaky you liked on your local machine, committing every five seconds or whatever.  but before you shared your code with the world, you should combine those commits into a single commit.  (or maybe a couple of commits if there was some logical grouping that made sense, e.g., upgrade a dependency in one commit, then add a new feature that required the upgrade in a second commit).

the reasoning is pretty straightforward. normal development sometimes goes in a straight line, but it often meanders.  you try one thing, rip it out and try another.  or maybe things get really complicated and there are a couple things going on, and you have to get a few plates spinning at once for it to all work together.  so the real commit history is messy, and nobody wants to see that.

but i had a few issues with this.  the rest of the open source development package (open development on github, feature branches for new work, merging in changes in pull requests, etc.) all made sense to me.  but squashing commits was the sticking point for me.  i grudgingly put up with it in open source develoment, and didn't adopt it (much less advocate for it) in my local environment.

the first problem i had was that it felt like lying.  the commits as i made them were real, and squashing them hid the intermediate steps.  "show your work" had been pounded into me since third grade math, and squashing felt like erasing my work.

the other problem i had was that i didn't know how to squash.  i tried it a few times when it would have been convenient, and messed up my local branch and had to manually copy files around to undo the damage.  i was pretty new to git, and the terminology and mechanics of syncing between the local repository and github were confusing to me.

i talked a lot about the first issue, but if i'm honest the second one was a pretty big part of my resistance to squashing too.  and they fed off each other: why bother learning something you think isn't worth doing?  why reconsider your opinion of something if it's all a mess anyway?

as luck would have it, i was working on an open source project that didn't require squashing commits before a pull request was opened -- the reviewer of the PR expected additional commits to be pushed to the same branch/PR in response to code review comments, and keeping those separate made it easier to review the changes without having to review the whole PR from scratch.  once the PR was ready to be merged, the reviewer would squash all the commits and merge them.

so i was able to see the benefits of squashing without having to actually do it myself.  and as i got more involved in the project and did more code review, i came to like the cleaner commit history that it enables.  and so i gradually came around and eventually decided i should learn how to squash.  to review and merge pull requests, i needed to know how to do it.

so i went back to the blog post i linked to above, and read it much more carefully.  i clicked on the "command line instructions" link at the bottom of github pull requests to see the commands to fetch changes from a remote branch and merge them into a local branch.  and i think there are a couple of points that are assumed, or off to the side of the main ways of thinkging about this, that i think it's worth making explicit:

1. you should really use branches, all the time, for everything.  they are cheap, so make them all the time if you even think you might want to make changes.  if you are not confident in rebasing yet, create a new branch just for rebasing.  if you mess it up, you can just throw the branch away and try again.

2. you don't have to count commits when rebasing, you just need a reference.  and the branch you are targeting to merge into is probably the reference you want.

3. even better than squashing is marking commits as "fixup" -- they get completely removed, including their commit messages.  so if your first commit message is good, you can mark everything else as "fixup" and you don't even need to edit the commit messages.


so, my process is now:

* update master and create a new branch when i start work on something:

  {% highlight shell %}
  git checkout master
  git pull
  git checkout -b my-branch-name
  {% endhighlight %}

* make my changes to that branch and commit my changes as i go.  i generally try to make the first commit message good so i can use it later:
  {% highlight shell %}
  git add path/to/update_file.rb
  git commit -m "Adding support for foo - closes #123"
  {% endhighlight %}

> as an aside, if you're using github issues, then the "closes #123" bit in the commit message will link the PR to that issue, and close the issue when the PR is merged.  github has a help page listing the various forms you can use to [close issues with commit messages](https://help.github.com/articles/closing-issues-via-commit-messages/).

* when i'm ready to submit a pull request, i update master and rebase against it:
  {% highlight shell %}
  git checkout master
  git pull
  git checkout my-branch-name
  git rebase -i master
  {% endhighlight %}

* the first step in rebasing is selecting which commits to include and how to handle them, by editing a list of commits, starting with something like:

  {% highlight shell %}
  pick 1b921d1 Adding support for foo - closes #123
  pick b82abe3 tests pass
  pick 3ab13ae fixing typo
  pick 8c13af4 no really fixing it this time
  {% endhighlight %}

> and then editing it to look like:

  {% highlight shell %}
  pick 1b921d1 Adding support for foo - closes #123
  fixup b82abe3 tests pass
  fixup 3ab13ae fixing typo
  fixup 8c13af4 no really fixing it this time
  {% endhighlight %}

* then git applies the commits in order, and if you're unlucky, you have to resolve merge conflicts.  this is the most complicated part by far.  here's a good summary of the [mechanics of resolving merge conflicts](http://genomewiki.ucsc.edu/index.php/Resolving_merge_conflicts_in_Git).  but the main thing i can recommend is updating master early and often.  as i got better at rebasing, i found it easier to just rebase any time there was a significant update to master, so i could take them one at a time.

* if there is more than one commit left (e.g., if you use "squash" instead of "fixup"), then you get a big list of the commit messages.  you then edit them down to a single final commit message.  if you only have one commit left, then you're done (the one commit's message will be used as-is).

* once the rebase is finished, i push my branch to github and then go view the repo in my browser to create a pull request.
