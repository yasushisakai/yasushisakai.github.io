---
layout: post
title: test_bash_script
date: 2018-09-24
categories: default
---

I made a simple shortcut to make the memo process in one command

```bash
memo () {
  # make a file
  y=$(date +'%Y-%m-%d')
  file="/mnt/c/Users/yasushi/code/yasushisakai.github.io/_posts/$y-$1.md"
  touch $file
  echo "---
layout: post
title: $1
date: $y
categories: default
---" > $file
  vim $file
}
```

with this you can ```memo <title of memo>``` and memo whatever

to automate the repo update process (add, commit, push)

```bash
umemo () {
cd "/mnt/c/Users/yasushi/code/yasushisakai.github.io/"
git add .
d=$(date +'%Y-%m-%d')
git commit -m "update: $d"
git push
}
```
and will push to github with generic commit message 'update: YYYY-MM-DD'
