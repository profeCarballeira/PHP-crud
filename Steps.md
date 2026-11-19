# Make a CRUD
[Tutorial](https://www.tutorialrepublic.com/php-tutorial/php-mysql-crud-application.php)

## Preparing the database
1. Make a database "company"
2. Make an user (%) with priviledges on the DB "company"
3. Import or copy and pase the sql-script to create the table.
```
CREATE TABLE employees (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    address VARCHAR(255) NOT NULL,
    salary INT(10) NOT NULL
);
```
4. Insert data
```
INSERT INTO `employees` (`id`, `name`, `address`, `salary`) VALUES
(1, 'Roland Mendel', 'C/ Araquil, 67, Madrid', 5000),
(2, 'Victoria Ashworth', '35 King George, London', 6500),
(3, 'Martin Blank', '25, Rue Lauriston, Paris', 8000);
```
> Remeber to use PDO always (this example)

## Coding
1. Copy+paste+adapt the config.php
```
<?php
/* Database credentials. Assuming you are running MySQL
server with default setting (user 'root' with no password) */
define('DB_SERVER', 'mysql');
define('DB_USERNAME', 'Manuel');
define('DB_PASSWORD', 'abc123.');
define('DB_NAME', 'company');
 
/* Attempt to connect to MySQL database */
try{
    $pdo = new PDO("mysql:host=" . DB_SERVER . ";dbname=" . DB_NAME, DB_USERNAME, DB_PASSWORD);
    // Set the PDO error mode to exception
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch(PDOException $e){
    die("ERROR: Could not connect. " . $e->getMessage());
}
?>
```
2. Copy and paset the index.php (landing page)
3. The same for create.php
4. The same for read.php
5. The same for update.php
6. The same for delete.php
