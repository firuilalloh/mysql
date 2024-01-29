# Mysql Date And Time Format

### Format Date In Mysql Manual Input
- ### date
```
//create table
CREATE TABLE testdate (
    product VARCHAR(255),
    tanggal DATE DEFAULT NULL
)

//insert
INSERT INTO testdate (product, tanggal) VALUES ("ki", NOW());
``` 

Dengan typedata di atas akan menunjukkan hasil :

> 2024-12-10
- ### datetime

```
//create table
CREATE TABLE testdate (
    product VARCHAR(255),
    tanggal DATETIME DEFAULT NULL
)

//insert
INSERT INTO testdate (product, tanggal) VALUES ("ki", NOW());
```

Dengan hasil typedata di atas akan menunukkan hasil :

> 2024-12-10 03:10:12

- ### timestamp

```
//create table
CREATE TABLE testdate (
    product VARCHAR(255),
    tanggal TIMESTAMP DEFAULT NULL
)

//insert
INSERT INTO testdate (product, tanggal) VALUES ("ki", NOW());
```
Dengan hasil typedata di atas akan menunukkan hasil yang sama dengan datetime :

> 2024-12-10 03:10:12

---
### Format Date In Mysql Automatic Input
- ### timestamp
```
//create table
CREATE TABLE `testdate` (
  `product` varchar(255) DEFAULT NULL,
  `tanggal` timestamp NOT NULL DEFAULT current_timestamp()
)

//insert
INSERT INTO testdate (product) VALUES ("ki");
```
Ketika create table tambahkan `NOT NULL DEFAULT current_timestamp()`

Dengan hasil sama dengan timestamp manual input :

> 2024-12-10 03:10:12

Yang membedakan adalah kalian tidak perlu mengisi kolom tanggal dengan fungsi `NOW()` karena sudah memiliki fungsi ketika cretae table `current_timestamp()`

Sama dengan yang lain ketika kalian memiliki fungsi `current_timestamp()` yang sudah di set ketika create table, maka kalian tidak perlu untuk mendefinisikan kolom tersebut ketika insert ke dalam kolom.

Exemple yang lain :
- ### date
```
//create table
CREATE TABLE `testdate` (
  `product` varchar(255) DEFAULT NULL,
  `tanggal` date NOT NULL DEFAULT current_timestamp()
)

//insert
INSERT INTO testdate (product) VALUES ("ki");
```

Outputnya :
> 2024-12-10

- ### datetime 
```
//create table
CREATE TABLE `testdate` (
  `product` varchar(255) DEFAULT NULL,
  `tanggal` datetime NOT NULL DEFAULT current_timestamp()
)

//insert
INSERT INTO testdate (product) VALUES ("ki");
```

Outputnya :
> 2024-12-10 03:10:12





