---
title: "Git Hooks"
date: 2021-12-06T22:05:56-06:00
draft: false
---

### Git what?!

For those who don't know, [git][1] is a super powerful version control solution for your code. It has too many features to list here, but one I would like to cover is git hooks. Git hooks allow you to run whatever commands you want at various points in the git lifecycle. For example, once you pull code from the repo run a command. I am using this technique to keep this blog site updated. I commit my code changes to the repo, then on the linux server I do a git pull to grab the latest code. Once that code has been pulled down, git automagically(™️) runs `hugo -D` to generate up the static site for this blog. I have a blog post about Hugo [here]({{< ref "posts/hugo" >}}).

### post-merge

When you issue a `git pull` a number of different things takes place. Git fetches the changes from the server, it then attempts to merge those changes into your your local code base. If it is successful, the post-merge hook is "fired". This mean that any commands in the .git/hooks/post-merge file are executed. 

If all of this sounds like wizardry, its because it is. Thats OK though, its easy to become a git wizard. Here are some fantastic resource to help you out.

- https://learngitbranching.js.org/ - This tutorial series will make you a git expert in no time  
- https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks - Here is the git hooks documentation.   

### You can Git too!

To play around with git, you should have a place to put your code (thats not just on your laptop).

The following place offer free git code hosting.

- https://github.com/ - One of the best git hosting locations around.
- https://gitlab.com/ - My favorite git hosting provider. They offer quite a lot more than just git hosting for free.
- https://bitbucket.org/product - Not a bad provider, the other two listed are a bit better IMHO.

[1]: https://git-scm.com/