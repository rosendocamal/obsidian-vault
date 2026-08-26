# Curso de SQL

| Inicio | Fin | Actualización |
|-|-|-|
| 2026-08-25 | | |

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
-- ADD
ALTER TABLE persons_8
ADD surname VARCHAR(150);

-- RENAME COLUMN
ALTER TABLE persons_8
RENAME COLUMN surname TO description;

-- MODIFY COLUMN
ALTER TABLE persons_8
MODIFY COLUMN description VARCHAR(250);

-- DROP COLUMN
ALTER TABLE persons_8
DROP COLUMN description;
```

## Relaciones

### Tipos de relaciones

- Relaciones `1:1`.

- Relaciones `1:N`.

- Relaciones `N:M`.

- Autoreferencia

### Creación de tablas relacionadas

```sql
-- TABLA 1:1
CREATE TABLE dni(
	dni_id INT AUTO_INCREMENT PRIMARY KEY,
    dni_number INT NOT NULL,
    user_id INT,
    UNIQUE(id),
    FOREIGN KEY(user_id) REFERENCES users(user_id)
);

-- TABLA 1:N
CREATE TABLE companies(
	company_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

ALTER TABLE users
ADD company_id INT;

ALTER TABLE users
ADD CONSTRAINT fk_companies
FOREIGN KEY(company_id) REFERENCES companies(company_id);

-- TABLA N:M
CREATE TABLE languages(
	language_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

CREATE TABLE users_languages(
	users_language_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    language_id INT,
    FOREIGN KEY(user_id) REFERENCES users(user_id),
    FOREIGN KEY(language_id) REFERENCES languages(language_id),
    UNIQUE (user_id, language_id)
);
```

### Datos y relaciones

```sql
-- DATOS 1:1
INSERT INTO dni (dni_number, user_id) VALUES (111111, 1);
INSERT INTO dni (dni_number, user_id) VALUES (232222, 2);
INSERT INTO dni (dni_number, user_id) VALUES (333331, 3);

-- DATOS 1:N
INSERT INTO companies (name) VALUES ('Dunosusa');
INSERT INTO companies (name) VALUES ('SuperWillys');
INSERT INTO companies (name) VALUES ('Google');
INSERT INTO companies (name) VALUES ('Facebook');
INSERT INTO companies (name) VALUES ('FMI');
INSERT INTO companies (name) VALUES ('Banco Mundial');

UPDATE users SET company_id = 1 WHERE user_id = 1;
UPDATE users SET company_id = 2 WHERE user_id = 5;
UPDATE users SET company_id = 3 WHERE user_id = 4;
UPDATE users SET company_id = 4 WHERE user_id = 3;
UPDATE users SET company_id = 5 WHERE user_id = 2;

-- DATOS N:M
INSERT INTO languages (name) VALUES ('C++');
INSERT INTO languages (name) VALUES ('MATLAB');
INSERT INTO languages (name) VALUES ('Python');
INSERT INTO languages (name) VALUES ('Rust');
INSERT INTO languages (name) VALUES ('Octave');
INSERT INTO languages (name) VALUES ('Maxima');

INSERT INTO users_languages (user_id, language_id) VALUES (1, 1);
INSERT INTO users_languages (user_id, language_id) VALUES (1, 2);
INSERT INTO users_languages (user_id, language_id) VALUES (1, 3);
INSERT INTO users_languages (user_id, language_id) VALUES (1, 4);
INSERT INTO users_languages (user_id, language_id) VALUES (1, 5);
INSERT INTO users_languages (user_id, language_id) VALUES (1, 6);
INSERT INTO users_languages (user_id, language_id) VALUES (2, 2);
INSERT INTO users_languages (user_id, language_id) VALUES (2, 3);
INSERT INTO users_languages (user_id, language_id) VALUES (3, 5);
INSERT INTO users_languages (user_id, language_id) VALUES (3, 6);
INSERT INTO users_languages (user_id, language_id) VALUES (4, 1);
INSERT INTO users_languages (user_id, language_id) VALUES (4, 2);
INSERT INTO users_languages (user_id, language_id) VALUES (4, 3);
INSERT INTO users_languages (user_id, language_id) VALUES (4, 4);
INSERT INTO users_languages (user_id, language_id) VALUES (5, 4);
```

## Consulta de relaciones

### INNER JOIN

```sql
SELECT * FROM users
INNER JOIN dni;

SELECT * FROM users
INNER JOIN dni
ON users.user_id = dni.user_id;

SELECT * FROM users
INNER JOIN dni
ON users.user_id = dni.user_id
ORDER BY age DESC;

SELECT * FROM users
INNER JOIN dni
ON users.user_id = dni.user_id
ORDER BY age ASC;

SELECT name, dni.dni_number, email FROM users
INNER JOIN dni
ON users.user_id = dni.user_id
ORDER BY age ASC;

SELECT * FROM users
JOIN companies
ON users.company_id = companies.company_id;

SELECT * FROM companies
JOIN users
ON companies.company_id = users.company_id;

SELECT *
FROM users_languages
INNER JOIN users ON users_languages.user_id = users.user_id
INNER JOIN languages ON users_languages.user_id = languages.language_id;

SELECT users.name AS 'Empleado', languages.name AS 'Lenguage de Programación'
FROM users_languages
INNER JOIN users ON users_languages.user_id = users.user_id
INNER JOIN languages ON users_languages.user_id = languages.language_id;
```

### LEFT JOIN

```sql
SELECT * FROM users
LEFT JOIN dni
ON users.user_id = dni.user_id;

SELECT name, dni_number FROM users
LEFT JOIN dni
ON users.user_id = dni.user_id;

SELECT name, dni_number FROM dni
LEFT JOIN users
ON users.user_id = dni.user_id;

SELECT users.name AS 'Empleado', languages.name AS 'Lenguage de Programación'
FROM users_languages
LEFT JOIN users ON users_languages.user_id = users.user_id
LEFT JOIN languages ON users_languages.user_id = languages.language_id;

SELECT users.name AS 'Empleado', languages.name AS 'Lenguage de Programación'
FROM users_languages
LEFT JOIN users ON users_languages.user_id = users.user_id
JOIN languages ON users_languages.user_id = languages.language_id;
```

### RIGHT JOIN

```sql
SELECT * FROM users
RIGHT JOIN dni
ON users.user_id = dni.user_id;

SELECT name, dni_number FROM users
RIGHT JOIN dni
ON users.user_id = dni.user_id;

SELECT name, dni_number FROM dni
RIGHT JOIN users
ON users.user_id = dni.user_id;

SELECT users.name AS 'Empleado', languages.name AS 'Lenguage de Programación'
FROM users_languages
RIGHT JOIN users ON users_languages.user_id = users.user_id
RIGHT JOIN languages ON users_languages.user_id = languages.language_id;

SELECT users.name AS 'Empleado', languages.name AS 'Lenguage de Programación'
FROM users_languages
RIGHT JOIN users ON users_languages.user_id = users.user_id
JOIN languages ON users_languages.user_id = languages.language_id;
```

### FULL JOIN

```sql
SELECT users.user_id AS u_user_id, dni.user_id AS d_user_id
FROM users
LEFT JOIN dni
ON users.user_id = dni.user_id
UNION ALL
SELECT users.user_id AS u_user_id, dni.user_id AS d_user_id
FROM users
RIGHT JOIN dni
ON users.user_id = dni.user_id
WHERE users.user_id IS NULL;

SELECT *
FROM users
LEFT JOIN dni
ON users.user_id = dni.user_id
UNION
SELECT *
FROM users
RIGHT JOIN dni
ON users.user_id = dni.user_id;
```

## Conceptos avanzados

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

