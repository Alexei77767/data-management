# GESTION DE DATOS - PRD

Define el proceso de gestion de datos de las distintas areas:

* [docs/research/warehouse/bags-and-labels.md](./warehouse/bags-and-labels.md)
* [docs/research/warehouse/dyehouse.md](./warehouse/dyehouse.md)
* [docs/research/warehouse/finished-product.md][def]
* [docs/research/warehouse/sic-jac-reports.md](./warehouse/sic-jac-reports.md)

## 1. Proposito y alcance

### 1.1 Proposito

Sistematizar el area de gestion de datos responsable de almacenar los datos generales de las diferentes areas ya dichas para tener un reporte mas general de como le esta yendo a la empresa

### 1.2 Alcance

Cubre los reportes que son enviados por los diferentes encargados de area principalmente:

| Area             | Archivo                    | Descripcion                                                                                |
| ---------------- | -------------------------- | ------------------------------------------------------------------------------------------ |
| Finished Product | [finished-product.md][def] | Son los datos de industrial y ovillo que son enviados en reporte hacia la gestion de datos |
| Raw Material     |                            | Son los datos de materia prima que le llegan directamente de almacen para ser reportados   |

### 1.3 Limites del sistema

| Limite     | Detalle                                                                                                                                                            |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Entrada    | Los reporte son entregados por el encargado de area de almacen y produccion en sus respectivas hojas de reporte cada uno                                           |
| Salida     | Los reportes son digitalizados en el sistema de gestion de datos posteriormente son revisados y corroborados tanto en la version digital como en la version fisica |
| No Incluye | Se filtran muchos datos con respecto a los reportes entregados, solo se ingresa los datos mas generales de cada area                                               |

## 2. Estructura Organizacional

### 2.1 Organigrama de operacion

```
Gestion de datos
|
|──Jefe de produccion
|  ├── Autoriza emisiones de MP
│  ├── Supervisa ambas unidades (Almacén + Operación)
│  ├── Verifica coherencia (MP emitida vs lotes producidos)
│  └── Consolida reporte diario a Gerencia
|
|──Unidad de Almacen
|  |
|  └──Supervisor
|     |──Autoriza entradas y salidas de almacen
|     |──Responsable de almacen
|     |──Entrega de reportes diarios a gestion de datos
|     |──Seguimiento a embolsado
|     |──Almacenado de los diferentes productos
|     |──Seguimiento continuo de la MP 
|     |──Manejo de reportes industrial y ovillado
|     └──Almacenado de bolsas y etiquetas 
|
|──Unidad de Produccion
```

### 2.2 Actores y responsabilidades

| Actor                    | Depende de         | Reponsabilidad en el sistema                                                  |
| ------------------------ | ------------------ | ----------------------------------------------------------------------------- |
| Gestion de datos         | Dueño de fabrica  | El encargado de pasarle todos los reportes generales al dueño de la fabrica  |
| Supervisor de almacen    | Jefe de produccion | El encargado de pasarle los reportes diarios de almacen a Gestion de datos    |
| Supervisor de Produccion | Jefe de produccion | El encargado de pasarle los reportes diarios de produccion a Gestion de datos |

## 3. Procesos productivos

El encargado de gestion de datos tiene el rol de recibir los distintos reportes digitalizarlos e ordenarlos donde correspondan sacando sus propios reportes ya sean semanales/mensuales/anuales, estos reportes son entregados directamente al dueño de la fabrica

### 3.1 Vision general

```
Gestion de datos
|
|──Almacen
|  |
|  └──Entrega de reportes diarios
|     |
|     |──Ovillo
|     |──MP
|     |──Distribuidora
|     |──Bolsas y etiquetas
|     |──Tintoreria
|     |──Entrega de fardos
|     └──Industrial
|
└──Produccion
   |
   └──Entrega de reportes diarios
      |
      |──Pasajes
      |──Preparacion 
      |──Continuado
      |──Bobinado
      |──Acoplado
      |──Retorcido
      |──Madejeado
      |──Tintoreria
      |──Secado
      |──Devanado 
      |──Embolsado
      |──Ovillado
      |──Almacen IND (Almacen Industrial)
      └──Almacen OVI (Almacen Ovillado)
```

### 3.2 Almacen

Almacen le envia los reportes diarios de entradas y salidas de las diferentes areas que maneja:

| Area       | Detalle                                                                                                                                                                                                     |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ovillo     | El reporte es diario mayormente se dan las salidas de este, en bolsas o en producto suelto, este llega con un numero de nota y todas las especificaciones necesarias                                        |
| MP         | El reporte se hace cada que llega nueva materia prima esta es almacenada en fardos y kilos, mayormente se registran las entradas de este, se entrega un reporte unicamente con los datos necesarios de este |
| Industrial | El reporte es diario mayormente de las salidas, en esta especifican el cliente el titulo junto a un numero de nota y la cantidad de bolsas y producto suelto                                                |

### 3.3 Produccion

Produccion le envia reportes diarios de que tanto a producido una sector en especifico, esta maneja varios sectores como ser:

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
* Almacen Industrial
* Almacen Ovillado

## 4. Reglas de negocio transverales

### 4.1 Flujo de informacion

En gestion de datos los distintos reportes son entregados por los supervisores de las diferentes areas correspondientes: Produccion y Ovillado. Estas pasan por un proceso de filtrado, ya que no todos los datos son necesarios para el area de gestion de datos, una vez iltrado se recibe en gestion de datos y se digitaliza

### 4.2 Roles y responsabilidades

| Roles                    | Responsabilidades                                                                                                                                    |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Jefe de Fabrica          | Recibir reportes y corroborar que todo este correcto                                                                                                 |
| Jefe de Produccion       | Supervisar todo el proceso de la fabrica, asi mismo autorizar los distintos reportes que se le son entregados                                        |
| Gestion de recursos      | Encargado de digitalizar todos los reportes y sacar una conclusion final de cada uno para crear un nuevo reporte que es entregado al jefe de fabrica |
| Supervisor de Almacen    | Encargado de autorizar los reportes para que sean entregados al jefe de produccion, dirigir a todo el personal y hacer que sus datos cuadren         |
| Supervisor de Produccion | Encargado de autorizar los reportes para que sean entregados al jefe de produccion, dirigir a todo el personal y hacer que sus datos cuadren         |

### 4.3 Gestion de errores y duplicados

Los errores en esta area son frecuentes y con su sistema actual es muy riesgoso cometerlos y tedioso de arreglarlos los errores mas frecuentes son en el apartado de Almacen y Produccion al momento de entregar sus reportes o se olvidan un dato o directamente esta mal formulado erroneo en una formula o en algun dato, estos se revisan uno por uno cada reporte diario hasta encontrar el dato erroneo

### 4.4 Inmutabilidad y Trazabilidad

Al momento de querer cambiar algun dato, este se puede editar sencillamente cambiando el valor en la celda pero no siempre es optimo por el hecho de que puede alterar varias casillas del sistema y para arreglarlo se necesita editar muchas otras a la vez

### 4.5 Reporte diario y consolidado

Los reportes diarios son acompañados por un reporte global que normalmente va englobando los reportes hasta donde se tiene del mes para que el encargado de gestion de datos verifique que esta ingresando los datos correctamente y tambien se corrobore con lo que ya tiene hasta el momento

## 5 Planificacion de Gestion de Datos

La planificacion para la gestion de datos inicia de los reportes que son enviados y de su almacenamiento luego de esto se deriva en varios reportes adicionales

### 5.1 Volumen fijo base de datos

Aproximadamente los datos que son ingresados mensualmente son 360 unicamente de almacen y produccion 
240 archivos recibidos por documentos en linea de almacen
60 archivos recibidos en fisico por almacen
60 archivos recibidos en fisico por produccion

### 5.2 Responsable de planificacion de datos

El encargado de Gestion de datos es quien organiza los datos de los reportes que le van llegando diaramente, almacenandolos, categorizandolos y acomodandolos para el reporte al jefe de fabrica para su respectiva revision

### 5.3 Implicaciones para el sistema de datos

En el sistema se debe poder visualizar lo planificado con la parte real en volumenes de registros por categorias y periodos, se deben generar alertas si algun dato es erroneo o no cuadra con los distintos datos que son presentados en reportes globales

## 6. Subdominios y archivos

## 7. Desiciones diferidas

## 8. Glosario

[def]: ./warehouse/finished-product.md
