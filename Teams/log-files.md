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
description: Obtén información sobre los registros de depuración, medios y escritorio generados por Microsoft Teams, dónde se pueden encontrar y cómo pueden ayudar con la supervisión y la solución de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 178e89ff91de4638f6a9ff56a4dcb935d18f6f91
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056950"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Usar archivos de registro para supervisar y solucionar problemas de Microsoft Teams

Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar a supervisar y solucionar problemas Teams:

-   [Registros de depuración](#debug-logs)

-   [Registros multimedia](#media-logs)

-   [Registros de escritorio](#desktop-logs)

En este artículo se describen estos registros y cómo se usan. Para obtener información sobre cómo solucionar problemas específicos, consulte: [Teams Solución de problemas](/MicrosoftTeams/troubleshoot/teams). Para obtener información sobre cómo ponerse en contacto con el soporte técnico, consulta [Obtener soporte técnico](/microsoft-365/business-video/get-help-support). Al crear una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico requerirá los registros de depuración. Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft comenzar rápidamente a solucionar el problema. Los registros **multimedia** o de **escritorio** solo son necesarios si Microsoft lo solicita.

> [!NOTE]
> En este artículo, el término **debug logs** hace referencia a los registros que se utilizan para la solución de problemas. Sin embargo, los archivos que se generan para estos registros contendrán los **registros de diagnóstico** del término en sus nombres.  

## <a name="collect-and-enable-logging"></a>Recopilar y habilitar el registro

Es importante recopilar registros tan pronto como se produzca un problema. Los registros se pueden recopilar con solo un par de clics.

- Windows: haz clic con el botón derecho en el icono de Teams de la bandeja del sistema y elige **Recopilar archivos de soporte** técnico. 

- Mac: seleccione el menú Ayuda y elija **Recopilar archivos de soporte técnico**.

Los registros de depuración, escritorio y medios se recopilarán en una carpeta con el nombre _Registro \<local date and time\>de diagnósticos de MSTeams_ . Esta carpeta se puede comprimir y compartir al abrir una solicitud de soporte técnico con Soporte técnico de Microsoft. La carpeta contendrá carpetas para escritorio, reunión (multimedia) y depuración (web). Puede recopilar los archivos con los siguientes métodos abreviados de teclado:

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>

- Mac: <kbd>Opción</kbd> + <kbd>Comando</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>


El registro multimedia solo está activado de manera predeterminada para algunas CPU, que se describen en [registros multimedia](#media-logs). En caso contrario, está desactivada de forma predeterminada. Para habilitar el registro multimedia, los usuarios deben activar la opción en el cliente de Teams. Vaya a **Configuración** >  **General** y seleccione **Habilitar registro para diagnósticos de reuniones (requiere reiniciar Teams)**. El cliente de Teams debe reiniciarse para iniciar el registro (reinícielo haciendo clic con el botón derecho en el icono del Dock (Mac) o la barra de tareas (Windows) y seleccionando **Salir**. Después de salir, solo tienes que hacer clic en el icono de la aplicación para volver a abrirla).

Si se produce un problema con una reunión o un evento en directo específicos, resulta útil tener la dirección URL asociada a la reunión. Esto proporciona información adicional para ayudar a identificar la reunión exacta o el evento en directo en los registros. Esta información se puede recopilar de cualquier participante de una reunión o del moderador o productor de un evento en directo. Para capturar esta dirección URL, mantenga el puntero sobre la url de la combinación y elija **Copiar hipervínculo**.

> [!NOTE]
> Si el registro multimedia está habilitado, se incluirán archivos adicionales en la carpeta Reunión que son necesarios para investigar problemas de audio y vídeo. Si el registro multimedia no está habilitado, habrá un número limitado de registros disponibles.
  
> [!NOTE]
> Anteriormente, los registros de depuración se recopilaban usando los métodos abreviados de teclado siguientes. Estas siguen funcionando y completarán la misma captura de registro que la opción **Recopilar archivos de soporte técnico** .
>
> - Windows: <kbd>Alt Ctrl</kbd> + <kbd></kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>
>
> - Mac: <kbd>Opción</kbd> + <kbd>Comando</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>


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

Consulte la sección _Recopilar y habilitar el registro_ para obtener instrucciones de Windows y Mac. Los registros de depuración los producen los clientes de escritorio de Windows y Mac, así como los clientes basados en el explorador. Los registros se basan en texto y se leen desde la parte inferior hacia arriba. Se pueden leer con cualquier editor basado en texto y se crean registros nuevos al iniciar sesión en el cliente.

Los registros de depuración muestran los siguientes flujos de datos:

-   Inicio de sesión

-   Solicitudes de conexión a servicios de nivel medio

-   Llamada/conversación

Para recopilar registros para Linux:
- Método abreviado de teclado: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>  
- Los archivos estarán disponibles en `~/Downloads`

Para recopilar registros para el explorador y los Windows:
- Método abreviado de teclado: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>  
- Los archivos estarán disponibles en `%userprofile%\Downloads`

Para recopilar registros para Mac:
- Método abreviado de teclado: <kbd>Opción</kbd> + <kbd>Comando</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>  
- Los archivos estarán disponibles en `~/Downloads`

## <a name="media-logs"></a>Registros de medios

Consulte la sección _Recopilar y habilitar el registro_ para obtener instrucciones de Windows y Mac. Los registros multimedia contienen datos de diagnóstico sobre el audio, el vídeo y el uso compartido de la pantalla en Teams reuniones. Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con las llamadas.

El registro multimedia está activado de manera predeterminada para equipos si la CPU es:
- cualquier Apple M1
- cualquier Intel Xeon
- cualquier Intel i9, excepto las series U, G7, M y MQ
- cualquier Intel i7 de sexta generación y posterior, excepto las series U, G7, M y MQ

En caso contrario, está desactivada de forma predeterminada. Para registrar datos de diagnóstico para Teams reuniones, los usuarios deben activar la opción en el cliente de Teams. Vaya a **Configuración** >  **General**, active la casilla Habilitar el **registro para diagnósticos de reuniones (es necesario reiniciar Teams**), reinicie Teams y reproduzca el problema. 

> [!NOTE]
> Al cerrar la sesión de Teams, el registro multimedia se restablece a su valor predeterminado. 

Cuando envíe los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo al reproducir el problema.

Para recopilar registros para Linux:  
- Los archivos estarán disponibles en las siguientes ubicaciones:
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Para recopilar registros para Windows:  
- Los archivos estarán disponibles en las siguientes ubicaciones:
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

Para recopilar registros para Mac:
- Los archivos estarán disponibles en las siguientes ubicaciones:
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

Esta es una lista de los archivos de registro que se generan y la información que contienen.

<br/>

|Nombre del archivo de registro  |Descripción  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | Contiene información relacionada con la pila de medios. Esto incluye el estado del canal, como la resolución, los descodificadores y codificadores usados, el número de fotogramas enviados y recibidos, así como el estado de la sesión de cámara y pantalla compartida basada en vídeo (VBSS).         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control, e información del puntero del mouse.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |Registra eventos de seguimiento de pila de medios.         |
|`Debug-0-s2790420889.blog`    | Contiene información relacionada con el agente multimedia, incluida la calidad de representación.          |
|`tscalling-0-2061129496.blog`   |Registra eventos en la API de llamada ts.       |

## <a name="desktop-logs"></a>Registros de escritorio

Consulte la sección _Recopilar y habilitar el registro_ para obtener instrucciones de Windows y Mac. Los registros de escritorio, también conocidos como registros de arranque, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros multimedia, estos registros solo son necesarios si Microsoft lo solicita. Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en un formato descendente.

Para recopilar registros para Linux:
- Haz clic en el icono Microsoft Teams de la bandeja del sistema y selecciona **Obtener registros**.
- Los archivos estarán disponibles en `~/.config/Microsoft/Microsoft Teams/logs.txt`.

Para recopilar registros para Mac:
- Haga clic en el menú Ayuda de Microsoft Teams y seleccione **Recopilar archivos de soporte técnico**.
- El `logs.txt` archivo estará en la carpeta Escritorio, dentro de la carpeta _Registro \<local date and time>de diagnósticos de MSTeams_.

Para recopilar registros para Windows:
- Haz clic en el icono Microsoft Teams de la bandeja del sistema y selecciona **Recopilar archivos de soporte técnico**.
- El `logs.txt` archivo se abrirá automáticamente en Bloc de notas.

Al investigar problemas al iniciar sesión en Teams, es posible que deba recopilar manualmente los registros de escritorio. Estos archivos de registro se encuentran en %appdata%\Microsoft\Teams en Windows.

## <a name="browser-trace"></a>Seguimiento del explorador

Para algunas categorías de errores, Soporte técnico de Microsoft puede requerir que recopile un seguimiento del explorador. Esta información puede proporcionar detalles importantes sobre el estado del cliente de Teams cuando se produce el error.

Antes de iniciar el seguimiento del explorador, asegúrese de que ha iniciado sesión en Teams. Es importante hacerlo antes de iniciar el seguimiento para que no contenga información de inicio de sesión confidencial.

Después de iniciar sesión, seleccione uno de los siguientes vínculos, según corresponda para su explorador, y siga los pasos proporcionados. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Perimetral](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> En los pasos, reemplace todas las referencias a la Azure Portal con el cliente de Teams.
  
## <a name="webrtc-logs-in-browsers"></a>Registros WebRTC en exploradores
Los registros WebRTC pueden ayudar a Soporte técnico de Microsoft proporcionando detalles de conexión para llamadas de audio y vídeo. Sigue los pasos para acceder a los registros webRTC en Edge (Chromium) o Chrome: 
  
1.  Abre una pestaña nueva y ve a una de las siguientes direcciones URL:
    -   Edge (Chromium):`edge://webrtc-internals/`
    -   Cromo: `chrome://webrtc-internals/`
  
2.  Abre la aplicación web Teams y reproduce el problema.
  
3.  Volver a la pestaña a la que se obtuvo acceso en el paso 1 y verá al menos dos pestañas:
    -   Solicitudes getUserMedia
    -   `https://teams.microsoft.com/url`

4.  Elija la pestaña con el nombre de la aplicación Teams y guarde el contenido de la página.

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
