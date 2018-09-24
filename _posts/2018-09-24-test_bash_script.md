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
