# Pokédex Angular — Sistemas Distribuidos

Aplicación web desarrollada en Angular que consume datos de Pokémon usando PokéAPI.

El proyecto fue desplegado en Azure Static Web Apps con integración continua usando GitHub y GitHub Actions.

---

# Información del Proyecto

- Framework: Angular
- Lenguaje: TypeScript
- API consumida: PokéAPI
- Despliegue: Azure Static Web Apps
- Control de versiones: GitHub
- CI/CD: GitHub Actions

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

![Repositorio GitHub](sistemas-distribuidos/poke-dex-lab/source/pokedex-angular/docs/repositorio-github.png)

---

# Historial de Versiones y Commits

El proyecto cuenta con múltiples commits realizados durante el desarrollo.

Entre los cambios realizados se encuentran:

- Configuración del pipeline
- Corrección de rutas SPA
- Configuración de seguridad
- Optimización de estilos
- Actualización del README

![Historial de Commits](sistemas-distribuidos/poke-dex-lab/source/pokedex-angular/docs/github-commits.png)

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

![Aplicaciones web estáticas de Azure](sistemas-distribuidos/poke-dex-lab/source/pokedex-angular/docs/aplicaciones%20web%20estáticas%20de%20Azure.png)

---

# Configuración del flujo de trabajo de GitHub Actions

Azure generó automáticamente un flujo de trabajo para el despliegue continuo de la aplicación.

Inicialmente el despliegue fallaba porque Azure buscaba el proyecto en la raíz del repositorio.

Se corrigió configurando correctamente la ruta:

```yaml
app_location: "sistemas-distribuidos/poke-dex-lab/source/pokedex-angular"
