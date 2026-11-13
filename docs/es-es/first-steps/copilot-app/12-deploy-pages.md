---
title: "Lección 12 - Publicar el sitio con GitHub Pages"
description: "Usa la aplicación GitHub Copilot para configurar un flujo de trabajo de Pages, revisar su pull request y comprobar que Space Quiz está disponible."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Dale a Space Quiz un hogar público publicándolo con GitHub Pages. Copilot puede preparar el flujo de trabajo y guiar la publicación, pero tú eres responsable de revisar los cambios y confirmar que el sitio está disponible.

En esta lección:

- pedirás a Copilot que configure la publicación en GitHub Pages.
- revisarás el flujo de trabajo y el pull request antes de fusionarlo.
- seguirás la publicación y comprobarás el sitio publicado.

## Escenario

Space Quiz ya está en un repositorio de GitHub, pero hace falta una forma sencilla de probarlo. Publicar el sitio de un solo archivo con GitHub Pages lo hace accesible mediante una URL pública sin añadir un servidor ni una dependencia del entorno de ejecución.

## Pide a Copilot que prepare la publicación

> [!WARNING]
> Crear un pull request puede confirmar cambios con Git y enviarlos al repositorio remoto. Revisa la configuración de aprobación y el repositorio de destino antes de enviar este prompt. Con **Approve all**, no esperes otro aviso de confirmación.

En la sesión de la aplicación Copilot para `space-quiz`, envía este prompt:

```plaintext
Prepare una publicación con GitHub Pages para este repositorio. Crea un flujo de trabajo de GitHub Actions que compile el sitio web si es necesario y lo publique en GitHub Pages cuando los cambios lleguen a la rama predeterminada. Añade un README que describa la aplicación y cómo ejecutarla localmente si aún no existe. Crea un pull request con estos cambios e indica su enlace y cualquier configuración o permiso de Pages necesario. No fusiones el pull request, no actives la fusión automática, no cambies la configuración de Pages ni publiques el sitio. Detente y espera a que lo revise.
```

## Revisa el flujo de trabajo y el pull request

1. Confirma que el README solo se añade si el repositorio aún no tiene uno.
2. Revisa los cambios del pull request, incluidos los pasos de compilación y publicación del flujo de trabajo, los desencadenadores y los permisos.
3. Confirma que el flujo de trabajo publica desde la rama predeterminada, no desde un pull request sin fusionar.
4. Solicita las correcciones necesarias y revisa el diff actualizado. Espera a que se superen las comprobaciones obligatorias del pull request antes de autorizar la fusión.

## Autoriza la fusión y la publicación

> [!WARNING]
> El siguiente prompt autoriza al agente a fusionar el pull request revisado, cambiar la configuración de Pages del repositorio y publicar el sitio. Envíalo solo después de terminar la revisión y confirmar el repositorio y el pull request. Según la configuración de aprobación, estas acciones podrían realizarse sin otro aviso.

Sustituye `<PR_NUMBER>` por el número del pull request que has revisado y envía este prompt por separado:

```plaintext
He revisado el pull request <PR_NUMBER> de este repositorio y autorizo su fusión y publicación. Activa GitHub Pages con GitHub Actions, fusiona solo ese pull request cuando se superen las comprobaciones obligatorias y supervisa la publicación hasta que termine correctamente. Indica la URL final del sitio web publicado. Si no tienes permiso para activar Pages o fusionar, dime exactamente qué debo aprobar o hacer; no confirmes que se ha completado hasta que el sitio esté disponible.
```

![Diagrama en tres etapas: un pull request de space-quiz fusionado; una ejecución correcta de GitHub Actions para publicar el sitio, con los pasos Build website, Upload artifact y Deploy to Pages; y Space Quiz disponible en yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Comprueba la publicación

1. Sigue la ejecución de publicación de GitHub Actions hasta que termine correctamente.
2. Abre la URL indicada y confirma que se carga Space Quiz.

Si el agente no puede activar Pages o fusionar el pull request, sigue las instrucciones específicas que te proporcione. No des la tarea por terminada hasta que la publicación se complete y el sitio esté disponible.

## Resumen y pasos siguientes

Space Quiz ya está disponible como sitio publicado y has comprobado la publicación en vez de confiar solo en el informe del agente. Continúa con la [lección 13: Repaso y próximos pasos][next-lesson].

[next-lesson]: ../13-review/
