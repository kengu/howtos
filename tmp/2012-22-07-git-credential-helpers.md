---

layout: howto
title: Prevent ``git`` from asking for credentials on every ``git push``

---


Solution (git 1.7.9+)
=====================

```
git config --global credential.helper cache
```