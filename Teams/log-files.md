---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Conozca los registros de depuración, medios y escritorio generados por Microsoft Teams, dónde se encuentran y cómo pueden ser útiles para resolver problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112196"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usar los archivos de registro para solucionar problemas en Microsoft Teams
=================================================

Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar a solucionar problemas de Microsoft Teams:

-   Registros de depuración

-   Registros de medios

-   Registros de escritorio

Al crear una solicitud de soporte técnico con soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Tener los registros de depuración a mano antes de crear la solicitud de soporte técnico permitirá a Microsoft empezar rápidamente a solucionar el problema. **Los registros** **multimedia o de** escritorio solo son necesarios si Microsoft lo solicita.

> [!NOTE]
> En este artículo, el término **Registros de depuración** hace referencia a los registros que se usan para la solución de problemas. Sin embargo, los archivos que se generan para estos registros contendrán el término registros **de diagnóstico** en sus nombres.  

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

<a name="debug-logs"></a>Registros de depuración
---------------------------

Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft. Los registros de depuración los producen los clientes de escritorio de Windows y Mac, así como los clientes basados en exploradores. Los registros se basan en texto y se leen desde abajo hacia arriba. Se pueden leer con cualquier editor basado en texto y se crean nuevos registros al iniciar sesión en el cliente.

Los registros de depuración muestran los siguientes flujos de datos:

-   Inicio de sesión

-   Solicitudes de conexión a servicios de nivel medio

-   Llamada/conversación

Los registros de depuración se generan con los siguientes métodos específicos del sistema operativo:

-   Windows:

      Método abreviado de teclado: Ctrl + Alt + Mayús + 1

-   Mac OSX:

      Método abreviado de teclado: Opción + Comando + Mayús + 1

-   Linux:

      Método abreviado de teclado: Ctrl + Alt + Mayús + 1

Los registros de depuración se descargan automáticamente en las siguientes carpetas:

-   Windows: %userprofile%\\Descargas

-   Mac OSX: ~/Descargas

-   Linux: ~/Descargas

-   Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.

<a name="media-logs"></a>Registros de medios
---------------------------

Los registros multimedia contienen datos de diagnóstico sobre audio, vídeo y uso compartido de pantalla en las reuniones de Teams. Son necesarios para los casos de soporte técnico vinculados a problemas relacionados con llamadas.

El registro multimedia está desactivado de forma predeterminada. Para registrar datos de diagnóstico para reuniones de Teams, los usuarios deben activar la opción en el cliente de Teams. Vaya a **Configuración** general , active la casilla Habilitar registro para diagnósticos de reuniones (requiere reiniciar  >   **Teams),** reinicie Teams y reproduzca el problema. 

En la tabla siguiente se describen las ubicaciones de registro multimedia. Cuando envíe los archivos de registro al soporte técnico de Microsoft, compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el período de tiempo cuando reproduzca el problema.

|Cliente |Ubicación |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Esta es una lista de los archivos de registro que se generan y la información que contienen.

|Nombre de archivo de registro  |Descripción  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Contiene información relacionada con la pila de elementos multimedia. Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores usados, así como el número de fotogramas enviados y recibidos, y el estado de la sesión de uso compartido de pantalla basado en cámaras y vídeo (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información del puntero del mouse.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Registros de eventos de seguimiento de la pila de medios.         |
|Debug-0-s2790420889.blog    | Contiene información relacionada con el agente multimedia, incluida la calidad de representación.          |
|tscalling-0-2061129496.blog   |Registra eventos en la API de llamadas ts.       |

<a name="desktop-logs"></a>Registros de escritorio
---------------------

Los registros de escritorio, también conocidos como registros de arranque, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros multimedia, estos registros solo son necesarios si Microsoft lo solicita. Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en un formato de arriba abajo.

Windows:

 - Haga clic con el botón derecho en **el icono de Microsoft Teams** en la bandeja del sistema y seleccione Obtener **registros.**

Mac OsX:

 - Elija **Obtener registros** en el menú desplegable Ayuda. 

Linux:

 - Haga clic en el **icono de Microsoft Teams** en la bandeja del sistema y seleccione Obtener **registros.**

|Cliente |Ubicación |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)