## ¿Qué es Supabase?

Supabase es una **plataforma de backend como servicio (BaaS)**. Su objetivo es proporcionar las herramientas que una aplicación necesita para almacenar y gestionar datos, autenticar usuarios, ejecutar lógica del servidor y comunicarse con el frontend.

Su componente principal es **PostgreSQL**, una base de datos relacional de código abierto. Encima de ella, Supabase proporciona servicios adicionales. ([Supabase][1])

### ¿Para qué sirve?

Principalmente para desarrollar aplicaciones sin tener que configurar y mantener desde cero todo el backend.

Entre sus servicios están:

* **Base de datos PostgreSQL** → almacenar y consultar información.
* **Authentication** → registro, inicio de sesión y gestión de usuarios.
* **Storage** → almacenar imágenes, documentos y otros archivos.
* **Realtime** → recibir actualizaciones de datos en tiempo real.
* **Edge Functions** → ejecutar código en el servidor.
* **APIs** → acceder a los datos desde aplicaciones web o móviles.
* **Seguridad y permisos** → controlar qué usuarios pueden acceder a determinados datos.
* **Dashboard** → administrar el proyecto y sus recursos.

---

## Planes de Supabase

Actualmente tiene **4 planes principales**: Free, Pro, Team y Enterprise. ([Supabase][1])

| Plan              |       Precio base | Orientado a                                                    |
| ----------------- | ----------------: | -------------------------------------------------------------- |
| 🆓 **Free**       |        **$0/mes** | Aprender, experimentar y proyectos pequeños                    |
| 💼 **Pro**        |       **$25/mes** | Aplicaciones en producción                                     |
| 🏢 **Team**       |      **$599/mes** | Equipos y organizaciones que necesitan controles empresariales |
| 🌐 **Enterprise** | **Personalizado** | Aplicaciones y organizaciones a gran escala                    |

### 🆓 Free

Es el plan gratuito.

Incluye, entre otras cosas:

* 500 MB de base de datos por proyecto
* 1 GB de almacenamiento
* 50.000 usuarios activos mensuales
* 5 GB de transferencia de datos
* 500.000 invocaciones de Edge Functions
* 2 millones de mensajes Realtime
* Hasta **2 proyectos activos gratuitos**
* Soporte mediante la comunidad

Los proyectos gratuitos pueden pausarse después de una semana de inactividad. ([Supabase][1])

### 💼 Pro — $25/mes

Está pensado para aplicaciones que ya están en producción.

Incluye:

* 8 GB de disco por proyecto
* 100.000 usuarios activos mensuales incluidos
* 100 GB de almacenamiento
* 250 GB de transferencia
* 2 millones de invocaciones de Edge Functions
* 5 millones de mensajes Realtime
* Copias de seguridad diarias durante 7 días
* Soporte por email

Además, algunos recursos pueden generar cargos adicionales si superas las cuotas incluidas. ([Supabase][1])

### 🏢 Team — $599/mes

Está dirigido a organizaciones que necesitan mayores controles administrativos y de seguridad.

Añade características como:

* **SSO**
* Roles y permisos más avanzados
* SOC 2
* ISO 27001
* AWS PrivateLink
* Backups durante 14 días
* Retención de logs durante 28 días
* Soporte prioritario y SLA

HIPAA está disponible como complemento de pago. ([Supabase][1])

### 🌐 Enterprise — precio personalizado

Es para organizaciones con necesidades empresariales grandes o específicas.

Incluye características como:

* Soporte 24/7/365
* Responsable de soporte dedicado
* SLA de disponibilidad
* Configuraciones personalizadas
* Soporte para AWS PrivateLink
* Seguridad y cumplimiento personalizados

El precio se negocia directamente con Supabase. ([Supabase][1])

### En resumen

Puedes verlo así:

```text
SUPABASE
│
├── Base de datos
├── Usuarios / Authentication
├── Archivos / Storage
├── Tiempo real / Realtime
├── Funciones / Edge Functions
├── APIs
└── Seguridad
        │
        ▼
    TU APLICACIÓN
```
