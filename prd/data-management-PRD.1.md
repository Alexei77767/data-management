# GESTIÓN DE DATOS - PRD

## 1. Resumen

El área de Gestión de Datos es responsable de consolidar la información generada por las distintas unidades de la empresa para elaborar los informes generales destinados a la Gerencia. Actualmente, este proceso se realiza mediante hojas de Excel que requieren un ingreso manual de datos intensivo y el uso de numerosas fórmulas.

---

## 2. Objetivos

### 2.1 Objetivo General

Desarrollar un nuevo sistema basado en Excel que reemplace el formulario actual de “Ventas de Producción”, simplificando el ingreso de datos, reduciendo errores y mejorando el desempeño global del proceso de elaboración de reportes.

### 2.2 Objetivos Específicos

* Diseñar un formulario principal para el área de Gestión de Datos que sustituya al sistema actualmente utilizado.
* Desarrollar un formulario independiente para la unidad de Almacén que permita registrar las salidas de producto de manera clara y estandarizada.
* Integrar ambos formularios para que la información registrada en Almacén se transfiera automáticamente al formulario principal de Gestión de Datos.
* Implementar un sistema de reportes que permita generar información consolidada de forma más rápida y eficiente.

---

## 3. Alcance y Límites

### 3.1 Alcance

Se desarrollará un sistema compuesto por tres formularios:

1. Un formulario para el registro de salidas de productos en la unidad de Almacén.
2. Un formulario que sirva de puente entre los formularios de “Almacén” y “Gestión de Datos”.
3. Un formulario principal para el área de Gestión de Datos.

Estos formularios estarán interconectados para que la información registrada en Almacén se incorpore automáticamente al sistema de Gestión de Datos, facilitando la generación de reportes de ventas de fábrica.

### 3.2 Límites

* No se migrará la totalidad de los datos históricos registrados en el sistema actual; únicamente se migrarán los datos correspondientes al año 2026.
* El formato general de ingreso de datos se mantendrá similar al utilizado actualmente para facilitar la adaptación de los usuarios.
* El sistema se enfocará exclusivamente en el registro y procesamiento de las ventas gestionadas por la unidad de Almacén.
* Se continuará utilizando formularios como plataforma principal de trabajo.
* Algunas operaciones seguirán dependiendo de fórmulas internas del sistema.

---

## 4. Contexto y Antecedentes

### 4.1 Contexto Actual

El área de Gestión de Datos es responsable de recopilar, organizar, filtrar y consolidar la información de ventas para generar los informes dirigidos a la Gerencia.

Actualmente, la información proviene de la unidad de Almacén. Antes de llegar a Gestión de Datos, los registros son revisados y aprobados por el Supervisor de Almacén y, posteriormente, por el Jefe de Producción.

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

Posteriormente, esta información se transcribe manualmente al sistema utilizado por Gestión de Datos.

La estructura principal utilizada actualmente es la siguiente:

```
Gestión de Datos
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
| Gestión de Datos       | Gerente             | Consolidar la información y elaborar reportes generales.                |
| Jefe de Producción     | Gerente             | Revisar y aprobar la información proveniente de Almacén.                |
| Supervisor de Almacén  | Jefe de Producción  | Registrar y verificar las salidas de productos antes de su aprobación.  |

---

### 4.5 Contexto de productos

En la fábrica se manejan distintas unidades y presentaciones, organizadas por lotes que comparten color, presentación y un peso estándar —por ejemplo, conos de 205 kg y ovillos de 202 kg—. Además, según la presentación varía la cantidad de conos u ovillos que entran en una bolsa. Normalmente los ovillos se empaquetan en alrededor de 15 bolsitas con 5 unidades cada una, y los conos se agrupan en 4 o 6 unidades según el tipo de material o el peso.

Antes de convertirse en ovillos o conos, las fibras se ensamblan en moños que reúnen 10 madejas (un moño pesa 5 kg y cada madeja 0,5 kg). El peso de cada bolsa depende del tipo de material utilizado en la fabricación y de la presentación elegida por el cliente; por esta razón, algunas bolsas pueden pesar más y otras menos. El formato de pedido lo gestiona el encargado de comercialización, quien acuerda el precio con el cliente; la fábrica produce el lote solicitado y el pago se realiza tras la entrega, siendo gestionado por comercialización.

Los pedidos se realizan por lotes y color, y los materiales que presentan variaciones de tono o defectos se comercializan como calidad “mixto” al 50 % del precio original, reuniendo piezas de distintos lotes. Asimismo, las piezas clasificadas como desperdicio se ofrecen a clientes a precio reducido. Todos los movimientos se registran por lote y color para asegurar la trazabilidad y facilitar los controles de calidad.

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

El formulario de almacen capturara datos de: fecha, titulo, N.nota, cliente, bolsas, peso unitario de bolsas, sueltos, peso unitario de sueltos, resumen diario, resumen mensual, resumen anual, N. de lote, color, codigo de color y observaciones, los campos de: fecha, titulo, N.nota, cliente, bolsas, peso unitario de bolsas, sueltos, peso unitario de sueltos, resumen diario, resumen mensual y resumen anual. Deben ser obligatorios las partes de: N. de lote, color, codigo de color y observaciones. Pueden omitirse ya que para el apartado de gestion de datos no son muy necesarios, la transferencia automatica de los datos sera una vez al dia entre las 11pm-2am automaticamente para evitar errores, los calculos del sistema seran automaticos en cuanto a las multiplicaciones de las distintas ventas y los resuemenes diarios, mensuales y anuales. una vez ingresado la venta al dia siguiente se hara la verificacion de los datos en el area de administracion de datos, si existe algun tipo de error se notificara inmediatamente a la unidad de almacen para su edicion. 

### 6.2 Requisitos no funcionales

El sistema es simple y deberia poder adaptarse muy bien a los usuarios por que es una copia del sistema que se usa actualmente pero mas automatizada, el sistema tendra un resndimiento optimo, en cuanto a la automatizacion de las formulas sera instantaneo dependiendo de la velocidad de internet una vez llenado los datos, la actualizacion de datos se hara un dia despues al llenado de datos para evitar errores, el formulario no tiene ninguna renstriccion de version, las reenstricciones de el formulario seran en las columnas en donde se encuentran formulas para automatizar los diferentes procesos de suma, multiplicaciones y etc. Estas columnas no se podran editar de ninguna manera, en caso de algun error o un dato desconocido el sistema automaticamente avisara que el dato no existe, el sistema podra actualizarse de manera sencilla en cualquier momento dependiendo de la actualizacion habra o no habra cambios en el manejo del sistema.

### 6.3 Requisitos de datos

Los datos que se migraran para este nuevo sistema seran unicamente los datos del 2026 llenados en la base de datos de el area de administracion de datos, todos los datos ingresados seran de texto o numericos, el registro sera entre la unidad de almacen y el area de administracion de datos, todos los campos estan registrados con su respectivo formato, al intentar poner algun formato que no es la celda se mostrara en rojo indicando un error.

### 6.4 Requisitos de integracion 

Los tres formularios se conectaran entre si a travez de la nube, mediante scripts para copiarlos y actualizarlos, la sincroniacion se hara una vez al dia entre las 11pm hasta las 2am de manera automatica, el formulario mas solido y que llegaria a servir como copia de seguridad llegaria a ser el formulario de la unidad de almacen.

### 6.5 Requisitos de calidad

La medicion de reduccion de errores de typeo sera de un 100% por que el sistema te obliga a escribir correctamente cada dato, para evitar los registros duplicados el area de gestion de datos se tiene que revisar los datos ingresados manualmente en todo caso de existir algun error se debe notificar inmediatamente a almacen, los datos ingresados al sistema deben ser igualmente revisados con los reportes fisicos que se tienen, para el uso del formulario no se necesita mucha capacitacion ya que es facil de entender

### 6.6 Requisitos de exclusion

El sistema bajo ningun concepto creara facturas, numeros de nota o informacion adicional nueva, unicamente sera para el registro de datos que ya se tiene en fisico.