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
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761098"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usar los archivos de registro para solucionar problemas en Microsoft Teams
=================================================

Hay tres tipos de archivos de registro generados automáticamente por el cliente, que se pueden aprovechar para ayudar en la solución de problemas de Microsoft Teams:

-   Registros de depuración

-   Registros de medios

-   Registros de escritorio

Al crear una solicitud de soporte con el soporte técnico de Microsoft, el ingeniero de soporte técnico necesitará los registros de depuración. Si cierra la sesión de depuración antes de crear la solicitud de soporte técnico, Microsoft le permitirá comenzar rápidamente a solucionar el problema. Los registros de **medios** o de **escritorio** solo son necesarios si lo solicita Microsoft.

> [!NOTE]
> En este artículo, el término **registros de depuración** hace referencia a los registros que se usan para la solución de problemas. Sin embargo, los archivos que se generan para estos registros contendrán el término **registros de diagnóstico** en sus nombres.  

En la tabla siguiente se describen los distintos clientes y los registros asociados. Los archivos de registro se almacenan en ubicaciones específicas del cliente y del sistema operativo.


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

Estos son los registros más comunes y son necesarios para todos los casos de soporte técnico de Microsoft. Los registros de depuración los generan los clientes de escritorio de Windows y Mac, así como los clientes basados en el explorador. Los registros se basan en texto y se leen de abajo hacia arriba. Se pueden leer con cualquier editor basado en texto y se crean nuevos registros al iniciar sesión en el cliente.

Los registros de depuración muestran los siguientes flujos de datos:

-   Inicio de sesión

-   Solicitudes de conexión a servicios de nivel medio

-   Llamada/conversación

Los registros de depuración se generan con los siguientes métodos específicos del sistema operativo:

-   Windows:

      Método abreviado de teclado: Ctrl + Alt + Mayús + 1

-   Mac OSX:

      Método abreviado de teclado: Opción + Comando + Mayús + 1

-   Linux

      Método abreviado de teclado: Ctrl + Alt + Mayús + 1

Los registros de depuración se descargan automáticamente en las siguientes carpetas:

-   Windows: %userprofile%\\Descargas

-   Mac OSX: ~/downloads

-   Linux: ~/downloads

-   Explorador: Se le pedirá que guarde el registro de depuración en la ubicación predeterminada.

<a name="media-logs"></a>Registros de medios
---------------------------

Los registros multimedia contienen datos de diagnóstico sobre el audio, el vídeo y la pantalla compartida en reuniones de Teams. Son necesarios para los casos de soporte técnico que están vinculados a problemas relacionados con la llamada.

El registro multimedia está desactivado de forma predeterminada. Para registrar los datos de diagnóstico de las reuniones de Teams, los usuarios deben activar la opción en el cliente de Teams. Vaya a **configuración**  >  **General**, active la casilla **Habilitar el registro de diagnósticos de reunión (debe reiniciar Teams**), reinicie Teams y reproduzca el problema. 

En la tabla siguiente se describen las ubicaciones de los registros de medios. Cuando envíe los archivos de registro al soporte técnico de Microsoft, Compruebe la marca de tiempo de los archivos de registro para asegurarse de que los registros cubren el intervalo de tiempo cuando reproducido el problema.

|Cliente |Ubicación |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *. ETL         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-Stack/*. blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*. blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-Stack/*. blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*. blog         |

Esta es una lista de los archivos de registro que se generan y la información que contienen.

|Nombre de archivo de registro  |Descripción  |
|---------|---------|
|Teams. MSRTC-0-s1039525249. blog     | Contiene información relacionada con la pila de medios. Esto incluye el estado del canal, como la resolución, los descodificadores y los codificadores que se usan, así como el número de tramas enviadas y recibidas y el estado de sesión de pantalla compartida basada en vídeo y en vídeo (VBSS).         |
|rtmcontrol. MSRTC-0-2415069487. blog      |Registra información relacionada con acciones de control remoto, como la marca de tiempo cuando se proporciona el control e información sobre el puntero del mouse.          |
|Teams_MediaStackETW -2-U-xr-U. ETL      |Registra eventos de seguimiento de pila de medios.         |
|Depurar: 0-s2790420889. blog    | Contiene información relacionada con el agente multimedia, incluida la calidad de representación.          |
|tscalling-0-2061129496. blog   |Registra eventos en la API de llamadas de TS.       |

<a name="desktop-logs"></a>Registros de escritorio
---------------------

Los registros de escritorio, también conocidos como registros del programa previo, contienen datos de registro que se producen entre el cliente de escritorio y el explorador. Al igual que los registros de medios, estos registros solo son necesarios si lo solicita Microsoft. Los registros se basan en texto y se pueden leer con cualquier editor basado en texto en un formato descendente.

Windows:

 - Haga clic con el botón derecho en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros**.

Mac OsX:

 - Elija **obtener registros** en el menú desplegable **ayuda** .

Linux

 - Haga clic en el icono de **Microsoft Teams** de la bandeja del sistema y seleccione **obtener registros**.

|Cliente |Ubicación |
|---------|---------|
|Windows     |% appdata% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
