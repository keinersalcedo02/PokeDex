# Pokédex Angular

Aplicación web desarrollada en Angular que consume la API pública de Pokémon utilizando PokéAPI.  
El proyecto fue desplegado en Azure Static Web Apps utilizando integración continua con GitHub y GitHub Actions.

---

# Información del Proyecto

| Información | Detalle |
|---|---|
| Estudiante | Keiner Jose Salcedo Ayola |
| Programa | Ingeniería de Sistemas |
| Materia | Sistemas Distribuidos |
| Proyecto | Pokédex Angular |

## Repositorio GitHub

https://github.com/keinersalcedo02/PokeDex

## Aplicación Desplegada

https://polite-coast-051954f0f.7.azurestaticapps.net

---

# Objetivo del Proyecto

El objetivo de este proyecto fue desarrollar una aplicación SPA (Single Page Application) utilizando Angular y desplegarla en Azure Static Web Apps.

Además del funcionamiento de la aplicación, se implementaron configuraciones relacionadas con:

- Seguridad HTTP
- Integración continua
- Despliegue automatizado
- Configuración de rutas SPA
- Buenas prácticas de desarrollo

---

# Tecnologías Utilizadas

- Angular
- TypeScript
- HTML5
- SCSS
- Git
- GitHub
- Azure Static Web Apps
- GitHub Actions
- PokéAPI

---

# Funcionalidades Principales

- Visualización de Pokémon
- Búsqueda dinámica
- Filtros
- Navegación SPA
- Consumo de API REST
- Diseño responsive

---

# Evidencia del Repositorio

La siguiente imagen muestra el repositorio principal del proyecto en GitHub.

<p align="center">
  <img src="docs/github-repository.png" width="100%">
</p>

---

# Historial de Versiones y Commits

El proyecto cuenta con múltiples commits realizados durante el desarrollo, evidenciando el progreso y evolución de la aplicación.

Algunos cambios importantes realizados fueron:

- Configuración del pipeline
- Corrección de rutas SPA
- Implementación de headers de seguridad
- Optimización de estilos
- Actualización del README

<p align="center">
  <img src="docs/github-commits.png" width="100%">
</p>

---

# Desarrollo del Proyecto

## Componentes Desarrollados

- Navbar
- Sidebar de filtros
- Tarjetas de Pokémon
- Buscador dinámico
- Sistema de ordenamiento

---

# Despliegue en Azure Static Web Apps

La aplicación fue desplegada utilizando Azure Static Web Apps con integración directa a GitHub.

## Configuración Realizada

- Repositorio GitHub
- Rama principal
- Pipeline CI/CD
- Variables de compilación
- Ruta del proyecto Angular

---

# Evidencia de Azure

La siguiente imagen muestra el recurso configurado en Azure Static Web Apps.

<p align="center">
  <img src="docs/azure-static-web-apps.png" width="100%">
</p>

---

# Configuración del Workflow GitHub Actions

Azure generó automáticamente un workflow para el despliegue continuo de la aplicación.

Inicialmente el despliegue fallaba porque Azure buscaba el proyecto en la raíz del repositorio.

## Ruta Correcta del Proyecto

```bash
sistemas-distribuidos/poke-dex-lab/source/pokedex-angular
```

## Solución Aplicada

Se modificó el archivo YAML del workflow con la ruta correcta:

```yaml
app_location: "sistemas-distribuidos/poke-dex-lab/source/pokedex-angular"
output_location: "dist/pokedex-angular"
```

Gracias a esta configuración Azure logró compilar y desplegar correctamente la aplicación.

---

# Evidencia del Workflow

<p align="center">
  <img src="docs/github-actions-workflow.png" width="100%">
</p>

---

# Problema de Rutas — Error 404

## Descripción

La aplicación cargaba correctamente, pero al actualizar la página o navegar manualmente aparecía un error 404.

## Causa

Angular funciona como una SPA y Azure no maneja automáticamente las rutas internas.

## Solución

Se creó el archivo:

```bash
staticwebapp.config.json
```

Con la siguiente configuración:

```json
{
  "navigationFallback": {
    "rewrite": "index.html"
  },
  "responseOverrides": {
    "404": {
      "rewrite": "/404.html"
    }
  }
}
```

Esto permitió que Angular manejara correctamente la navegación sin errores.

---

# Configuración de Seguridad

Para mejorar la seguridad de la aplicación se configuraron diferentes headers HTTP dentro del archivo `staticwebapp.config.json`.

## Configuración Implementada

```json
{
  "navigationFallback": {
    "rewrite": "index.html"
  },
  "responseOverrides": {
    "404": {
      "rewrite": "/404.html"
    }
  },
  "globalHeaders": {
    "Content-Security-Policy": "default-src 'self'; img-src 'self' data: https: https://raw.githubusercontent.com; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src 'self' data: https://fonts.gstatic.com; connect-src 'self' https://pokeapi.co https://*.pokeapi.co; object-src 'none'; base-uri 'self'; frame-ancestors 'none'; form-action 'self'; upgrade-insecure-requests",

    "Strict-Transport-Security": "max-age=63072000; includeSubDomains; preload",

    "X-Content-Type-Options": "nosniff",

    "X-Frame-Options": "DENY",

    "Referrer-Policy": "strict-origin-when-cross-origin",

    "Permissions-Policy": "geolocation=(), microphone=(), camera=(), payment=(), usb=()",

    "X-Permitted-Cross-Domain-Policies": "none",

    "X-XSS-Protection": "1; mode=block"
  }
}
```

---

# Explicación de los Headers Configurados

## Content-Security-Policy (CSP)

Permite controlar qué recursos puede cargar la aplicación y ayuda a prevenir ataques XSS.

## Strict-Transport-Security (HSTS)

Obliga al navegador a utilizar únicamente conexiones HTTPS seguras.

## X-Frame-Options

Evita ataques Clickjacking bloqueando iframes externos.

## X-Content-Type-Options

Previene MIME Sniffing.

## Referrer-Policy

Controla la información enviada entre sitios.

## Permissions-Policy

Deshabilita permisos sensibles del navegador como:

- Cámara
- Micrófono
- Geolocalización
- USB
- Pagos

---

# Validación de Seguridad

La aplicación fue analizada usando SecurityHeaders para validar la implementación correcta de los headers HTTP.

## Resultado del Escaneo

<p align="center">
  <img src="docs/securityheaders-azure.png" width="100%">
</p>

La aplicación obtuvo una calificación alta gracias a la configuración de seguridad implementada.

---

# Aplicación Funcionando

La siguiente imagen muestra la Pokédex funcionando correctamente en producción.

<p align="center">
  <img src="docs/app-running.png" width="100%">
</p>

---

# Problemas Encontrados Durante el Desarrollo

## Layout roto

### Problema

El buscador cambiaba de posición al cargar los datos.

### Causa

Configuración incorrecta de CSS Grid.

### Solución

Se definieron columnas fijas y una estructura estable.

---

## Estilos inconsistentes

### Problema

La interfaz cambiaba después de cargar.

### Causa

Múltiples temas activos simultáneamente.

### Solución

Mantener un único tema global activo.

---

# Resultado Final

✅ Aplicación desplegada correctamente  
✅ Pipeline automatizado con GitHub Actions  
✅ Navegación SPA funcionando correctamente  
✅ Seguridad HTTP configurada  
✅ Aplicación accesible públicamente  
✅ Integración continua funcionando correctamente

---

# Organización de las Imágenes

Las imágenes utilizadas en este README se encuentran almacenadas dentro de la carpeta:

```bash
docs/
```

---

# Autor

Keiner Jose Salcedo Ayola  
Ingeniería de Sistemas  
Sistemas Distribuidos
