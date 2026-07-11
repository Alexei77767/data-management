# GESTION DE DATOS - PRD

## 1. Resumen

El area de gestion de datos es la encarga de globalizar todos los datos para mandar un reporte general al gerente a travez del sistema diseñado en excel.

## 2. Objetivos

### 2.1 Objetivo general

Reemplazar el formulario simplificando las formulas que este usa, para tener un mejor rendimiento y menor cantidad de errores tanto de typeo como de entrega de datos erroneos.

### 2.2 Objetivos especificos

* Crear un formulario que supla las necesidades de gestion de datos.
* Crear un formulario aparte para el llenado de datos directamente de la seccion de almacen.
* Crear un nuevo sistema de reportes enlazado con los formularios de gestion de datos previamente creados.

## 3. Alcance y limites

### 3.1 Alcance

Unicamente se tomara el apartado de almacen mas especificamente las salidas que tiene del apartado "Ventas fabrica", se hara en un formulario, se conectara con otro formulario el cual sera manejado por la seccion de almacen y los reportes se crearan automaticamente mientras el formulario sea llenado.

### 3.2 Limites

No trasladaremos los datos llenados anteriormente en su sistema actual, el formato de llenado de datos no variara mucho, el sistema unicamente incluira datos de las salidas de venta de almacen y se mantendra el uso de formulas en el formulario.

## 4. Contexto y Antecedentes

### 4.1 Contexto

El area de gestion de datos es la encargada de englobalizar, filtrar y hacer un reporte al Gerente, este proceso se hace a travez de los reportes enviados por el area de: almacen. Esta area esta conformada por un supervisor y sus trabajadores, para que los reportes de esta area lleguen a manos del jefe de produccion que es el encargado de darle el visto bueno primero debe aprobarlo el supervisor de la seccion y posteriormente el reporte llega al area de gestion de datos para su respectivo englobalizado y filtrado, esto lo hace en base a su sitema de base de datos en la cual rellena manualmente toda la informacion para sacar sus reportes en su sistema recibe informacion de:

```
 Almacen 
 |──Fecha
 |──N. de nota
 |──Cliente
 |──Titulo
 |──N. de titulo
 |──Tipo de titulo
 |──Bolsas
 |──Sueltos
 |──Cantidad total (kg)
 |──Kilos segun almacen (kg)
 |──Precio 
 |──Precio total
 └──Global
```

Cada uno de estos se almacena en las distintas celdas respectivamente asignadas por gestion de datos, una vez concluido esto los reportes se hacen arrastrando celdas en las distintas hojas de excel.

### 4.2 Antecedentes

El sistema desde hace mucho tiempo se manejo del mismo formato al igual que los reportes no existen antecedentes de como era el llenado de datos antes de que tengan el sistema fucnionando.

### 4.3 Actores y responsabilidades

| Actor                 | Depende de         | Responsabilidad                                                                                                              |
| --------------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| Gerente               |                    | Recepcion de reportes y verificacion de que todo marcha bien                                                                 |
| Gestion de datos      | Gerente            | Englobalizacion de datos para posteriormente crear un reporte general                                                        |
| Jefe de produccion    | Gerente            | Aprobacion de los datos de almacen                                                                                           |
| Supervisor de almacen | Jefe de produccion | Encargado de recolectar los datos de almacen y hacer que el jefe de produccion lo revise para ser enviado a gestion de datos |

## 5. Problemas

Los problemas principales del sistema en su mayoria son errores de typeo, el hecho de que algunas formulas son eliminadas por accidente al momento de poner un valor equivocado en una celda que no era, otro problema es que para hacer los reportes se necesitan seleccionar las celdas manualmente de cada mes o año o dia, dependiendo del reporte que se necesite, errores en el ingreso de datos por parte de los demas supervisores, aveces se olvidan meter un valor o se equivocan en alguna suma y aun asi, sin revisar pasan los datos al area de gestion de datos y eso causa errores de calculo, la parte de la revision es tediosa y mayormente se tiene que revisar muchas hojas de reporte para encontrar un solo problema, muchos formularios del excel que maneja ya no se usan y el usuario crea manualmente otros formularios para el almacenado de sus datos o hacer formulas mas eficientes.

## 6. Requisitos

---------------------------------------------------------------------------------------------