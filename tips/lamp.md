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

### Authentication

By default on `codebox.io` the **MySQL** credentials are :

  - **username:** `root`
  - **password:** `root`

`codebox.io` does not expose the credentials in environment variables yet.

## PHPMyAdmin

### Accessing the admin UI

`phpmyadmin` is installed by default on `codebox.io`, when using the `apache` runner you can access the `phpmyadmin` UI by visiting the `/phpmyadmin/` url.

### Credentials

The `phpmyadmin` credentials are the same as specified above for `mysql`.


## PHP Code Example

A simple `PHP` sample that connects to the MySQL database prints the info.

```php
<?php
// Connect to MySQL database
$link = mysql_connect('localhost', 'root', 'root');

// Error connecting
if (!$link) {
   die('Error connecting to MySQL server : ' . mysql_error());
}

// Print out information on the MySQL host
printf("MySQL Host info : %s\n", mysql_get_host_info());
?>
```
