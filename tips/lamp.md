---
layout: default
title: LAMP Tips
section: tips/lamp
---

Tips for running a LAMP stack on Codebox.io
=========


Pre-installed LAMP tools:

  - `apache`
  - `mysql` (and necessary PHP plugins)
  - `php` version `5.4`


## Apache Server

`apache` can automatically be run from the `codebox` UI by simply clicking the run button.


## Builtin PHP server

If `apache` is not installed, when clicking `run`, `codebox` will fallback to the builtin `php` server. Which is essentially the following command:

```
php -S 0.0.0.0:$PORT
```


## MySQL

MySQL can be started or stopped with the following commands :

### Start
```
sudo mysqld
```

### Stop
```
sudo killall mysqld
```
