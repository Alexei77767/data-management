# GESTION DE DATOS - PRD

## Resumen

El area de gestion de datos es una de las areas principales que globalizan todos los datos para mandar un reporte general al gerente.

## Alcance y limites

### Alcance

El alcance del proyecto sera de idear una solucion temporal al typeo de el programa de gestion de datos con la implementacion de formularios temporales para que el llenado venga directamente de almacen, esto va a incluir las areas de el llenado de datos de Almacen por el momento las cuales son:

* Fecha
* Numero de nota
* Cantidad
* Cliente
* Titulo
* Bolsas
* Sueltos
* Kilos en general
* Precio por kilos
* Precio total (Kilos en general * Precio)

### Limites

Los limites son que no vamos a trasladar la base de datos entera y por el momento sera una solucion basica, tampoco implemetaremos el area de produccion por el momento pero de igual forma se empesara a forumlar como seria la base mas optima para su sistema.

## Contexto y Antecedentes

### Contexto

El area de gestion de datos es la encargada de englobalizar, filtrar y hacer un reporte al Gerente, este proceso se hace a travez de distintas areas como ser: almacen y produccion. Cada una de estas areas esta conformado por un supervisor y sus trabajadores, para que los reportes de estas areas lleguen a manos del jefe de produccion que es el encargado de darle el visto bueno y posteriormente el reporte llegua al area de gestion de datos para su respectivo englobalizado y filtrado, esto lo hace en base a su sitema de base de datos en la cual rellena manualmente toda la informacion para sacar sus reportes en su sistema recibe informacion de:

* Almacen
  * Ovillo
  * MP (Materia Prima)
  * Distribuidora
  * Bolsas y etiquetas
  * Tintoreria
  * Entrega de fardos
  * Industrial
* Produccion
  * Pasajes
  * Preparacion
  * Continuado
  * Bobinado
  * Acoplado
  * Retorcido
  * Madejeado
  * Tintoreria
  * Secado
  * Devanado
  * Embolsado
  * Ovillado
  * Almacen IND (Almacen Industrial)
  * Almacen OVI (Almacen Ovillo)
    Cada uno de estos se almacena en las distintas casillas respectivamente asignadas por gestion de datos, una vez concluido esto los reportes se hacen arrastrando casillas en las distintas hojas de excel

#### Area de almacen

En esta area se registran las salidas de los productos especificando los distintos detalles como ser:

* Fecha
* Numero de Nota
* Cantidad de titulos distintos comprados por un solo numero de nota
* Cliente
* Titulo
* Bolsas
* Producto fuera de bolsa (Suelto)
* Cantidad de kilos totales de bolsas y sueltos
* Precio
* Cantidad vendida en total (Precio * Cantidad de Kilos totales)
  Estos apartados se llenan de manera manual cada uno incluyendo las formulas para sumar las bolsas y los sueltos para alcanzar su cantidad en kilos respectivo.

#### Materia Prima

En el area de materia prima se registran los camiones, el tipo de material que llega, ingresos en fardos, en kilos, las salidas de las fardos y el stock en existencia. estos reportes igual son entregados al gerente las divisiones son:

* Fecha
* Camion
* Ingreso en Kilos
* Ingreso en fardos
* Salida en kilos
* Salida en fardos
* Stock Total en Kilos
* Stock total en camiones
  -----------------------Falta Completar-----------------------
  Para llenar estos datos, almacen entrega las etiquetas de los fardos que le llegan y posteriormente son digitalizados para su respectivo reporte

#### Area de produccion

En el area de produccion se registra el trabajo de cada sector y el reporte que se envia a gestion de datos es un resumen diario de lo que pasa en cada sector de la planta los sectores son:

* Pasajes
* Preparacion
* Continuado
* Bobinado
* Acoplado
* Retorcido
* Madejeado
* Tintoreria
* Secado
* Devanado
* Embolsado
* Ovillado
* Almacen IND (Almacen Industrial)
* Almacen OVI (Almacen Ovillo)
  El supervisor de produccion se encarga de estructurar el reporte para posteriormente ser enviado a gestion de datos ser digitalizado

### Antecedentes

El sistema desde hace mucho tiempo se manejo del mismo formato al igual que los reportes no existen antecedentes de como era el llenado de datos antes de que tengan el sistema fucnionando

## Problemas

Los problemas principales del sistema en su mayoria son errores de typeo, y el hecho de que algunas formulas son eliminadas por accidente al momento de poner un valor equivocado en una celda que no era, otro problema es que para hacer los reportes se necesitan seleccionar las celdas manualmente de cada mes o año o dia, dependiendo del reporte que se necesite, errores en el ingreso de datos por parte de los demas supervisores, aveces se olvidan meter un valor o se equivocan en alguna suma y aun asi, sin revisar pasan los datos al area de gestion de datos y eso causa errores de calculo, la parte de la revision es tediosa y mayormente se tiene que revisar muchas hojas de reporte para encontrar un solo problema, muchos formularios del excel que esta hecho ya no se usan y el usuario crea manualmente otros formularios para el almacenado de sus datos o hacer formulas mas eficientes.

## Requisitos

---

