# Olam2021
An update of Olam Autoresponder being worked on by a codeAthon team

OLAM Autoresponder is a sequential autoresponder which means that it can send out a series of emails in response to just one request. It is good for sending out daily devotionals, bible studies, lessons in a course, evangelism follow-up etc.

 

It is double-opt-in to prevent spamming. It is highly configurable and PDF attachments are possible. You can set the time between emails being sent out. They can be sent daily, every two days, monthly, whatever you want.

 

It is written in PHP/MySQL and runs on a LAMP stack.

 

It is a fork of the abandoned Infinite Autoresponder on Sourceforge. There have been many improvements and security updates. Accidental unsubscribing has been fixed and the ability to resubscribe where you left off has been added.

 

Olam is Hebrew for eternity/forever ( a take off from "infinite").

 

OLAM Autoresponder is Open Source and is free under the GPL . You are free to download it, modify it, and use it however you wish (as provided by the GPL).


Dev setup instructions
======================
Requires PHP and MySQL (MariaDB). 
Tested using PHP 7.4.

Requires mysqli extension enabled. Arch Linux users see https://wiki.archlinux.org/index.php/PHP#MySQL/MariaDB

Before running the commands to create the database ensure mysql or MariaDB is running.
systemd based distros can use the following:

```
$ systemctl start mysqld.service
```

```
$ mysqladmin create olam_autoresponder -u root -p
$ mysql -u root -p -e "GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, CREATE TEMPORARY TABLES, LOCK TABLES ON olam_autoresponder.* TO 'olam_autoresponder'@'localhost' IDENTIFIED BY '5tH7w34GlU'"
```

Edit config.php and fill in the database name, username and password.

You might need to switch the database server from localhost to 127.0.0.1

Then start the dev server:
```
$php -S localhost:8000
```