---

layout: howto
title: Unpublish [GitHub pages](http://pages.github.com/)
category: github

---


Solution
========

To unpublish a project page, just delete the remote `gh-pages` branch

``` 
$ git push origin --delete gh-pages
```

**Reference**: [GitHub:help](https://help.github.com/articles/unpublishing-a-project-page)
