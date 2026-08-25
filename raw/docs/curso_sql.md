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

## Sentencias SQL

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
```

###

```sql
```

###

```sql
```

###

```sql
```

###

```sql
```

###

```sql
```

###

```sql
```

###

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

