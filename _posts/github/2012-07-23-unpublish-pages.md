---

layout: howto
title: Unpublish project pages
category: github

---


Solution
========

To unpublish <a href="http://pages.github.com">GitHub project pages</a>, just delete the remote `gh-pages` branch:

``` 
$ git push origin --delete gh-pages
```

**Reference**: [GitHub:help](https://help.github.com/articles/unpublishing-a-project-page)
