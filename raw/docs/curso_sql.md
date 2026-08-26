# Curso de SQL

| Inicio | Fin | Actualización |
|-|-|-|
| 2026-08-25 | | |

> [!IMPORTANT]
> Las notas y las clases fueron cursadas pensando en el entorno de Fedora.

> [!NOTE]
> Descargar [**MySQL Community**](https://dev.mysql.com/downloads/mysql/).

> [!IMPORTANT]
> Guía de instalación de [**MySQL**](https://docs.fedoraproject.org/en-US/quick-docs/installing-mysql-mariadb/) en Fedora.

## Instalación de MySQL (en Fedora)

Para ver cuales versiones están disponibles en nuestra versión de Fedora:

```bash
dnf search mysql | grep server
```

Para instalar la distribución de `MySQL` por defecto:

```bash
sudo dnf install mysql-server -y
```

Para arrancar el servicio de `MySQL`:

```bash
sudo systemctl enable --now mysqld
```

Para conectar y utilizar la base de datos:

```bash
mysql -u root -p
```

> [!NOTE]
> Consultar métodos para instalar [**MySQL Workbench**](https://computingforgeeks.com/install-and-use-mysql-workbench-on-fedora/) en Fedora.

## Instalación de MySQL Workbench

Descargar el archivo `rpm` [aquí](https://dev.mysql.com/downloads/workbench/).

Instalar el archivo `rpm`, sustituye `[rpm]` por el nombre del fichero correspondiente:

```bash
sudo dnf install [rpm] -y
```

> [!NOTE]
> Ayuda para la instalación, consulte [aquí](https://es.console-linux.com/?p=37144).
> Este método no tiene soporte oficial.

## SQL

Creación de una tabla desechable.

```sql
CREATE DATABASE hello_sql;
```

```sql
CREATE SCHEMA `hello_mysql` ;
```

```sql
CREATE TABLE `hello_mysql`.`users` (
  `user_id` INT NOT NULL,
  `name` VARCHAR(50) NOT NULL,
  `surname` VARCHAR(100) NULL,
  `age` INT NULL,
  `init_date` DATE NULL,
  `email` VARCHAR(100) NULL,
  PRIMARY KEY (`user_id`));
```

```sql
INSERT INTO `hello_mysql`.`users` (`user_id`, `name`, `surname`, `age`, `init_date`, `email`) VALUES ('2', 'Sarah', 'Lopez', '35', '2010-08-31', 'sarahlopez@grupoalianza.com');
INSERT INTO `hello_mysql`.`users` (`user_id`, `name`, `surname`, `age`, `init_date`, `email`) VALUES ('3', 'Brais', 'Castillos', '25', '2009-09-24', 'braiscastillos@grupoalianza.com');
INSERT INTO `hello_mysql`.`users` (`user_id`, `name`, `surname`, `age`, `init_date`, `email`) VALUES ('4', 'Satya', 'Sundai', '48', '2005-07-01', 'satyasundai@grupoalianza.com');
```

## Lectura de Bases de Datos

### Comentarios

```sql
-- Comentario en una línea.

/* Comentarios en varias líneas.
   Esto es una línea.
   Esto es otra línea.
*/
```

### SELECT

```sql
SELECT * FROM users;

SELECT name FROM users;

SELECT user_id, name FROM users;
```

### DISTINCT

Trae los datos distintos indicados.

```sql
SELECT name FROM users;

SELECT user_id, name FROM users;
```

### WHERE

```sql
SELECT * FROM users WHERE age = 128

SELECT name FROM users WHERE age > 20;

SELECT DISTINCT email FROM users WHERE age >= 15;
```

### ORDER BY

```sql
SELECT * FROM users ORDER BY name;

SELECT * FROM users ORDER BY name ASC;

SELECT * FROM users ORDER BY name DESC;

SELECT * FROM users WHERE age > 35 ORDER BY age DESC;

SELECT * FROM users WHERE age <= 80 ORDER BY email ASC;
```

### LIKE

```sql
SELECT * FROM users WHERE email LIKE '%grupoalianza.com';

SELECT * FROM users WHERE user_id <= 3 AND email LIKE '%alianza.com';

SELECT * FROM users WHERE user_id <= 3 OR user_id = 4 AND email LIKE '%@%';
```

### AND, OR, NOT

```sql
SELECT * FROM users WHERE NOT NOT email LIKE '%grupoalianza.com';

SELECT * FROM users WHERE NOT NOT NOT email LIKE '%grupoalianza.com';

SELECT * FROM users WHERE NOT age = 128 AND email LIKE '%grupoalianza.com';

SELECT * FROM users WHERE NOT email = 'juansalinas@grupoalianza.com' OR age >= 25 AND age < 100;
```

### LIMIT

```sql
SELECT * FROM users WHERE NOT email = 'juansalinas@grupoalianza.com' OR age >= 25 AND age < 100 LIMIT 2;

SELECT * FROM users LIMIT 2;
```

### NULL

```sql
SELECT * FROM users WHERE email IS NULL;

SELECT * FROM users WHERE email IS NOT NULL;

SELECT * FROM users WHERE email IS NOT NULL AND user_id >= 2 AND user_id < 4 LIMIT 1;
```

### MAX, MIN

```sql
SELECT MAX(age) FROM users;

SELECT MIN(age) FROM users;

SELECT MAX(age), MIN(age) FROM users;

SELECT MAX(age) as edad_maxima,
	MIN(age) as edad_minima
FROM users;
```

### COUNT

```sql
SELECT COUNT(*) FROM users;

SELECT COUNT(age) FROM users;
```

### SUM, AVG

```sql
SELECT SUM(age) FROM users;

SELECT AVG(age) FROM users;
```

### IN

```sql
SELECT * FROM users WHERE name IN ('juan');

SELECT * FROM users WHERE name IN ('Juan');

SELECT * FROM users WHERE name IN ('JUAN');

SELECT * FROM users WHERE name IN ('braiS', 'SATYA');
```

### BETWEEN

```sql
SELECT * FROM users WHERE age BETWEEN 20 AND 35;
```

### ALIAS

```sql
SELECT name AS 'NOMBRE', init_date AS 'FECHA DE GRADUACIÓN' FROM users WHERE age BETWEEN 20 AND 50;
```

### CONCAT

```sql
SELECT CONCAT('Nombre: ', name, ', Apellidos: ', surname) AS 'Nombre completo' FROM users;

SELECT CONCAT(name, ' ', surname) AS 'NOMBRE COMPLETO' FROM users;

SELECT CONCAT(name, ' ', surname, ' tiene ', age, ' años y su correo electrónico es ', email) AS 'Frase' FROM users;
```

### GROUP BY

```sql
SELECT MAX(age) FROM users GROUP BY age ORDER BY age DESC;

SELECT MAX(age) FROM users GROUP BY age;

SELECT MIN(age) FROM users GROUP BY age ORDER BY age ASC;

SELECT MIN(age) FROM users GROUP BY age;

SELECT age AS 'Edad', COUNT(age) AS 'Personas' FROM users GROUP BY age;

SELECT age AS 'Edad', COUNT(age) AS 'Personas' FROM users WHERE age > 15 AND age < 128 GROUP BY age;

SELECT age AS 'Edad', COUNT(age) AS 'Personas' FROM users WHERE age > 15 AND age < 128 GROUP BY age ORDER BY age ASC;

SELECT age AS 'Edad', COUNT(age) AS 'Personas' FROM users WHERE age > 15 AND age < 128 GROUP BY age ORDER BY age DESC;
```

### HAVING

```sql
SELECT COUNT(age) FROM users HAVING COUNT(age) > 3;
```

### CASE

```sql
SELECT *,
CASE
	WHEN age > 30 THEN 'Muy cerca de la jubilación.'
    ELSE 'Está en sus años de juventud.'
END AS '¿Es joven?'
FROM users;

SELECT *,
CASE
	WHEN age > 30 THEN False
    ELSE True
END AS '¿Come como si chambeara?'
FROM users;

SELECT *,
CASE
    WHEN age > 99 THEN 'Usted es sobreviviente del siglo pasado.'
	WHEN age > 30 THEN 'Muy cerca de la jubilación.'
    ELSE 'De ninguna manera.'
END AS '¿Se puede jubilar?'
FROM users;
```

### IFNULL

```sql
SELECT name, surname, IFNULL(age, 0) AS age FROM users;
```

## Escritura de Base de Datos

### INSERT

```sql
INSERT INTO users (user_id, name, surname) VALUES (5, 'María', 'López');

INSERT INTO users (user_id, name, surname) VALUES (6, 'Chesco', 'Pérez');
```

### UPDATE

```sql
UPDATE users SET age = '21' WHERE user_id = 6;

UPDATE users SET init_date = '2007-10-31' WHERE user_id = 6;

UPDATE users SET age = 20, init_date = '2020-10-10' WHERE user_id = 5;
```

### DELETE

```sql
DELETE FROM users WHERE user_id = 5;
```

## Administración de bases de datos

### CREATE

```sql
CREATE DATABASE test;
```

### DELETE

```sql
DROP DATABASE test;
```

## Administración de tablas

### CREATE TABLE

```sql
CREATE DATABASE test;

CREATE TABLE persons (
	id INT,
    name VARCHAR(100),
    age INT,
    email VARCHAR(50),
    created DATE
);

-- NOT NULL
CREATE TABLE persons_2 (
	id INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    age INT,
    email VARCHAR(50),
    created DATE
);

-- UNIQUE
CREATE TABLE persons_3 (
	id INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    age INT,
    email VARCHAR(50),
    created DATETIME,
    UNIQUE(id)
);

-- PRIMARY KEY
CREATE TABLE persons_4 (
	id INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    age INT,
    email VARCHAR(50),
    created DATETIME,
    UNIQUE(id),
    PRIMARY KEY(id)
);

-- CHECK
CREATE TABLE persons_5 (
	id INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    age INT,
    email VARCHAR(50),
    created DATETIME,
    UNIQUE(id),
    PRIMARY KEY(id),
    CHECK(age>=18)
);

-- DEFAULT
CREATE TABLE persons_6 (
	id INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    age INT,
    email VARCHAR(50),
    created DATETIME DEFAULT CURRENT_TIMESTAMP(),
    UNIQUE(id),
    PRIMARY KEY(id),
    CHECK(age>=18)
);

-- AUTO_INCREMENT
CREATE TABLE persons_7 (
	id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    age INT,
    email VARCHAR(50),
    created DATETIME DEFAULT CURRENT_TIMESTAMP(),
    UNIQUE(id),
    PRIMARY KEY(id),
    CHECK(age>=18)
);
```

### DROP TABLE

```sql
CREATE TABLE persons_8 (
	name VARCHAR(100) NOT NULL DEFAULT 'SN'
);

DROP TABLE persons_8;
```

### ALTER TABLE

```sql

```

## Herramientas gráficas

- [**DbVisualizer**](https://www.dbvis.com/).
- [**phpMyAdmin**](https://www.phpmyadmin.net/).
- [**dbForge**](https://www.devart.com/dbforge/).
- [**SQLPro Studio**](https://www.sqlprostudio.com/).
- [**TablePlus**](https://www.tableplus.com).
- [**MySQL Workbench**](https://dev.mysql.com/downloads/workbench).

## Recursos adicionales

- [**SQLBolt**](https://sqlbolt.com/).
- [**W3Schools**](https://www.w3schools.com/sql/).

