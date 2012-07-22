---

layout: howto
title: Prevent git from asking for credentials on every git push
category: [git, config]

---


Solution
========

With git 1.7.9 or later, just do:

``` 
git config --global credential.helper cache 
```

which tells git to keep your password cached in memory for (by default) 15 minutes.

**Reference**: [Stackoverflow](http://stackoverflow.com/questions/5343068/is-there-a-way-to-skip-password-typing-when-using-https-github)