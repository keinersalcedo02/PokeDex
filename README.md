# Pokédex Angular — Sistemas Distribuidos

Aplicación web desarrollada en Angular que permite consultar información de Pokémon consumiendo datos desde PokéAPI.

El proyecto fue desplegado en Azure Static Web Apps utilizando integración continua con GitHub y GitHub Actions.

---

# URL Pública

https://TU-URL-AQUI.azurestaticapps.net

---

# Repositorio GitHub

https://github.com/keinersalcedo02/PokeDex

---

# Objetivo del Proyecto

El propósito de esta aplicación es implementar una Pokédex web moderna utilizando Angular, aplicando conceptos de:

- Sistemas distribuidos
- Consumo de APIs REST
- Despliegue en la nube
- Seguridad web
- Integración y despliegue continuo

---

# Funcionalidades Implementadas

La aplicación cuenta con las siguientes funcionalidades:

- Visualización dinámica de Pokémon
- Búsqueda en tiempo real
- Filtros interactivos
- Navegación SPA
- Diseño responsive
- Consumo de PokéAPI
- Despliegue automático con GitHub Actions

---

# Tecnologías Utilizadas

- Angular
- TypeScript
- HTML5
- CSS3
- Azure Static Web Apps
- GitHub Actions
- PokéAPI
- GitHub

---

# Evidencia del Repositorio

La siguiente captura muestra el repositorio principal utilizado para el desarrollo del proyecto.

![Repositorio GitHub](./sistemas-distribuidos/poke-dex-lab/source/pokedex-angular/docs/github-repository.png)

---

# Historial de Versiones y Commits

Durante el desarrollo se realizaron múltiples commits para evidenciar el progreso del proyecto y la implementación gradual de funcionalidades.

Entre los cambios más importantes se encuentran:

- Configuración inicial del proyecto Angular
- Implementación de componentes
- Integración con PokéAPI
- Configuración de Azure Static Web Apps
- Corrección de rutas SPA
- Implementación de headers de seguridad
- Ajustes visuales y optimización

![Historial de Commits](./sistemas-distribuidos/poke-dex-lab/source/pokedex-angular/docs/github-commits.png)

---

# Desarrollo de la Aplicación

## Componentes Desarrollados

La estructura de la aplicación se organizó utilizando componentes reutilizables:

- Navbar principal
- Sidebar de filtros
- Tarjetas de Pokémon
- Buscador dinámico
- Sistema de ordenamiento
- Vista responsive

---

# Despliegue en Azure Static Web Apps

La aplicación fue desplegada utilizando Azure Static Web Apps conectado directamente al repositorio de GitHub.

Durante la configuración se establecieron:

- Rama principal
- Pipeline CI/CD
- Ruta del proyecto Angular
- Configuración de compilación
- Variables necesarias para el despliegue

---

# Evidencia de Azure Static Web Apps

La siguiente imagen muestra la configuración y despliegue de la aplicación en Azure.

![Azure Static Web Apps](./sistemas-distribuidos/poke-dex-lab/source/pokedex-angular/docs/azure-static-web-apps.png)

---

# Configuración de GitHub Actions

Azure generó automáticamente el flujo de trabajo para realizar despliegues automáticos cada vez que se realiza un push al repositorio.

Inicialmente se presentaron errores porque Azure intentaba compilar desde la raíz del repositorio.

El problema fue solucionado configurando correctamente la ruta:

```yaml
app_location: "sistemas-distribuidos/poke-dex-lab/source/pokedex-angular"
