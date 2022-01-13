---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Obtenga información sobre los registros de depuración, medios y escritorio producidos por Microsoft Teams, dónde se pueden encontrar y cómo pueden ayudar con la supervisión y solución de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a8a58511c3a9562281f162ef1c92d8e01d96228
ms.sourcegitcommit: 45756a51857ed1d8714175d2b715c388e2f0db81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62027593"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Use archivos de registro para supervisar y solucionar problemas Microsoft Teams

Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar a supervisar y solucionar problemas Teams:

-   [Registros de depuración](#debug-logs)

-   [Registros multimedia](#media-logs)

-   [Registros de escritorio](#desktop-logs)

En este artículo se describen estos registros y cómo se usan. Para obtener información sobre cómo solucionar problemas específicos, [vea: Teams solución de problemas.](/MicrosoftTeams/troubleshoot/teams) Para obtener información sobre cómo ponerse en contacto con el soporte técnico, vea [Obtener soporte técnico.](/microsoft-365/business-video/get-help-support) Al crear una solicitud de soporte técnico con soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft empezar rápidamente a solucionar el problema. **Los registros** multimedia **o de** escritorio solo son necesarios si Microsoft lo solicita.

> [!NOTE]
> En este artículo, el término **Registros de depuración** hace referencia a los registros que se usan para la solución de problemas. Sin embargo, los archivos que se generan para estos registros contendrán el término registros **de diagnóstico** en sus nombres.  

## <a name="collect-and-enable-logging"></a>Recopilar y habilitar el registro

Es importante recopilar registros tan pronto como se produzca un problema. Los registros se pueden recopilar juntos con solo un par de clics.

- Windows: Haga clic con el botón derecho en el icono Teams en la bandeja del sistema y elija **Recopilar archivos de soporte técnico.** 

- Mac: seleccione el menú Ayuda y elija **Recopilar archivos de soporte técnico.**

Los registros de depuración, escritorio y medios se recopilarán en una carpeta con el nombre Registro de diagnóstico _de MSTeams. \<local date and time\>_ Esta carpeta se puede comprimir y compartir al abrir una solicitud de soporte técnico con el soporte técnico de Microsoft. La carpeta contendrá carpetas para escritorio, reunión (multimedia) y depuración (web). Puede recopilar los archivos con los siguientes métodos abreviados de teclado:

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>

- Mac: <kbd>Comando de</kbd> + <kbd>opción</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>


El registro multimedia está desactivado de forma predeterminada. Para habilitar el registro multimedia, los usuarios deben activar la opción en Teams cliente. Vaya a **Configuración** General y seleccione Habilitar registro para diagnósticos de reuniones  >   **(requiere reiniciar Teams).** El Teams debe reiniciarse para iniciar el registro (reinicie haciendo clic con el botón derecho en el icono del dock (Mac) o la barra de tareas (Windows) y seleccionando **Salir.** Después de salir, simplemente haga clic en el icono de la aplicación para abrirlo de nuevo).

Si se produce un problema con una reunión específica o un evento en directo, es útil tener la dirección URL asociada a la reunión. Esto proporciona información adicional para ayudar a identificar la reunión exacta o el evento en directo en los registros. Esta información se puede recopilar de cualquier participante para una reunión o del moderador o productor de un evento en directo. Esta dirección URL se puede capturar si mantiene el puntero sobre la dirección URL de combinación y elige **Copiar hipervínculo.**

> [!NOTE]
> Si el registro multimedia está habilitado, habrá archivos adicionales incluidos en la carpeta Reunión que son necesarios para investigar problemas de audio y vídeo. Si el registro multimedia no está habilitado, habrá un número limitado de registros disponibles.
  
> [!NOTE]
> Los registros de depuración se recopilaban previamente con los métodos abreviados de teclado siguientes. Estos siguen funcionando y completarán la misma captura de registro que la **opción Recopilar archivos de** soporte técnico.
>
> - Windows: <kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>
>
> - Mac: <kbd>Comando de</kbd> + <kbd>opción</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>


En la tabla siguiente se describen los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y del sistema operativo.


|Cliente |Depuración|Escritorio|Medios|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).

## <a name="debug-logs"></a>Registros de depuración

Consulte la _sección Recopilar y habilitar el registro_ para obtener Windows y Mac. Los registros de depuración son producidos por Windows y mac clientes de escritorio, así como por clientes basados en explorador. Los registros están basados en texto y se leen desde abajo hacia arriba. Se pueden leer con cualquier editor basado en texto y se crean nuevos registros al iniciar sesión en el cliente.

Los registros de depuración muestran los siguientes flujos de datos:

-   Inicio de sesión

-   Solicitudes de conexión a servicios de nivel medio

-   Llamada/conversación

Para recopilar registros para Linux:
- Método abreviado de <kbd>teclado: Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Mayús</kbd>  +  <kbd>1</kbd>  
- Los archivos estarán disponibles en `~/Downloads`

Para recopilar registros del Explorador y Windows:
- Método abreviado de <kbd>teclado: Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Mayús</kbd>  +  <kbd>1</kbd>  
- Los archivos estarán disponibles en `%userprofile%\Downloads`

## <a name="media-logs"></a>Registros de medios

Consulte la _sección Recopilar y habilitar el registro_ para obtener Windows y Mac. Los registros multimedia contienen datos de diagnóstico sobre audio, vídeo y uso compartido de pantalla en Teams reuniones. Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con llamadas.

El registro multimedia está desactivado de forma predeterminada. Para registrar datos de diagnóstico Teams reuniones, los usuarios deben activar la opción en el Teams cliente. Vaya **a Configuración** General , active la casilla Habilitar registro para diagnósticos de reuniones (requiere reiniciar Teams), reinicie Teams y  >  reproduzca el problema. 

Cuando envíe los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo cuando reproduzca el problema.

Para recopilar registros para Linux:  
- Los archivos estarán disponibles en las siguientes ubicaciones:
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Para recopilar registros para Windows:  
- Los archivos estarán disponibles en las siguientes ubicaciones:
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\media-stack\\\*\.blog`
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\skylib\\\*\.blog` 

Para recopilar registros para Mac:
- Los archivos estarán disponibles en las siguientes ubicaciones:
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

Esta es una lista de los archivos de registro que se generan y la información que contienen.

<br/>

|Nombre de archivo de registro  |Descripción  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | Contiene información relacionada con la pila de elementos multimedia. Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores usados, así como el número de fotogramas enviados y recibidos, y el estado de la sesión de uso compartido de pantalla basado en cámaras y vídeo (VBSS).         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información del puntero del mouse.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |Registros de eventos de seguimiento de la pila de medios.         |
|`Debug-0-s2790420889.blog`    | Contiene información relacionada con el agente multimedia, incluida la calidad de representación.          |
|`tscalling-0-2061129496.blog`   |Registra eventos en la API de llamadas ts.       |

## <a name="desktop-logs"></a>Registros de escritorio

Consulte la _sección Recopilar y habilitar el registro_ para obtener Windows y Mac. Los registros de escritorio, también conocidos como registros de arranque, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros multimedia, estos registros solo son necesarios si Microsoft lo solicita. Los registros están basados en texto y se pueden leer con cualquier editor basado en texto en un formato de arriba abajo.

Para recopilar registros para Linux:
- Haga clic en el Microsoft Teams en la bandeja del sistema y seleccione **Obtener registros.**
- Los archivos estarán disponibles en `~/.config/Microsoft/Microsoft Teams/logs.txt` .
  
Para recopilar registros para Windows:
- Haga clic en Microsoft Teams icono de la bandeja del sistema y seleccione **Recopilar archivos de soporte técnico.**
- El `logs.txt` archivo se abrirá en Bloc de notas automáticamente.

Al investigar problemas al iniciar sesión Teams, es posible que deba recopilar manualmente los registros de escritorio. Estos archivos de registro se encuentran en %appdata%\Microsoft\Teams en Windows.

## <a name="browser-trace"></a>Seguimiento del explorador

Para algunas categorías de errores, es posible que el soporte técnico de Microsoft requiera que recopile un seguimiento del explorador. Esta información puede proporcionar detalles importantes sobre el estado del Teams cliente cuando se produce el error.

Antes de iniciar el seguimiento del explorador, asegúrese de que ha iniciado sesión en Teams. Es importante hacer esto antes de iniciar el seguimiento para que el seguimiento no contenga información confidencial de inicio de sesión.

Después de haber iniciado sesión, seleccione uno de los vínculos siguientes, según corresponda para el explorador, y siga los pasos proporcionados. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Perimetral](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> En los pasos, reemplace todas las referencias a Azure Portal por el Teams cliente.
  
## <a name="webrtc-logs-in-browsers"></a>Registros webRTC en exploradores
Los registros webRTC pueden ayudar al soporte técnico de Microsoft proporcionando detalles de conexión para llamadas de audio y vídeo. Siga los pasos para obtener acceso a los registros webRTC en Edge (Chromium) o Chrome: 
  
1.  Abra una pestaña nueva y vaya a una de las siguientes direcciones URL:
    -   Borde (Chromium):`edge://webrtc-internals/`
    -   Chrome: `chrome://webrtc-internals/`
  
2.  Abra la Teams web y reproduzca el problema.
  
3.  Vuelva a la pestaña a la que se tuvo acceso en el paso 1 y verá al menos dos pestañas:
    -   Solicitudes de GetUserMedia
    -   `https://teams.microsoft.com/url`

4.  Elija la pestaña con el nombre de la Teams y guarde el contenido de la página.

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
