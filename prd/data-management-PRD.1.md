# GESTION DE DATOS - PRD

## 1. Resumen

El area de gestion de datos es la encarga de globalizar todos los datos para mandar un reporte general al gerente a travez del sistema diseñado en excel.

## 2. Objetivos

### 2.1 Objetivo general

Reemplazar el formulario de "Ventas de produccion" simplificando las formulas que este usa, para tener un mejor rendimiento y menor cantidad de errores tanto de typeo como de entrega de datos erroneos.

### 2.2 Objetivos especificos

* Crear un formulario que supla el formulario que se usa actualmente en el area de gestion de datos.
* Crear un formulario aparte para el llenado de datos enlazado al formulario principal directamente desde la seccion de almacen.
* Crear un nuevo sistema de reportes enlazado con los formularios de gestion de datos previamente creados.

## 3. Alcance y limites

### 3.1 Alcance

Se hara un formulario para facilitar el llenado de datos del area "Gestion de datos" para su seccion de "Ventas de fabrica" el cual estara conectado con otro formulario que se le dara a la seccion de "Almacen" en el cual se debera ingresar los datos de las salidas diarias.

### 3.2 Limites

No trasladaremos los datos llenados anteriormente en su sistema actual, el formato de llenado de datos no variara mucho, el sistema unicamente incluira datos de las salidas de venta de almacen y se mantendra el uso de formulas en el formulario.

## 4. Contexto y Antecedentes

### 4.1 Contexto actual

El area de gestion de datos es la encargada de englobalizar, filtrar y hacer un reporte al Gerente, este proceso se hace a travez de los reportes enviados por el area de: almacen. Esta area esta conformada por un supervisor y sus trabajadores, para que los reportes de esta area lleguen a manos del jefe de produccion que es el encargado de darle el visto bueno primero debe aprobarlo el supervisor de la seccion y posteriormente el reporte llega al area de gestion de datos para su respectivo englobalizado y filtrado, esto lo hace en base a su sitema de base de datos en la cual rellena manualmente toda la informacion para sacar sus reportes en su sistema recibe informacion de:

```
 Almacen 
 └──Ventas de fabrica
    |──Fecha (Fecha de salida del producto)
    |──N. de nota (Es el numero con el que se registra la salida de algun producto)
    |──Cliente (El nombre del destinatario al cual se entrega el producto)
    |──Titulo (El tipo de producto que se vendio con sus especificaciones)
    |──Bolsas (La cantidad de bolsas del mismo producto que se envio)
    |──Sueltos (La cantidad de producto fuer a de bolsa que se vendio)
    |──Cantidad total (La cantidad total de kilos que suman las bolsas y los sueltos)
    |──OBS. (Las observaciones que se tienen de dicha venta)
    └──Color (El color junto al codigo de color del producto vendido)

```

Cada uno de estos se almacena en las distintas celdas respectivamente asignadas por gestion de datos, una vez concluido esto los reportes se hacen arrastrando celdas en las distintas hojas de excel.
Los apartados usados actualmente en Gestion de datos son:

```
Gestion de datos
└──Ventas de fabrica
   |──Fecha (Fecha en la que se hizo la venta)
   |──N. de nota (El numero de salida, algo asi como una factura)
   |──Cliente (El cliente al cual se le vendio el producto)
   |──Titulo (Las especificaciones de el producto que es vendido)
   |──Bolsas (La cantidad de bolsas vendidas del producto)
   |──Sueltos (La cantidad de producto suelto que es vendido)
   |──Kilos Totales (La cantidad de kilos totales con las bolsas y los productos sueltos)
   |──Precio unitario (El precio por kilo del producto en bs)
   |──Precio total (El precio total de kilos y precio unitario en bs)
   |──Global (Es la ganancia hasta el mes en bs)
```
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

* Errores de typeo
* El hecho de que algunas formulas son eliminadas por accidente al momento de poner un valor equivocado en una celda que no era
* Otro problema es que para hacer los reportes se necesitan seleccionar las celdas manualmente de cada mes o año o dia dependiendo del reporte que se necesite
* Errores en el ingreso de datos por parte de los demas supervisores
* Aveces se olvidan meter un valor o se equivocan en alguna suma y aun asi
sin revisar pasan los datos al area de gestion de datos y eso causa errores de calculo
* La parte de la revision es tediosa y mayormente se tiene que revisar muchas hojas de reporte para encontrar un solo problema
* Muchos formularios del excel que maneja ya no se usan y el usuario crea manualmente otros formularios para el almacenado de sus datos o hacer formulas mas eficientes.

## 6. Requisitos

---------------------------------------------------------------------------------------------