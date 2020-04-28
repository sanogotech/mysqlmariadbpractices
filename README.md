
# MySQL  /Maria DB  Best Practices


## Docs Urls
- https://www.hostinger.fr/tutoriels/creer-un-utilisateur-mysql/

## Install  XAMPP
Download

[Link to Download XAMPP ](https://www.apachefriends.org/fr/download.html
)

## PhpMyAdmin
- In Windows Start: XAMPP

![XAMPP Control Panel](https://github.com/sanogotech/mysqlmariadbpractices/blob/master/docs/images/xampcontrolpanel.jpg)

```
https://localhost:80
user = root
password =
```
![Login PhpMyadmin ](https://github.com/sanogotech/mysqlmariadbpractices/blob/master/docs/images/phpmyadminlogin.png)

## Add myql  to  PATH
```
Ex :  C:\xampp\mysql\bin  to PATH  Windows
```
## BASICS : Command Line
* Connect
```
mysql  -u  root  -p

```
* In Mysql Shell After connection
```
help;

List of all client commands:
Note that all text commands must be first on line and end with ';'
?         (\?) Synonym for `help'.
clear     (\c) Clear the current input statement.
connect   (\r) Reconnect to the server. Optional arguments are db and host.
delimiter (\d) Set statement delimiter.
ego       (\G) Send command to MariaDB server, display result vertically.
exit      (\q) Exit mysql. Same as quit.
go        (\g) Send command to MariaDB server.
help      (\h) Display this help.
notee     (\t) Don't write into outfile.
print     (\p) Print current command.
prompt    (\R) Change your mysql prompt.
quit      (\q) Quit mysql.
rehash    (\#) Rebuild completion hash.
source    (\.) Execute an SQL script file. Takes a file name as an argument.
status    (\s) Get status information from the server.
tee       (\T) Set outfile [to_outfile]. Append everything into given outfile.
use       (\u) Use another database. Takes database name as argument.
charset   (\C) Switch to another charset. Might be needed for processing binlog with multi-byte charsets.
warnings  (\W) Show warnings after every statement.
nowarning (\w) Don't show warnings after every statement.

```
* Creare User avec l'octroi de tous les privilèges
```
CREATE USER 'non-root'@'localhost' IDENTIFIED BY 'mypassword';

GRANT ALL PRIVILEGES ON * . * TO 'non-root'@'localhost';
FLUSH PRIVILEGES;

```
* Create User avec des droits specifiques
```
GRANT [permission type] ON [database name].[table name] TO ‘non-root’@'localhost’;
GRANT CREATE, SELECT ON * . * TO 'non-root'@'localhost';
REVOKE [permission type] ON [database name].[table name] FROM ‘non-root’@‘localhost’;
REVOKE ALL PRIVILEGES ON *.* FROM 'non-root'@'localhost';
DROP USER ‘non-root’@‘localhost’;
FLUSH PRIVILEGES;
```