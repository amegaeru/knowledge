## 1.Basic Command.
|details|command|
|:--|:--|
|Login a MYSQL Database|# mysql -u root -p|
|Logout a MYSQL Database|mysql> \q|
||mysql> quit|

## 2.Login Command.
|details|command|
|:--|:--|
|Create Managed User|mysql> GRANT ALL PRIVILEGES ON *.* TO hoge@localhost;|
|Create Database User|mysql> GRANT ALL ON db_User.* TO hoge@localhost;|
|Create Table User|mysql> GRANT ALL ON db_User.tbl_Customer TO hoge@localhost;|
|Set User password|SET PASSWORD FOR hoge=PASSWORD('hogehoge');|
|Verify User|SELECT Host, User, Password FROM mysql.user WHERE user='hoge';|
|Delete User|mysql> DROP USER [user_name];|

## 3.Operating Database Command.
|details|command|
|:--|:--|
|Create Database|mysql> CREATE DATABASE IN NOT EXISTS db_User;|
|Verify Database List|mysql> SHOW DATABASES;|
|Change Used Database|mysql> USE [database_name];|
|Delete Database|mysql> DROP DATABASE [database_name];|

## 4.Operating Table Command.
```
CREATE TABLE [DB名].[テーブル名](
  id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
  title VARCHAR(50),
  content TEXT,
  create_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
);
```
|details|command|
|:--|:--|
|Verify Table List|mysql> SHOW TABLES;|
|Delete Database|mysql> DROP TABLE [database_name].[table_name];|

|details|command|
|:--|:--|
|固定長文字列|CHAR|
|可変長文字列|VARCHAR|
|整数|INT、BIGINT、TNYINT|
|浮遊小数点|DOUBLE、FLOAT|
|日付|DATE|
|時刻|DATETIME|
|テキスト|TEXT、LONGTEXT|

|details|command|
|:--|:--|
|自動|AUTO_INCREMENT|
|NULL禁止|NOT NULL|
|プライマリキー指定|PRIMARY KEY|