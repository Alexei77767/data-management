# GESTION DE DATOS - PRD
## Resumen
El area de gestion de datos es la encarga de globalizar todos los datos para mandar un reporte general al gerente.

## Objetivos
### Objetivo general
Reemplazar el formulario simplificando las formulas que este usa, para tener un mejor rendimiento y menor cantidad de errores tanto de typeo como de entrega de datos erroneos
### Objetivos especificos
* Crear un formulario que supla las mismas necesidades de gestion de datos
* Crear un formulario aparte para el llenado de datos que llegan directamente de la seccion de almacen
* Crear un nuevo sistema de reportes enlazado con los formularios creados

## Alcance y limites
### Alcance 
Unicamente se tomara el apartado de almacen mas especificamente las salidas que tiene del apartado "Ventas fabrica" este no se trata de una base de datos ya que unicamente son formularios en hojas de calculo, se conectara con otro formulario el cual sera manejado por la seccion de almacen y los reportes se crearan automaticamente mientras el formulario sea llenado.

### Limites
No trasladaremos la "base de datos" entera, el formato de llenado de datos no variara mucho, el sistema unicamente incluira datos de las salidas de venta de almacen y se mantendra el uso de formulas en el formulario.

## Contexto y Antecedentes 
### Contexto
El area de gestion de datos es la encargada de englobalizar, filtrar y hacer un reporte al Gerente, este proceso se hace a travez de los reportes enviados por el area de: almacen. Esta area esta conformada por un supervisor y sus trabajadores, para que los reportes de esta area lleguen a manos del jefe de produccion que es el encargado de darle el visto bueno primero debe aprobarlo el supervisor de la seccion y posteriormente el reporte llega al area de gestion de datos para su respectivo englobalizado y filtrado, esto lo hace en base a su sitema de base de datos en la cual rellena manualmente toda la informacion para sacar sus reportes en su sistema recibe informacion de: 
* Almacen 
    * Fecha
    * N. de nota
    * Cliente
    * Titulo
    * N. de titulo
    * Tipo de titulo
    * Bolsas
    * Sueltos
    * Cantidad total (kg)
    * Kilos segun almacen (kg)
    * Precio 
    * Precio total
    * Verificar 
    * Global

Cada uno de estos se almacena en las distintas casillas respectivamente asignadas por gestion de datos, una vez concluido esto los reportes se hacen arrastrando casillas en las distintas hojas de excel.

### Antecedentes 
El sistema desde hace mucho tiempo se manejo del mismo formato al igual que los reportes no existen antecedentes de como era el llenado de datos antes de que tengan el sistema fucnionando 

## Problemas
Los problemas principales del sistema en su mayoria son errores de typeo, y el hecho de que algunas formulas son eliminadas por accidente al momento de poner un valor equivocado en una celda que no era, otro problema es que para hacer los reportes se necesitan seleccionar las celdas manualmente de cada mes o año o dia, dependiendo del reporte que se necesite, errores en el ingreso de datos por parte de los demas supervisores, aveces se olvidan meter un valor o se equivocan en alguna suma y aun asi, sin revisar pasan los datos al area de gestion de datos y eso causa errores de calculo, la parte de la revision es tediosa y mayormente se tiene que revisar muchas hojas de reporte para encontrar un solo problema, muchos formularios del excel que esta hecho ya no se usan y el usuario crea manualmente otros formularios para el almacenado de sus datos o hacer formulas mas eficientes.

## Requisitos
---------------------------------------------------------------------------------------------