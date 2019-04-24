---
title: Usar los archivos de registro para solucionar problemas en Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Conozca los registros de depuración, medios y escritorio generados por Microsoft Teams, dónde se encuentran y cómo pueden ser útiles para resolver problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e0484b84daa1bd8604c5f2caf9cb728f8fce25a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219782"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usar los archivos de registro para solucionar problemas en Microsoft Teams
=================================================

Hay tres tipos de archivos de registro que el cliente genera automáticamente y que pueden usarse para ayudar en la solución de problemas de Microsoft Teams.

-   Registros de depuración

-   Registros de medios

-   Registros de escritorio

Cuando se crea una solicitud de soporte técnico con Soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Disponer de estos registros con antelación, antes de crear la solicitud de soporte técnico, permitirá a Microsoft empezar rápidamente a resolver el problema. Los registros de medios o de escritorio solo son necesarios si los solicita Microsoft.

En esta table se muestran los distintos clientes y sus registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y el sistema operativo.


|Cliente |Depuración|Escritorio|Medios|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Para ver una lista completa de los sistemas operativos y los exploradores compatibles, vea [Obtener clientes para Microsoft Teams](get-clients.md).

<a name="debug-logs"></a>Registros de depuración
---------------------------

Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft. Depurar los registros producidos por los clientes de escritorio de Windows y Mac, así como los clientes basado en el explorador. Los registros son texto basados y copia de seguridad que se leen de la parte inferior. Puede leer con cualquier editor de texto en función y se crean los registros de nuevo al iniciar sesión en el cliente.

Los registros de depuración muestran los siguientes flujos de datos:

-   Inicio de sesión

-   Solicitudes de conexión a servicios de nivel intermedio

-   Llamada/conversación

Los registros de depuración se generan usando los siguientes métodos de SO específicos:

-   Windows:

      Método abreviado de teclado: Ctrl + Alt + Mayús + 1

-   Mac OSX:

      Método abreviado de teclado: Opción + Comando + Mayús + 1

Los registros de depuración se descargan automáticamente en las siguientes carpetas.

-   Windows: %userprofile%\\Descargas

-   Mac OSX: Descargas

-   Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.

<a name="media-logs"></a>Registros de medios
---------------------------

Los registros de medios contienen datos de diagnóstico sobre el uso compartido de pantalla, audio, vídeo. Son necesarios para resolver casos de soporte técnico. Se generan únicamente bajo petición y solo pueden ser inspeccionados por Microsoft. En la siguiente tabla se muestra la ubicación del registro.


|Cliente |Ubicación |
|---------|---------|
|Windows     |%AppData%\Microsoft\Teams\media-Stack\*.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack\*.blog         |


<a name="desktop-logs"></a>Registros de escritorio
---------------------

Los registros de escritorio, también conocidos como registros de programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si los solicita Microsoft. Los registros son archivos de texto y se pueden leer con cualquier editor de texto de arriba abajo.

Windows:

1.  Haga clic con el botón secundario en el **icono de Microsoft Teams** en la bandeja de la aplicación y seleccione **Obtener registros**.

Mac OsX:

1.  Elija **Obtener registros** en el menú desplegabe **Ayuda**.

|Cliente |Ubicación |
|---------|---------|
|Windows     |%AppData%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
