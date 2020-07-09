---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 2303082c4f1c16a28a9116047d904a5d491a535a
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085756"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usar los archivos de registro para solucionar problemas en Microsoft Teams
=================================================

Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.

-   Registros de depuración

-   Registros de medios

-   Registros de escritorio

When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.

The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.


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

Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft. Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en explorador. Los registros se basan en texto y se leen de abajo hacia arriba. Se pueden leer con cualquier editor basado en texto y los nuevos registros se crean al iniciar sesión en el cliente.

Los registros de depuración muestran los siguientes flujos de datos:

-   Inicio de sesión

-   Solicitudes de conexión a servicios de nivel intermedio

-   Llamada/conversación

Los registros de depuración se generan usando los siguientes métodos de SO específicos:

-   Windows:

      Método abreviado de teclado: Ctrl + Alt + Mayús + 1

-   Mac OSX:

      Método abreviado de teclado: Opción + Comando + Mayús + 1

-   Linux

      Método abreviado de teclado: Ctrl + Alt + Mayús + 1

Los registros de depuración se descargan automáticamente en las siguientes carpetas.

-   Windows: %userprofile%\\Descargas

-   Mac OSX: Descargas

-   Linux: ~/downloads

-   Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.

<a name="media-logs"></a>Registros de medios
---------------------------

Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.


|Cliente |Ubicación |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *. ETL         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-Stack/*. blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*. blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-Stack/*. blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*. blog         |



<a name="desktop-logs"></a>Registros de escritorio
---------------------

Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.

Windows:

1.  Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .

Mac OsX:

1.  Elija **Obtener registros** en el menú desplegabe **Ayuda**.

Linux

1.  Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros** .

|Cliente |Ubicación |
|---------|---------|
|Windows     |% appdata% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

