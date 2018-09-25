---
title: skip password input when ssh-ing
layout: post
---

# how to create ssh key and config 

how to register remote server, so that I can shortcut and do ``` ssh server ```

## on remote server
``` cd .ssh ```
``` ssh-keygen ```
enter key name
``` cat yourkeyname.pub >> authorized_keys```
``` chmod 600 authorized_keys```

## on local client
``` cd .ssh```
```scp user@server:.ssh/yourkeyname yourkeyname```

and add the following lines to .ssh config
```
Host aliasName
	Hostname serverhostname
	User username
	IdentityFile path/to/key
```
