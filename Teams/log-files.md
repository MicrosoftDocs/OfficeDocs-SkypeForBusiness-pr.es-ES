---
title: Configurar archivos de registro para supervisar y solucionar problemas en Teams
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
description: Obtenga información sobre los registros de depuración, medios y escritorio producidos por Microsoft Teams, dónde se pueden encontrar y cómo pueden ayudarle con la supervisión y la solución de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2edddca64bf0cb50dc29758fd60bc397cbc00f8b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705819"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>Configurar archivos de registro para supervisar y solucionar problemas en Teams

Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar a supervisar y solucionar problemas de Teams:

-   [Registros de depuración](#debug-logs)

-   [Registros multimedia](#media-logs)

-   [Registros de escritorio](#desktop-logs)

En este artículo se describen estos registros y cómo se usan. Para obtener información sobre cómo solucionar problemas específicos, consulte: [Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams). 

Para obtener información sobre cómo recopilar registros de dispositivos Salas de Microsoft Teams, consulta [Descargar registros de dispositivos](/microsoftteams/rooms/rooms-manage#download-device-logs).

Para obtener información sobre cómo ponerse en contacto con el soporte técnico, consulta [Obtener soporte técnico](/microsoft-365/business-video/get-help-support).

> [!NOTE]
> En este artículo, el término **debug logs** hace referencia a los registros que se utilizan para la solución de problemas. Sin embargo, los archivos que se generan para estos registros contendrán los **registros de diagnóstico** del término en sus nombres.  

## <a name="logs-overview"></a>Información general de los registros

Es importante recopilar registros tan pronto como se produzca un problema.

Al crear una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico requerirá los registros de depuración. Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft comenzar rápidamente a solucionar el problema. Los registros **multimedia** o de **escritorio** solo son necesarios si Microsoft lo solicita.

Los registros de depuración, escritorio y medios se recopilarán en una carpeta con el nombre _Registro \<local date and time\>de diagnósticos de MSTeams_ . Esta carpeta se puede comprimir y compartir al abrir una solicitud de soporte técnico con Soporte técnico de Microsoft. La carpeta contendrá carpetas para escritorio, reunión (multimedia) y depuración (web). Puede recopilar los archivos con los siguientes métodos abreviados de teclado:

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>

- Mac: <kbd>Opción</kbd> + <kbd>Comando</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>


Si se produce un problema con una reunión o un evento en directo específicos, resulta útil tener la dirección URL asociada a la reunión. La dirección URL proporciona información adicional para ayudar a identificar la reunión exacta o el evento en directo en los registros. Esta información se puede recopilar de cualquier participante de una reunión o del moderador o productor de un evento en directo. Para capturar esta dirección URL, mantenga el puntero sobre la url de la combinación y elija **Copiar hipervínculo**.

> [!NOTE]
> Si el registro multimedia está habilitado, se incluirán archivos adicionales en la carpeta Reunión que son necesarios para investigar problemas de audio y vídeo. Si el registro multimedia no está habilitado, habrá un número limitado de registros disponibles.
  
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

Los registros de depuración los producen los clientes de escritorio de Windows y Mac, así como los clientes basados en el explorador. Los registros se basan en texto y se leen desde la parte inferior hacia arriba. Se pueden leer con cualquier editor basado en texto y se crean registros nuevos al iniciar sesión en el cliente.

Los registros de depuración muestran los siguientes flujos de datos:

-   Inicio de sesión

-   Solicitudes de conexión a servicios de nivel medio

-   Llamada/conversación

Para recopilar registros para Linux:
- Método abreviado de teclado: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>  
- Los archivos estarán disponibles en `~/Downloads`

Para recopilar registros para El explorador y Windows:
- Método abreviado de teclado: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>  
- Los archivos estarán disponibles en `%userprofile%\Downloads`

Para recopilar registros para Mac:
- Método abreviado de teclado: <kbd>Opción</kbd> + <kbd>Comando</kbd> + <kbd>Mayús</kbd> + <kbd>1</kbd>  
- Los archivos estarán disponibles en `~/Downloads`

## <a name="media-logs"></a>Registros de medios

Los registros multimedia contienen datos de diagnóstico sobre el audio, el vídeo y el uso compartido de la pantalla en las reuniones de Teams. Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con las llamadas.

El registro multimedia está activado de manera predeterminada para equipos si la CPU es:
- cualquier Apple M1
- cualquier Intel Xeon
- cualquier Intel i9, excepto las series U, G7, M y MQ
- cualquier Intel i7 de sexta generación y posterior, excepto las series U, G7, M y MQ

En caso contrario, está desactivada de forma predeterminada. Hay dos formas de registrar datos de diagnóstico para las reuniones de Teams:

- Administración configuración: puede administrar los registros multimedia de los usuarios finales
- Configuración del usuario final: los usuarios finales pueden activar los registros multimedia

### <a name="admin-configuration"></a>configuración de Administración

La administración de registros multimedia para los usuarios finales proporciona una experiencia de solución de problemas fluida, especialmente cuando los problemas son intermitentes. Los administradores pueden usar el cmdlet TeamsMediaLoggingPolicy para habilitar y administrar el registro multimedia para los usuarios.

Lea [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) para cmdlets de PowerShell y más información.

### <a name="end-user-configuration"></a>Configuración del usuario final

Para que los usuarios finales registren datos de diagnóstico para las reuniones de Teams, deben activar la opción en el cliente de Teams. Irán a **Configuración** > **general**, activarán la casilla **Habilitar registros multimedia (datos de diagnóstico para audio, vídeo y uso compartido de la pantalla)** y reproducirán el problema.

> [!NOTE]
> Cuando los usuarios cierran la sesión de Teams, el registro multimedia se restablece a su valor predeterminado.

### <a name="collecting-and-sending-media-logs"></a>Recopilar y enviar registros multimedia

Antes de enviar los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo al reproducir el problema.

Para recopilar registros para Linux:  
- Los archivos estarán disponibles en las siguientes ubicaciones:
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Para recopilar registros de Windows:  
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

Los registros de escritorio, también conocidos como registros de arranque, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros multimedia, estos registros solo son necesarios si Microsoft lo solicita. Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en un formato descendente.

Para recopilar registros para Linux:
- Haga clic en el icono de Microsoft Teams en la bandeja del sistema y seleccione **Obtener registros**.
- Los archivos estarán disponibles en `~/.config/Microsoft/Microsoft Teams/logs.txt`.

Para recopilar registros para Mac:
- Haga clic en el menú Ayuda de Microsoft Teams y seleccione **Recopilar archivos de soporte técnico**.
- El `logs.txt` archivo estará en la carpeta Escritorio, dentro de la carpeta _Registro \<local date and time>de diagnósticos de MSTeams_.

Para recopilar registros de Windows:
- Haga clic en el icono de Microsoft Teams en la bandeja del sistema y seleccione **Recopilar archivos de soporte técnico**.
- El `logs.txt` archivo se abrirá automáticamente en el Bloc de notas.

Al investigar problemas al iniciar sesión en Teams, es posible que deba recopilar manualmente los registros de escritorio. Estos archivos de registro se encuentran en %appdata%\Microsoft\Teams en Windows.

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)

[Registros y seguimiento del explorador para Teams](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
