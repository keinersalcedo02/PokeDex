Pokédex - Proyecto Angular
Descripción

Este proyecto es una Pokédex desarrollada con Angular que consume la API pública PokéAPI. Permite visualizar, filtrar y explorar diferentes Pokémon.

El objetivo fue desarrollar la aplicación y desplegarla en la nube usando Azure Static Web Apps con integración a GitHub.

Creación de cuenta en GitHub

Se ingresó a https://github.com

Se hizo clic en Sign up
Se completaron los datos:

Correo electrónico
Contraseña segura
Nombre de usuario

Se verificó el correo electrónico
Se inició sesión

Seguridad de la cuenta

Para proteger la cuenta se aplicaron:

Contraseña segura (uso de mayúsculas, números y símbolos)
Verificación de correo electrónico
Uso de conexión segura HTTPS
No compartir credenciales
Creación del repositorio

Se creó un repositorio llamado pokedex
Se configuró como público
Se subió el proyecto usando Git

Comandos utilizados:
git init
git add .
git commit -m "Primer commit del proyecto pokedex"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/pokedex.git
git push -u origin main
Desarrollo del proyecto
Tecnologías utilizadas:
Angular
TypeScript
HTML
SCSS
PokéAPI
Componentes desarrollados:
Barra de estado
Sidebar de filtros
Lista de Pokémon
Despliegue en Azure Static Web Apps
Creación de cuenta en Azure

Se ingresó a https://portal.azure.com

Se creó una cuenta o se inició sesión con cuenta Microsoft
Se verificó la identidad
Se accedió al portal

Creación del recurso

Se buscó Static Web Apps
Se creó un nuevo recurso
Se configuró:

Nombre del proyecto
Región
Origen: GitHub

Se conectó con el repositorio pokedex

Configuración del pipeline (GitHub Actions)

Azure generó automáticamente un workflow, el cual fue modificado porque inicialmente no encontraba el proyecto.

Problema

El despliegue fallaba porque Azure buscaba el proyecto en la raíz del repositorio, pero el proyecto estaba dentro de una carpeta interna.

Ruta real del proyecto:

sistemas-distribuidos/poke-dex-lab/source/pokedex-angular

Solución

Se modificó el archivo del workflow para indicar correctamente la ubicación del proyecto:

app_location: "sistemas-distribuidos/poke-dex-lab/source/pokedex-angular"
output_location: "dist/pokedex-angular"

Con esto Azure pudo encontrar el proyecto y desplegarlo correctamente.

Configuración de Angular (environment)

Se utilizó el archivo de producción donde:

Se configuraron las URLs de la API
Se definieron rutas de imágenes
Se ajustaron configuraciones generales

Esto permitió que la aplicación funcionara correctamente en producción.

Problema de rutas (Error 404)
Descripción

Al desplegar, la aplicación cargaba correctamente, pero al recargar la página o navegar entre rutas aparecía un error 404.

Causa

Angular es una SPA (Single Page Application) y Azure no maneja rutas internas automáticamente.

Solución

Se creó el archivo:

staticwebapp.config.json

Con la siguiente configuración:

navigationFallback → redirige todas las rutas a index.html
responseOverrides → maneja errores 404

Esto permitió que Angular controle correctamente la navegación.

Configuración de seguridad

Se añadieron encabezados de seguridad en la aplicación:

Content Security Policy (CSP)
Strict Transport Security (HSTS)
X-Frame-Options
X-Content-Type-Options
Referrer Policy
Permissions Policy

Esto protege la aplicación contra:

Ataques XSS
Carga de contenido externo no autorizado
Clickjacking
Accesos inseguros
Otros problemas encontrados
Layout roto

El buscador se movía al cargar los datos

Causa: uso incorrecto de grid
Solución: definir columnas fijas y estructura estable

Estilos inconsistentes

La interfaz cambiaba después de cargar

Causa: múltiples temas activos
Solución: dejar un solo tema activo

Resultado final
Aplicación funcionando correctamente
Despliegue exitoso en Azure
Rutas funcionando sin errores
Seguridad correctamente configurada
Pipeline automatizado con GitHub Actions
Enlace del proyecto

https://polite-coast-051954f0f.7.azurestaticapps.net

Autor

Keiner Jose Salcedo Ayola
Ingeniería de Sistemas
Sistemas Distribuidos
