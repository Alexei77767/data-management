# Comparativa: Supabase vs Firebase

## 1. Introducción

**Supabase** y **Firebase** son plataformas Backend as a Service (BaaS). Ambas proporcionan servicios que permiten desarrollar aplicaciones web y móviles sin tener que construir desde cero toda la infraestructura del backend.

La diferencia fundamental está en su filosofía:

* **Supabase** está construido alrededor de **PostgreSQL**, una base de datos relacional.
* **Firebase** pertenece a Google y ofrece principalmente **Cloud Firestore**, una base de datos NoSQL orientada a documentos, además de Realtime Database.

---

## 2. Comparación general

| Característica              | Supabase                                                     | Firebase                       |
| ---------------------------- | ------------------------------------------------------------ | ------------------------------ |
| Empresa                      | Supabase                                                     | Google                         |
| Tipo                         | BaaS                                                         | BaaS                           |
| Base principal               | PostgreSQL                                                   | Cloud Firestore                |
| Modelo de datos              | Relacional / SQL                                             | NoSQL / documentos             |
| Base de datos en tiempo real | Sí                                                          | Sí                            |
| Autenticación               | Sí                                                          | Sí                            |
| Almacenamiento de archivos   | Sí                                                          | Sí                            |
| Funciones de servidor        | Edge Functions                                               | Cloud Functions                |
| APIs                         | APIs automáticas                                            | SDKs y APIs                    |
| Hosting                      | Integración con servicios externos y opciones de plataforma | Firebase Hosting / App Hosting |
| Analítica                   | Integraciones                                                | Firebase Analytics             |
| Aplicaciones móviles        | Sí                                                          | Especialmente fuerte           |
| Consultas SQL                | Sí                                                          | No en Firestore                |
| Ecosistema Google            | No                                                           | Sí                            |
| Código abierto              | Componentes y plataforma self-hostable                       | No como plataforma completa    |
| Self-hosting                 | Sí                                                          | No                             |
| Modelo de precios            | Suscripción + uso                                           | Gratuito + pago por uso        |

---

# 3. Base de datos

### Supabase

Supabase utiliza **PostgreSQL** como base de datos.

Esto permite trabajar con:

* Tablas
* Relaciones entre tablas
* Claves primarias y foráneas
* JOIN
* SQL
* Vistas
* Funciones
* Triggers
* Transacciones
* Restricciones de integridad

Por ejemplo:

```text
CLIENTES
   │
   ├── CLIENTE_ID
   ├── NOMBRE
   └── DIRECCIÓN
          │
          ▼
       PEDIDOS
          │
          ├── PEDIDO_ID
          ├── CLIENTE_ID
          └── FECHA
```

Este enfoque resulta natural cuando los datos tienen **relaciones complejas**.

### Firebase

Firebase utiliza principalmente **Cloud Firestore**, que es una base de datos NoSQL basada en documentos y colecciones.

Conceptualmente:

```text
clientes/
   cliente_001
      nombre: "Juan"
      ciudad: "La Paz"

   cliente_002
      nombre: "Ana"
      ciudad: "Cochabamba"
```

No funciona como una base de datos relacional tradicional.

### Diferencia

**Supabase:**

> "Tengo datos relacionados y quiero trabajar con SQL."

**Firebase:**

> "Quiero almacenar documentos y acceder rápidamente a ellos desde una aplicación."

---

# 4. Autenticación

Ambas plataformas ofrecen sistemas de autenticación.

### Supabase Auth

Permite:

* Email y contraseña
* OAuth
* Proveedores sociales
* Magic links
* MFA
* Gestión de sesiones
* Control de usuarios

Además, Supabase integra la autenticación directamente con PostgreSQL y sus políticas de seguridad.

### Firebase Authentication

Permite:

* Email y contraseña
* Google
* Apple
* Facebook
* GitHub
* Teléfono
* Otros proveedores

Firebase también tiene una integración muy amplia con el ecosistema de Google.

**Conclusión:** ambos ofrecen una solución completa de autenticación; Firebase destaca especialmente por la variedad de servicios integrados en su ecosistema.

---

# 5. Almacenamiento

Ambos permiten almacenar archivos.

### Supabase Storage

Puede utilizarse para:

* Imágenes
* Videos
* PDFs
* Documentos
* Archivos de aplicaciones

Además, permite establecer políticas de acceso vinculadas al sistema de seguridad de PostgreSQL.

### Firebase Storage

Firebase utiliza **Cloud Storage for Firebase**, integrado con Google Cloud.

También permite almacenar archivos y controlar su acceso mediante reglas de seguridad.

---

# 6. Tiempo real

Ambos ofrecen funcionalidades de actualización en tiempo real.

### Supabase Realtime

Puede escuchar cambios realizados en PostgreSQL y transmitirlos a los clientes.

Por ejemplo:

```text
Base de datos
     ↓
Nuevo registro
     ↓
Supabase Realtime
     ↓
Aplicación
     ↓
Actualización inmediata
```

El plan gratuito de Supabase incluye actualmente 2 millones de mensajes Realtime y 200 conexiones simultáneas máximas.

### Firebase

Firebase tiene dos alternativas principales:

* Cloud Firestore con actualizaciones en tiempo real.
* Firebase Realtime Database.

Realtime Database está diseñada específicamente alrededor de sincronización de datos en tiempo real. El plan Blaze permite hasta 200.000 conexiones simultáneas por base de datos.

---

# 7. Funciones del servidor

Ambos permiten ejecutar código en el backend.

### Supabase

Utiliza **Edge Functions**.

Sirven para ejecutar código sin tener que administrar un servidor tradicional.

El plan gratuito incluye 500.000 invocaciones y Pro incluye 2 millones; posteriormente se cobra por uso adicional.

### Firebase

Utiliza **Cloud Functions**.

Las funciones pueden reaccionar a:

* Cambios en Firestore
* Autenticación
* Storage
* Solicitudes HTTP
* Eventos de otros servicios de Google

El plan Blaze incluye actualmente 2 millones de invocaciones gratuitas mensuales antes del cobro adicional.

---

# 8. APIs

Una de las características interesantes de Supabase es que su PostgreSQL puede exponerse mediante APIs generadas automáticamente.

Esto permite que una aplicación pueda hacer operaciones como:

```text
Aplicación
     ↓
API
     ↓
PostgreSQL
```

Firebase, por otro lado, suele trabajar principalmente mediante sus **SDK**, que permiten interactuar directamente con Firestore, Authentication, Storage, etc.

---

# 9. Seguridad

Ambos tienen sistemas de seguridad bastante completos.

### Supabase

Una característica importante es **Row Level Security (RLS)**.

Permite definir políticas como:

```text
Usuario A
   ↓
Puede ver sus registros

Usuario B
   ↓
Puede ver otros registros
```

Las reglas se pueden establecer directamente sobre las tablas de PostgreSQL.

### Firebase

Utiliza **Security Rules**, mediante las cuales se define quién puede leer o modificar determinados documentos o archivos.

Por ejemplo:

```text
Usuario autenticado
       ↓
Puede leer documentos

Usuario no autenticado
       ↓
Acceso denegado
```

---

# 10. Servicios adicionales

Aquí Firebase tiene un ecosistema particularmente amplio.

Firebase ofrece servicios como:

* Analytics
* Crashlytics
* App Check
* Cloud Messaging
* Remote Config
* A/B Testing
* App Distribution
* Test Lab
* Hosting
* Performance Monitoring

La documentación oficial de Firebase actualmente incluye estos servicios dentro de su plataforma.

Supabase, en cambio, concentra más su propuesta alrededor del backend:

* PostgreSQL
* Auth
* Storage
* Realtime
* Edge Functions
* APIs
* Seguridad
* Dashboard

---

# 11. Precios

Este es uno de los aspectos que más diferencia a ambas plataformas.

### Supabase

Actualmente ofrece:

| Plan       |        Precio |
| ---------- | ------------: |
| Free       |        $0/mes |
| Pro        | Desde $25/mes |
| Team       |      $599/mes |
| Enterprise | Personalizado |

El plan gratuito incluye 500 MB de base de datos, 1 GB de almacenamiento y 50.000 usuarios activos mensuales. El Pro incluye 8 GB de base de datos, 100 GB de almacenamiento y 250 GB de transferencia.

### Firebase

Firebase tiene:

**Spark**

```text
Gratis
```

y

**Blaze**

```text
Pago por uso
```

El plan Spark proporciona cuotas gratuitas para diferentes servicios. En Blaze se paga según el consumo. Por ejemplo, Firestore tiene actualmente cuotas gratuitas de 1 GiB de almacenamiento, 50.000 lecturas diarias y 20.000 escrituras diarias, antes de aplicar los cargos correspondientes.

Una diferencia importante es:

```text
SUPABASE
Plan + cuotas + consumo adicional
        ↓
Costos relativamente predecibles
```

mientras que:

```text
FIREBASE
Uso de los servicios
        ↓
Facturación según consumo
```

Por eso el costo final depende mucho de cómo esté diseñada y utilizada la aplicación.

---

# 12. Ventajas y desventajas

## Supabase

### Ventajas

* PostgreSQL completo.
* Utiliza SQL.
* Excelente para datos relacionales.
* APIs automáticas.
* Auth, Storage y Realtime integrados.
* RLS para seguridad.
* Puede utilizarse mediante self-hosting.
* Arquitectura basada en tecnologías ampliamente conocidas.

### Desventajas

* Algunas características avanzadas requieren planes superiores.
* La infraestructura puede requerir conocimientos de PostgreSQL cuando el proyecto crece.
* Su ecosistema de servicios adicionales es menor que el de Firebase.

---

## Firebase

### Ventajas

* Ecosistema muy amplio.
* Excelente integración con servicios de Google.
* Muy buena integración con Android.
* Herramientas de analítica, notificaciones, pruebas y monitoreo.
* Excelente soporte para aplicaciones en tiempo real.
* SDKs para diferentes plataformas.
* Escalabilidad administrada.

### Desventajas

* Firestore utiliza un modelo NoSQL.
* No ofrece las capacidades relacionales de PostgreSQL.
* Las consultas y el diseño de datos requieren pensar de forma diferente a SQL.
* El modelo de facturación basado en uso puede hacer que los costos dependan bastante del patrón de acceso.
* Existe mayor dependencia del ecosistema Firebase/Google.

---

# 13. Comparación resumida

| Aspecto                  | Supabase                   | Firebase                                          |
| ------------------------ | -------------------------- | ------------------------------------------------- |
| Base de datos relacional | **Sí**              | No                                                |
| SQL                      | **Sí**              | No en Firestore                                   |
| NoSQL                    | No como base principal     | **Sí**                                     |
| Relaciones entre datos   | **Excelente**        | Más limitado                                     |
| Tiempo real              | Sí                        | **Excelente**                               |
| Autenticación           | **Sí**              | **Sí**                                     |
| Storage                  | **Sí**              | **Sí**                                     |
| Serverless Functions     | **Sí**              | **Sí**                                     |
| APIs                     | **Excelente**        | Excelente mediante SDK/API                        |
| Analytics                | Básico/integrable         | **Muy completo**                            |
| Notificaciones push      | No es su enfoque principal | **Sí**                                     |
| Android                  | Bueno                      | **Excelente**                               |
| PostgreSQL               | **Sí**              | Mediante servicios adicionales, no como Firestore |
| SQL                      | **Sí**              | No                                                |
| Ecosistema               | Bueno                      | **Muy amplio**                              |
| Self-hosting             | **Sí**              | No                                                |
| Precio inicial           | Gratis                     | Gratis                                            |
| Modelo de pago           | Plan + consumo             | Principalmente consumo                            |

---

# 14. Conclusión para un informe

La diferencia fundamental entre ambas plataformas se encuentra en su **modelo de datos y enfoque de desarrollo**. Supabase utiliza PostgreSQL como núcleo, por lo que resulta especialmente adecuado para aplicaciones que requieren estructuras relacionales, consultas SQL, integridad de datos y relaciones entre múltiples entidades. Firebase utiliza principalmente Cloud Firestore, basado en un modelo NoSQL de documentos, y destaca por su amplio ecosistema de servicios orientados al desarrollo web y móvil. ([Firebase][1])

Por tanto, **no se puede afirmar que una plataforma sea universalmente superior a la otra**. La elección depende de los requisitos de la aplicación: Supabase resulta especialmente apropiado cuando el modelo relacional y SQL son importantes, mientras que Firebase resulta especialmente atractivo cuando se busca aprovechar un ecosistema amplio de servicios para aplicaciones web y móviles.

**En una frase para tu informe:**

> **Supabase prioriza un backend basado en PostgreSQL y tecnologías relacionales, mientras que Firebase ofrece un ecosistema más amplio de servicios para aplicaciones web y móviles, con Cloud Firestore como una de sus principales opciones de base de datos.**
