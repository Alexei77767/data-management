# ADMINISTRACIÓN DE DATOS - PRD

## 1. Resumen

El Área de Administración de Datos es responsable de consolidar la información generada por las distintas unidades de la empresa para elaborar los informes generales destinados a la Gerencia. Actualmente, este proceso se realiza mediante hojas de Excel que requieren un ingreso manual de datos intensivo y el uso de numerosas fórmulas.

---

## 2. Objetivos

### 2.1 Objetivo General

Desarrollar un nuevo sistema basado en Google Sheets que reemplace el formulario actual de “Ventas de Producción”, simplificando el ingreso de datos, reduciendo errores y mejorando el desempeño global del proceso de elaboración de reportes.

### 2.2 Objetivos Específicos

* Diseñar un formulario principal para el Área de Administración de Datos que sustituya al sistema actualmente utilizado.
* Desarrollar un formulario independiente para la unidad de Almacén que permita registrar las salidas de producto de manera clara y estandarizada.
* Integrar ambos formularios para que la información registrada en Almacén se transfiera automáticamente al formulario principal de Administración de Datos.
* Implementar un sistema de reportes que permita generar información consolidada de forma más rápida y eficiente.

---

## 3. Alcance y Límites

### 3.1 Alcance

Se desarrollará un sistema compuesto por tres formularios:

1. Un formulario para el registro de salidas de productos en la unidad de Almacén.
2. Un formulario que sirva de puente entre los formularios de Almacén y Administración de Datos.
3. Un formulario principal para el Área de Administración de Datos.

Estos formularios estarán interconectados para que la información registrada en Almacén se incorpore automáticamente al sistema de Administración de Datos, facilitando la generación de reportes de ventas de fábrica.

### 3.2 Límites

* No se migrará la totalidad de los datos históricos registrados en el sistema actual; únicamente se migrarán los datos correspondientes al año 2026.
* El formato general de ingreso de datos se mantendrá similar al utilizado actualmente para facilitar la adaptación de los usuarios.
* El sistema se enfocará exclusivamente en el registro y procesamiento de las ventas gestionadas por la unidad de Almacén.
* Se continuará utilizando formularios como plataforma principal de trabajo.
* Algunas operaciones seguirán dependiendo de fórmulas internas del sistema.

---

## 4. Contexto y Antecedentes

### 4.1 Contexto Actual

El Área de Administración de Datos es responsable de recopilar, organizar, filtrar y consolidar la información de ventas para generar los informes dirigidos a la Gerencia.

Actualmente, la información proviene de la unidad de Almacén. Antes de llegar al Área de Administración de Datos, los registros son revisados y aprobados por el Supervisor de Almacén y, posteriormente, por el Jefe de Producción.

El reporte de ventas generado por Almacén contiene la siguiente información:

```
Almacén
└── Ventas de Fábrica
    ├── Fecha
    ├── N.º de Nota
    ├── Cliente
    ├── Título
    ├── Bolsas
    ├── Sueltos
    ├── Cantidad Total
    ├── Observaciones
    └── Color
```

**Descripción de los campos:**

* **Fecha:** Fecha de salida del producto.
* **N.º de Nota:** Identificador de la salida registrada, definido por el sistema mediante un contador.
* **Cliente:** Persona o empresa que recibe el producto.
* **Título:** Especifica formato, título y material.
* **Bolsas:** Cantidad de bolsas despachadas.
* **Sueltos:** Cantidad de piezas vendidas fuera de bolsa.
* **Cantidad Total:** Peso total de bolsas y piezas sueltas del producto vendido.
* **Observaciones:** Comentarios o información adicional sobre la venta.
* **Color:** Color y código correspondiente del producto.

Posteriormente, esta información se transcribe manualmente al sistema utilizado por Administración de Datos.

La estructura principal utilizada actualmente es la siguiente:

```
Administración de Datos
└── Ventas de Fábrica
    ├── Fecha
    ├── N.º de Nota
    ├── Cliente
    ├── Título
    ├── Bolsas
    ├── Sueltos
    ├── Kilos Totales
    ├── Precio Unitario
    ├── Precio Total
    ├── Resumen diario
    ├── Resumen mensual
    └── Resumen anual
```

**Descripción de los campos adicionales:**

* **Kilos Totales:** Peso total entre bolsas y kilos vendidos.
* **Precio Unitario:** Precio por kilogramo del producto.
* **Precio Total:** Resultado de multiplicar los kilos totales por el precio unitario.
* **Resumen diario:** Acumulado de ventas correspondiente al día.
* **Resumen mensual:** Acumulado de ventas correspondiente al mes.
* **Resumen anual:** Acumulado de ventas correspondiente al año.

Actualmente, gran parte de los reportes se generan mediante fórmulas y selección manual de datos, lo que incrementa el tiempo de trabajo y la posibilidad de errores.

### 4.2 Antecedentes

El sistema actual ha sido utilizado durante varios años con pocas modificaciones significativas. No se dispone de información detallada sobre versiones anteriores ni sobre procedimientos anteriores al sistema implementado en la actualidad.

### 4.3 Actores y Responsabilidades

| Actor                  | Depende de          | Responsabilidad                                                         |
| ---------------------- | ------------------- | ----------------------------------------------------------------------- |
| Gerente                | -                   | Recibir y revisar los reportes generales de la empresa.                 |
| Administración de Datos | Gerente             | Consolidar la información y elaborar reportes generales.                |
| Jefe de Producción    | Gerente             | Revisar y aprobar la información proveniente de Almacén.                |
| Supervisor de Almacén | Jefe de Producción | Registrar y verificar las salidas de productos antes de su aprobación. |

---

### 4.5 Contexto de productos

En la fábrica se manejan distintas unidades y presentaciones, organizadas por lotes que comparten color, presentación y un peso estándar —por ejemplo, conos de 205 kg y ovillos de 202 kg—. Además, según la presentación varía la cantidad de conos u ovillos que entran en una bolsa. Normalmente los ovillos se empaquetan en alrededor de 15 bolsitas con 5 unidades cada una, y los conos se agrupan en 4 o 6 unidades según el tipo de material o el peso.

Antes de convertirse en ovillos o conos, las fibras se ensamblan en moños que reúnen 10 madejas (un moño pesa 5 kg y cada madeja 0,5 kg). El peso de cada bolsa depende del tipo de material utilizado en la fabricación y de la presentación elegida por el cliente; por esta razón, algunas bolsas pueden pesar más y otras menos. El formato de pedido lo gestiona el encargado de comercialización, quien acuerda el precio con el cliente; la fábrica produce el lote solicitado y el pago se realiza tras la entrega, siendo gestionado por comercialización.

Los pedidos se realizan por lotes y color, y los materiales que presentan variaciones de tono o defectos se comercializan como calidad “mixto” al 50 % del precio original, reuniendo piezas de distintos lotes. Asimismo, las piezas clasificadas como desperdicio se ofrecen a clientes a precio reducido. Todos los movimientos se registran por lote y color para asegurar la trazabilidad y facilitar los controles de calidad.

En caso de que el producto presente alguna imperfeccion como ser su teñido primero se intenta volver al teñir, si se logra arreglar se toma como producto bueno, si no resulta el producto va a la seccion de recuperado, en donde se remata a mitad de precio, los conos que pesan menos de lo debido se sacan de los conos y se meten en una bolsa junto a otros que no cumplen el peso debido este es conocido como "Mixto" que son varios conos sin los conos de distintos colores.

## 5. Problemas Identificados

* Errores de digitación durante el ingreso manual de información.
* Eliminación accidental de fórmulas al modificar celdas incorrectas.
* Generación de reportes mediante selección manual de datos, lo que incrementa el tiempo de trabajo.
* Inconsistencias en la información registrada por diferentes usuarios.
* Omisión de datos o errores de cálculo que pueden pasar desapercibidos durante las revisiones.
* Proceso de validación lento debido a la necesidad de revisar múltiples hojas y registros.
* Existencia de formularios obsoletos que ya no se utilizan.
* Creación manual de nuevas hojas y formularios para suplir las limitaciones del sistema actual.
* Dificultad para mantener la integridad y consistencia de la información a medida que aumenta el volumen de datos.

---

## 6. Requisitos

### 6.1 Requisitos funcionales

* El formulario de Almacén registrará los siguientes datos: fecha, título, número de nota, cliente, bolsas, peso unitario de bolsas, sueltos, peso unitario de sueltos, número de lote, color, código de color y observaciones.
* Los campos obligatorios serán: fecha, título, número de nota, cliente, bolsas, peso unitario de bolsas, sueltos, peso unitario de sueltos, número de lote, color y código de color.
* Las observaciones serán opcionales, pero estarán disponibles para registrar comentarios adicionales sobre cada salida.
* El formulario de Administración de Datos debe recibir automáticamente la información proveniente de Almacén una vez al día, entre las 23:00 y las 02:00, de manera definitiva y en una sola dirección, para minimizar el riesgo de errores manuales.
* El sistema calculará automáticamente: kilos totales, precio total y los totales diarios, mensuales y anuales a partir de los registros ingresados.
* El Área de Administración de Datos verificará la información ingresada el día siguiente. Si se detecta algún error, se notificará inmediatamente a la unidad de Almacén para su corrección.

### 6.2 Requisitos no funcionales

* El sistema debe ser intuitivo y familiar para los usuarios porque se basa en el esquema actual, pero con mayor automatización.
* El rendimiento debe ser óptimo en la ejecución de cálculos y actualizaciones de datos.
* La actualización de datos programada debe realizarse un día después del ingreso para disminuir la probabilidad de errores.
* No se requiere una versión específica de Google Sheets para el formulario, pero se utilizarán restricciones de celda en las columnas con fórmulas para impedir su edición directa.
* Las celdas con fórmulas no se podrán editar manualmente; en caso de ingresar datos inválidos, el sistema mostrará una indicación de error.
* La actualización de datos debe evitar la edición simultánea durante la sincronización, ya que se han identificado problemas de espacios en blanco en la hoja de Administración de Datos cuando se edita mientras se sincroniza.
* El diseño debe permitir actualizaciones y cambios futuros sin afectar la estructura general del sistema.

### 6.3 Requisitos de datos

* Solo se migrarán los datos correspondientes al año 2026.
* Los datos ingresados pueden ser de tipo texto o numérico, siempre respetando el formato definido para cada campo.
* El sistema debe validar los formatos y mostrar alertas cuando se detecte un valor incorrecto.
* El registro debe incluir información de origen y, cuando corresponda, el estado de aprobación por la unidad de Almacén y el Área de Administración de Datos.

### 6.4 Requisitos de integración

* Los tres formularios se conectarán entre sí mediante un proceso automatizado en Google Sheets que copie y sincronice la información.
* La sincronización se realizará una vez al día, entre las 23:00 y las 02:00, de forma automática y definitiva.
* La transferencia de datos será unidireccional: desde el formulario de la unidad de Almacén hacia el formulario de Administración de Datos.
* El formulario de la unidad de Almacén servirá como fuente principal y copia de seguridad de los registros diarios.
* La transferencia de datos debe ser segura y verificable para garantizar la consistencia entre los formularios.

### 6.5 Requisitos de calidad

* El sistema debe reducir significativamente los errores de digitación mediante controles de validación y automatización.
* Se deben evitar duplicados mediante reglas de validación y revisión de los registros en el Área de Administración de Datos.
* Los datos ingresados deben cotejarse con los reportes físicos disponibles en caso de discrepancias.
* El formulario debe ser sencillo de usar y requerir una capacitación mínima para los usuarios.

### 6.6 Requisitos de exclusión

* El sistema no generará facturas ni creará números de nota nuevos.
* No se incorporará información adicional que no provenga de los registros físicos existentes.
* No se desarrollarán funciones de contabilidad, facturación o inventario completo fuera del alcance definido.