# Pokédex Angular — Sistemas Distribuidos

Aplicación web desarrollada en Angular que consume la API pública de Pokémon usando PokéAPI.  
El proyecto fue desplegado en Azure Static Web Apps utilizando integración continua con GitHub y GitHub Actions.

---

# Información del Proyecto

- **Estudiante:** Keiner Jose Salcedo Ayola
- **Programa:** Ingeniería de Sistemas
- **Materia:** Sistemas Distribuidos
- **Proyecto:** Pokédex Angular

---

# Repositorio GitHub

https://github.com/keinersalcedo02/PokeDex

# Aplicación Desplegada

https://polite-coast-051954f0f.7.azurestaticapps.net

---

# Objetivo del Proyecto

El objetivo de este proyecto fue desarrollar una aplicación web SPA (Single Page Application) utilizando Angular y desplegarla en la nube mediante Azure Static Web Apps.

Además del funcionamiento de la aplicación, se trabajó en:

- Configuración de seguridad HTTP
- Integración continua con GitHub Actions
- Despliegue automatizado
- Configuración correcta de rutas SPA
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

# Funcionalidades de la Aplicación

- Visualización de Pokémon
- Filtros dinámicos
- Búsqueda en tiempo real
- Navegación SPA
- Consumo de API REST
- Diseño responsive

---

# Evidencia del Repositorio

La siguiente imagen muestra el repositorio principal del proyecto en GitHub.

![Repositorio GitHub](docs/github-repository.png)

---

# Historial de Versiones y Commits

El proyecto cuenta con múltiples commits realizados durante el desarrollo, demostrando el progreso y evolución de la aplicación.

Entre los cambios realizados se encuentran:

- Configuración del pipeline
- Corrección de rutas SPA
- Configuración de seguridad
- Optimización de estilos
- Actualización del README

![Historial de Commits](docs/github-commits.png)

---

# Desarrollo del Proyecto

## Componentes Desarrollados

- Barra de navegación
- Barra lateral de filtros
- Tarjetas de Pokémon
- Buscador dinámico
- Sistema de ordenamiento

---

# Despliegue en Azure Static Web Apps

## Creación del Recurso

La aplicación fue desplegada utilizando Azure Static Web Apps con integración directa a GitHub.

Se configuró:

- Repositorio GitHub
- Rama principal
- Pipeline CI/CD
- Variables de compilación
- Ruta del proyecto Angular

---

# Evidencia de Azure Static Web Apps

![Azure Static Web Apps](docs/azure-static-web-apps.png)

---

# Configuración del flujo de trabajo de GitHub Actions

Azure generó automáticamente un flujo de trabajo para el despliegue continuo de la aplicación.

Inicialmente el despliegue fallaba porque Azure buscaba el proyecto en la raíz del repositorio.

## Ruta Correcta del Proyecto

```bash
sistemas-distribuidos/poke-dex-lab/source/pokedex-angular
