# GESTIÓN DE DATOS - PRD

## 1. Resumen

El área de Gestión de Datos es responsable de consolidar toda la información generada por las diferentes áreas de la empresa para elaborar reportes generales dirigidos a la Gerencia. Actualmente, este proceso se realiza mediante hojas de Excel que requieren una gran cantidad de ingreso manual de información y el uso de numerosas fórmulas.

---

## 2. Objetivos

### 2.1 Objetivo General

Desarrollar un nuevo sistema basado en Excel que reemplace el formulario actual de "Ventas de Producción", simplificando el ingreso de datos, reduciendo errores y mejorando el rendimiento general del proceso de elaboración de reportes.

### 2.2 Objetivos Específicos

* Crear un formulario principal para el área de Gestión de Datos que reemplace al sistema utilizado actualmente.
* Crear un formulario independiente para el área de Almacén que permita registrar las salidas de productos de forma sencilla y estandarizada.
* Integrar ambos formularios para que la información registrada en Almacén se transfiera automáticamente al formulario principal de Gestión de Datos.
* Implementar un sistema de reportes que permita generar información consolidada de manera más rápida y eficiente.

---

## 3. Alcance y Límites

### 3.1 Alcance

Se desarrollará un sistema compuesto por dos formularios:

1. Un formulario para el registro de salidas de productos en la unidad de Almacén.
2. Un formulario principal para el área de Gestión de Datos.

Ambos formularios estarán conectados entre sí para que la información registrada en Almacén se incorpore automáticamente al sistema de Gestión de Datos, facilitando la generación de reportes de ventas de fábrica.

### 3.2 Límites

* No se migrarán los datos históricos registrados en el sistema actual.
* El formato general de ingreso de datos se mantendrá similar al utilizado actualmente para facilitar la adaptación de los usuarios.
* El sistema estará enfocado únicamente en el registro y procesamiento de las ventas registradas por el área de Almacén.
* Se continuará utilizando formularios como plataforma principal de trabajo.
* Algunas operaciones seguirán dependiendo de fórmulas internas del sistema.

---

## 4. Contexto y Antecedentes

### 4.1 Contexto Actual

El área de Gestión de Datos tiene la responsabilidad de recopilar, organizar, filtrar y consolidar la información de ventas para generar reportes dirigidos a la Gerencia.

Actualmente, la información proviene del área de Almacén. Antes de llegar a Gestión de Datos, los registros son revisados y aprobados por el Supervisor de Almacén y posteriormente por el Jefe de Producción.

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
* **N.º de Nota:** Identificador de la salida registrada.
* **Cliente:** Persona o empresa que recibe el producto.
* **Título:** Descripción y especificaciones del producto vendido.
* **Bolsas:** Cantidad de bolsas despachadas.
* **Sueltos:** Cantidad de piezas vendido fuera de bolsa.
* **Cantidad Total:** Peso total del producto vendido.
* **Observaciones:** Comentarios o información adicional sobre la venta.
* **Color:** Color y código correspondiente del producto.

Posteriormente, esta información es transcrita manualmente al sistema utilizado por Gestión de Datos.

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
    └── Global
```

**Descripción de los campos adicionales:**

* **Kilos Totales:** Peso total vendido.
* **Precio Unitario:** Precio por kilogramo del producto.
* **Precio Total:** Resultado de multiplicar los kilos totales por el precio unitario.
* **Global:** Acumulado de ventas correspondiente al período de análisis.

Actualmente, gran parte de los reportes se generan mediante fórmulas y selección manual de datos, lo que incrementa el tiempo de trabajo y la posibilidad de errores.

### 4.2 Antecedentes

El sistema actual ha sido utilizado durante varios años con pocas modificaciones significativas. No se dispone de información detallada sobre versiones anteriores ni sobre procedimientos previos al sistema actualmente implementado.

### 4.3 Actores y Responsabilidades

| Actor                 | Depende de         | Responsabilidad                                                        |
| --------------------- | ------------------ | ---------------------------------------------------------------------- |
| Gerente               | -                  | Recibir y revisar los reportes generales de la empresa.                |
| Gestión de Datos      | Gerente            | Consolidar la información y elaborar reportes generales.               |
| Jefe de Producción    | Gerente            | Revisar y aprobar la información proveniente de Almacén.               |
| Supervisor de Almacén | Jefe de Producción | Registrar y verificar las salidas de productos antes de su aprobación. |

---

## 5. Problemas Identificados

* Errores de digitación durante el ingreso manual de información.
* Eliminación accidental de fórmulas al modificar celdas incorrectas.
* Generación de reportes mediante selección manual de datos, lo que incrementa el tiempo de trabajo.
* Inconsistencias en la información registrada por diferentes usuarios.
* Omisión de datos o errores de cálculo que pueden pasar desapercibidos durante las revisiones.
* Proceso de validación lento debido a la necesidad de revisar múltiples hojas y registros.
* Existencia de formularios obsoletos que ya no son utilizados.
* Creación manual de nuevas hojas y formularios para suplir limitaciones del sistema actual.
* Dificultad para mantener la integridad y consistencia de la información a medida que aumenta el volumen de datos.

---

## 6. Requisitos

(Pendiente de definición)
