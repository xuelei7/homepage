# SQL

## 環境整備

インストールしてから，パスを通して，以下のように実行

```
$ net start mysql57
$ mysql --user=root --password
mysql> exit;
$ net stop mysql57
```

## データベースの作成

```
mysql> SHOW databases;
mysql> CREATE DATABASE practise;
```

## テーブルの作成

```
mysql> USE practise;
mysql> SHOW tables;
mysql> CREATE TABLE users (
    > id INT AUTO_INCREMENT,
    > name TEXT,
    > PRIMARY KEY (id))
    > DEFAULT CHARSET=utf8;

mysql> SHOW tables;
+--------------------+
| Tables_in_practise |
+--------------------+
| users              |
+--------------------+
1 row in set (0.00 sec)

mysql> DESCRIBE users;
+-------+---------+------+-----+---------+----------------+
| Field | Type    | Null | Key | Default | Extra          |
+-------+---------+------+-----+---------+----------------+
| id    | int(11) | NO   | PRI | NULL    | auto_increment |
| name  | text    | YES  |     | NULL    |                |
+-------+---------+------+-----+---------+----------------+
2 rows in set (0.00 sec)
```

## 動作確認

```
mysql> SELECT * FROM users;
Empty set (0.00 sec)

mysql> INSERT INTO users(name) VALUES ('xuelei7');
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM users;
+----+---------+
| id | name    |
+----+---------+
|  1 | xuelei7 |
+----+---------+
1 row in set (0.00 sec)
```

## データベースの削除

```
mysql> DROP TABLE users;
mysql> DROP DATABASE practise;
```

# SQL I

```
SELECT aaa
FROM bbb
WHERE a = b;

WHERE ee LIKE '%cc%';

WHERE NOT [条件];

WHERE kk IS (NOT) NULL;

aa AND bb

cc OR dd

ORDER BY ?? ASC/DESC

LIMIT [件数]
```

# SQL II

```
//重複を取り除く
SELECT DISTINCT(column)
FROM xxx;

//和
SELECT SUM(...)

//平均
SELECT AVG(...)

//数える
SELECT COUNT(...)
//NULLを含む場合
SELECT COUNT(*)

//最大最小
SELECT MAX(...)
SELECT MIN(...)

//集計
GROUP BY ...

```

使用する順番：
where > group by > count/sum/avg/max/min > having

# SQL III

サブクエリ

```
//コラムの名前変更
SELECT a AS '文字列'
```

JOIN

```
SELECT *
FROM A
(LEFT) JOIN B
ON A.id=B.id;
```

# SQL IV

## データの追加

```
INSERT INTO table (val1,val2,val3)

VALUES(v1,v2,v3)
```

## データの更新

```
UPDATE table
SET val1='vv1', val2='vv2'
WHERE id=x;
```

## データの削除

```
DELETE FROM table
WHERE id=x;
```