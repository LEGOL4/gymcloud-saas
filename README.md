# GymCloud — Sistema de Gestión en la Nube (SaaS)

Este proyecto es una plataforma SaaS simulada para la gestión digital de un gimnasio pequeño en Lima, Perú (50-150 socios, 4-7 empleados). Diseñado originalmente para operar 100% en papel, ahora migra a la nube implementando controles de seguridad alineados a la norma **ISO/IEC 27001:2022** y cumplimiento de la **Ley de Protección de Datos Personales de Perú (Ley N° 29733)**.

La aplicación consta de un solo archivo `index.html` (que integra HTML, CSS y JS) y está optimizada para ser desplegada en **Azure Static Web Apps**.

---

## 🛠️ Tecnologías Utilizadas

- **Frontend**: HTML5 Semántico, CSS3 Vanilla (con variables de diseño, flexbox, grid y animaciones en scroll) y JavaScript Vanilla (DOM, Intersection Observer).
- **Iconografía**: [Lucide Icons](https://lucide.dev/) (cargados mediante CDN).
- **Tipografía**: [Google Fonts (Inter)](https://fonts.google.com/specimen/Inter).
- **Hosting / Cloud**: Azure Static Web Apps.

---

## 🚀 Despliegue en Azure Static Web Apps (Paso a Paso)

Para desplegar este proyecto en Microsoft Azure utilizando GitHub, sigue estos pasos:

### Paso 1: Crear un Repositorio en GitHub
1. Inicia sesión en tu cuenta de [GitHub](https://github.com).
2. Crea un nuevo repositorio público o privado llamado `GymCloud`.
3. Sube los archivos del proyecto a la rama principal (usualmente `main` o `master`):
   - `index.html`
   - `staticwebapp.config.json`
   - `README.md`
   Puedes hacerlo a través de la terminal Git o subiendo los archivos directamente desde la interfaz web de GitHub.

### Paso 2: Crear el Recurso en Azure Portal
1. Inicia sesión en [Azure Portal](https://portal.azure.com).
2. En la barra de búsqueda superior, escribe **Static Web Apps** y selecciónalo.
3. Haz clic en **+ Crear** (o **+ Create**).
4. Configura los siguientes parámetros en la pestaña **Básicos (Basics)**:
   - **Suscripción**: Selecciona tu suscripción activa de Azure.
   - **Grupo de recursos**: Elige uno existente o crea uno nuevo (ej. `rg-gymcloud`).
   - **Nombre**: `gymcloud-saas`.
   - **Tipo de plan**: Selecciona **Gratuito (Free)** (ideal para proyectos universitarios y desarrollo).
   - **Región**: Selecciona la región más cercana a Perú (ej. `East US 2` o `West US 2`).

### Paso 3: Vincular con GitHub
1. En la sección **Detalles de la implementación (Deployment details)**, selecciona **GitHub** como origen del código.
2. Inicia sesión en tu cuenta de GitHub (si se te solicita) y autoriza a Azure.
3. Rellena los campos de tu repositorio:
   - **Organización**: Tu usuario de GitHub.
   - **Repositorio**: `GymCloud`.
   - **Rama**: `main` (o la rama donde subiste los archivos).

### Paso 4: Configurar los Detalles de Compilación (Build Details)
Azure detectará automáticamente el tipo de aplicación, pero asegúrate de rellenar la sección **Detalles de compilación (Build Details)** con los siguientes valores para una Web Estática de un solo archivo:
- **Preajustes de compilación (Build Presets)**: `Custom` (Personalizado).
- **Ubicación de la aplicación (App location)**: `/` (indica que el proyecto está en la raíz).
- **Ubicación de la API (Api location)**: Déjalo vacío (ya que no usamos Azure Functions backend para esta simulación).
- **Ubicación del artefacto (Output location)**: `/` o déjalo vacío (Azure leerá los archivos directamente desde la raíz del repositorio).

### Paso 5: Crear y Validar
1. Haz clic en **Revisar y crear (Review + create)** y luego en **Crear (Create)**.
2. Azure iniciará el aprovisionamiento de la Static Web App y configurará automáticamente un flujo de trabajo (workflow) de GitHub Actions en tu repositorio.
3. Una vez completado el recurso, ve al recurso en el portal y copia la **URL** generada (ej. `https://salmon-sea-0123456.azurestaticapps.net`).
4. Entra a tu repositorio en GitHub y haz clic en la pestaña **Actions** para ver el estado del despliegue. Una vez que el flujo termine en verde, tu sitio estará en línea.

---

## 🔒 Continuidad del Negocio e ISO 27001:2022

El sistema incluye una sección que documenta la gestión de riesgos para la continuidad de las operaciones del gimnasio:
- **R1: Adopción del SaaS** (Control ISO A.6.3: Concienciación y capacitación en seguridad).
- **R2: Pérdida de Datos en la Migración** (Control ISO A.8.13: Copias de seguridad).
- **R3: Interrupción de Proveedor Cloud** (Control ISO A.5.23: Seguridad en la nube).
- **R4: Fuga de Datos** (Control ISO A.8.5: Prevención de fuga de información).
- **R5: Dependencia del Proveedor** (Control ISO A.5.23: Portabilidad e interoperabilidad).

El mapa de calor 5x5 integrado permite a los administradores visualizar de manera interactiva la criticidad de los riesgos identificados, ofreciendo un panel de control idóneo para la toma de decisiones tecnológicas.
