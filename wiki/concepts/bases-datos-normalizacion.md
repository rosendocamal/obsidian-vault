---
title: "Bases de Datos y Normalización"
type: concept
created: 2026-07-21
updated: 2026-07-21
sources: [raw/courses/capacitate-para-el-empleo/especialidad_tratamientos_datos.md]
tags: [bases-datos, normalizacion, entidad-relacion, cardinalidad, visualizacion-datos]
---

# Bases de Datos y Normalización

## Definición

Una **base de datos** es un conjunto de datos relacionados entre sí, almacenados y consultados mediante software especializado. Permite manejar grandes cantidades de información de manera fácil, rápida y automática, con integridad de datos (no se pierde ni se repite) y seguridad de acceso (Capacítate para el empleo, 2026).

## Modelo Entidad-Relación (ER)

El modelo ER divide la información en tablas de menor tamaño y las relaciona entre sí:

- **Entidad**: cualquier cosa que es objeto de interés (rectángulo en el diagrama)
- **Atributo**: categoría o clasificación de la entidad (oválo)
- **Relación**: vínculo entre entidades (rombo)
- **Llave primaria**: identificador único de cada registro (no puede ser nulo)

## Normalización

Proceso de acomodar los datos al modelo ER. Hay 3 formas normales:

1. **Primera forma normal (1NF)**: campos repetidos se consolidan en uno solo; cada registro tiene una llave primaria única
2. **Segunda forma normal (2NF)**: datos repetidos se separan en tablas y se relacionan mediante llaves foráneas
3. **Tercera forma normal (3NF)**: campos que no dependen de las llaves primarias se colocan en una tabla nueva

La normalización previene duplicación, reduce espacio de almacenamiento y permite consultas más rápidas.

## Cardinalidad

Forma en que las entidades se relacionan entre sí:

| Tipo | Descripción |
|------|-------------|
| **1:1** (uno a uno) | Un registro de una entidad se relaciona con un único registro de otra |
| **1:N** (uno a muchos) | Un registro se relaciona con varios registros de otra entidad |
| **N:M** (muchos a muchos) | Varios registros de una entidad se relacionan con varios de otra |

## Depuración y visualización de datos

- **Depuración**: filtros, formato condicional, eliminación de duplicados
- **Tablas dinámicas (pivot)**: resumen grandes volúmenes de datos
- **Gráficos**: barras (comparación), circulares (impacto sobre total), lineales (comportamiento en el tiempo), compuestos (múltiples variables)

### Criterios para informes

- Tablas: título, columna matriz, encabezados, cifras, pie de notas
- Gráficas: título en mayúsculas, periodo delimitado, unidades, colores distinguibles con leyenda

## Plan de trabajo para bases de datos

**Si la base no existe**:
1. Diagnóstico y modelado ER
2. Identificación de entidades, atributos, llaves y cardinalidades
3. Ejecución en software adecuado
4. Pruebas de consulta

**Si la base existe y necesita depuración**:
1. Respaldo de la base actual
2. Análisis de convenciones
3. Eliminación de inconsistencias y duplicados
4. Exportación en formato adecuado

## Contenido vinculado

- [[osint-busqueda-informacion]]
- [[contabilidad-basica]]
- [[analisis-foda]]
- [[fundamentos-programacion]]
