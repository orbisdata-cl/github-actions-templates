# GitHub Actions Templates — Orbis Data

Templates de CI/CD para proyectos de la organización. Basados en el stack Node.js + Docker + SonarQube.

## Estructura

```
ci/          → Pipeline de Integración Continua (Pull Requests)
cd-dev/      → Pipeline de CD para ambiente de desarrollo (push a develop)
cd-prod/     → Pipeline de CD para producción (dispatch manual)
```

## Cómo usar

1. Copiar el archivo `.yml` del template que necesitás a `.github/workflows/` en tu proyecto.
2. Reemplazar todos los placeholders `{entre-llaves}` con los valores reales.
3. Configurar los secrets en GitHub Actions del repositorio.
4. Listo.

## Placeholders comunes

| Placeholder | Descripción |
|---|---|
| `{nombre-del-proyecto}` | Nombre del proyecto (aparece en notificaciones Discord) |
| `{dockerhub-username}` | Usuario o org de DockerHub |
| `{nombre-imagen}` | Nombre del repositorio en DockerHub |
| `{nombre-contenedor}` | Nombre del contenedor Docker en el servidor |
| `{nombre-red}` | Red Docker en el servidor (ej: `mi-app-network`) |
| `{puerto-externo}` | Puerto expuesto en el servidor |
| `{puerto-interno}` | Puerto interno del contenedor |

## Secrets requeridos

Ver la [documentación de CI/CD](https://app.notion.com/p/doc-testia/Definici-n-base-de-implementar-el-CI-CD-en-tu-proyectoyo-cr-3c7191cec7de8008b40aea7efec36424) en Notion para la lista completa.

## Node.js

Los templates usan `node-version: lts/*` para apuntar siempre al LTS activo, sin hardcodear una versión específica.
