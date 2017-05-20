---
layout: post
title: "How to reset a git repository"
date: 2016-04-25
categories: git
---

So, you have a repo on git which you're absolutely *certain* you won't need to look through earlier commits?
You want a simple reset of the repo with the current state of the code used as the initial commit?
Sure, that's easily doable. In just two lines actually.

You'll need to navigate to the repo and enter the following in either your terminal or "git shell" (if you're used to using the GitHub desktop application).


```shell
git reset $(git commit-tree HEAD^{tree} -m "commit message")
git push origin master --force
```

Replace "commit message" with your own commit message but that's it!



### Credits
[This answer](http://stackoverflow.com/a/23486788) by ryenus on StackOverflow for the awesome one-liner reset commit
