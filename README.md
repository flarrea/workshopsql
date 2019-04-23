# Workshop SQL
Introducción al uso de SQL

El presente workshop tiene como propósito entregar conceptos iniciales en el uso de SQL para consultar Bases de Datos Relacionales. Al final del curso, el participante podrá construir sus propias consultas SQL básicas a conjuntos de datos determinados. Además, podrá utilizar Microsoft Access o Excel para realizar dichas consultas.

Los objetivos son:

Conocer de forma básica el concepto de base de datos relacional.
Conocer SQL.
Identificar los tipos de sentencias básicas SQL y sus componentes sintácticos.
Conocer los clientes SQL que permiten consultar bases de datos.
Importar tablas desde una base de datos a Access y Excel.
Crear consultas SQL para extraer, visualizar, modificar o eliminar datos de una base de datos.
Automatizar consultas básicas de SQL.
Valorar el potencial creativo y profesional de la utilización de SQL.

Preparación del entorno:

Se utilizará sistema operativo Windows 10, MS Access y MS Excel, además de una base de datos de prueba.

Descripción del módulo:

Parte 1: 

a) Introducción a las bases de datos relacionales.
b) Introducción a la utilización de SQL.

Parte 2: 

a) Tipos de sentencias básicas SQL.
b) Componentes sintácticos de SQL.
d) Sentencias DQL(Data Query Language: SELECT).
e) Sentencias DML(Manipulación de Datos: INSERT, DELETE y UPDATE).

Parte 3:

a) Clientes SQL.
b) Importar datos a MS Access y MS Excel

Parte 4:

a) Consultas DQL: SELECT.
b) Consultas DML: INSERT.
c) Consultas DML: DELETE.
d) Consultas DML: UPDATE.

Parte 5:

a) Modificador condicional: WHERE.
b) Modificador selector: *.
c) Modificador: DISTINCT.
d) Operador de comparación.
e) Operador aritmético.
f) Operador lógico.
g) Operador sobre cadena de caracteres.
h) Operador de pertenencia.
i) Operador Simple String Pattern Matching.
j) Operador nulo.
k) Operador ORDER BY
l) Operador LIMIT


Parte 6:

a) Consultas multitablas.
b) Operador JOIN.
c) Operador INNER JOIN.
d) Operador ALIASING.
f) Consultas anidadas.

Parte 7: Evaluación:

a) Evaluación práctica de consultas de datos.

######################################################################################

Consulta SQL desde Access:

![SQL_Acess](https://user-images.githubusercontent.com/5190215/56532314-891ab380-6523-11e9-87af-a4e646d45c6e.gif)

######################################################################################

Consulta SQL desde Excel:

![SQL_Excel](https://user-images.githubusercontent.com/5190215/56607375-65fd0c00-65d6-11e9-8ef7-d6e0f01f157a.gif)

######################################################################################

Ejemplos de consultas:

Consulta SQL Básica: * SELECTOR
Selecciona todos los valores de todas las tuplas de una relación

SELECT *
FROM Product;


SELECT *
FROM Product
WHERE Category = ‘Tablet’;

SELECT Name, Category
FROM Product;

SELECT Name, Category
FROM Product
WHERE Manufactor = ‘Apple’

DISTINCT Elimina valores duplicados

SELECT DISTINCT Category
FROM Product;

Operadores de comparación: =, <>, <, >, <=, >=
Operaciones aritméticas: +, -, *, /

Condición WHERE

IN Test de pertenencia a un conjunto

SELECT name, price
FROM Product
WHERE Manufacter IN (‘Amazon’, ‘Microsoft’);

SELECT name
FROM Product
WHERE (Manufacter, Category) IN ((‘Amazon’, ‘Tablet’),
(‘Microsoft’, ‘Tablet’));

LIKE: Simple String Pattern Matching

SELECT *
FROM Products
WHERE Name LIKE ‘%Air’;

Soporta 2 comodines
Underscore (_) matches exactly one character
(equivalent to ? in the UNIX shell)
Percent (%) matches 0 or more characters
(equivalent to * in the UNIX shell)

Buscar nombres de productos cuyo nombre de fabricante comience con ‘A’:

SELECT name
FROM Product
WHERE Manufacter LIKE ’A%’;

Buscar el nombre y el precio de productos que contengan la palabra Air:

SELECT name, price
FROM Product
WHERE name LIKE ‘%Air%;

Buscar empleados que tienen el valor NULL en el atributo salario

SELECT *
FROM employee
WHERE salary IS NULL;

SQL: ORDER BY

Ordena las tuplas en una consulta basada en los valores de algunos atributos
El orden por defecto es el orden ascendentes de los valores (ASC)

Ordenar los empleados por el valor de sus salarios en orden descendente:

SELECT fname, lname, salary
FROM employee
ORDER BY salary DESC;

Ordenar los empleados por el valor de sus salarios, y para salarios con el mismo valor, por sus apellidos.

SELECT fname, lname, salary
FROM employee
ORDER BY salary, lname;

LIMIT: Limita el resultado a una cantidad especificada de tuplas

SELECT <attribute list>
FROM <table list>
WHERE <condition on the tables>
LIMIT <number of tuples>;

Puede ser usado con ORDER BY para obtener un valor máximo o mínimo

Nota: Para usar en SQL Server se dbe remplazar por TOP (31)

SELECT TOP (31) fname, lname, salary
FROM employee
ORDER BY salary, lname;

Mostrará 31 registros.

