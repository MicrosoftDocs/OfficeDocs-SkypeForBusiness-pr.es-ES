---
title: Obtener clientes para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar los distintos clientes disponibles para Microsoft Teams, que incluyen web, escritorio (Windows y Mac) y móvil (iOS y Android).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e8a77a6d03735769e61f679126b3a5aac7f70e3
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "37563612"
---
<a name="get-clients-for-microsoft-teams"></a>Obtener clientes para Microsoft Teams 
===========================

Microsoft Teams tiene clientes disponibles para web, escritorio (Windows y Mac) y móvil (iOS y Android). Todos estos clientes requieren una conexión a Internet activa y no admiten el modo sin conexión.

> [!NOTE]
> A partir del 29 de noviembre de 2018, ya no podrá usar la aplicación de Microsoft Teams para Windows 10 S (versión preliminar), disponible en Microsoft Store. En su lugar, ahora puede descargar e instalar el cliente de escritorio de Teams en dispositivos que ejecutan el modo Windows 10 S. Para descargar el cliente de escritorio, vaya [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)a. Las compilaciones MSI del cliente de escritorio de Teams aún no están disponibles para los dispositivos que ejecutan el modo Windows 10 S.
>
> Para obtener más información sobre el modo de Windows 10 S, consulte [Introducción a Windows 10 en modo S](https://www.microsoft.com/windows/s-mode). 

<a name="desktop-client"></a>Cliente de escritorio
--------------

> [!Tip]
> Vea la sesión siguiente para conocer las ventajas del cliente de escritorio de Windows, y cómo planearlo e implementarlo: [Cliente de escritorio de Teams para Windows](https://aka.ms/teams-clients)

El cliente de escritorio de Microsoft Teams es una aplicación independiente y también está [disponible en Office 365 ProPlus](https://docs.microsoft.com/en-us/deployoffice/teams-install). Teams está disponible para Windows (7 y posteriores) en versiones de 32 y 64 bits, y para macOS (10.10 y posteriores). En Windows, Teams requiere .NET Framework 4.5 o posterior; el instalador de Teams le ofrecerá instalarlo si no lo tiene. 

Los clientes de escritorio brindan asistencia en tiempo real para las comunicaciones (audio, vídeo y contenido compartido) para las reuniones de equipo, las llamadas grupales y las llamadas de uno a uno.

Los usuarios pueden descargar e instalar los clientes de escritorio directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos locales adecuados (no se requieren derechos de administrador para instalar el cliente de Teams en PC, pero sí son necesarios para Mac).

Los administradores de TI pueden elegir su método preferido para distribuir los archivos de instalación en los equipos de su organización, como System Center Configuration Manager (Windows) o Jamf Pro (macOS). Para obtener el paquete de MSI de distribución de Windows, vea [Instalar Microsoft Teams con MSI](msi-deployment.md).  

> [!NOTE]
> La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.

### <a name="windows"></a>Windows

La instalación de Microsoft Teams para Windows brinda instaladores que se pueden descargar en arquitecturas de 32 y 64 bits.

> [!NOTE]
> La arquitectura (32 o 64 bits) de Microsoft Teams es independiente de la arquitectura de Windows y Office que esté instalada.

El cliente de Windows se implementará en la carpeta AppData ubicada en el perfil del usuario. Implementar en el perfil de usuario local permite instalar el cliente sin necesidad de tener permisos elevados. El cliente de Windows aprovecha las siguientes ubicaciones:

- %LocalAppData%\\Microsoft\\Teams

- % LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Cuando los usuarios inician una llamada utilizando el cliente de Microsoft Teams, podrían recibir una advertencia con la configuración del firewall de Windows que les pide que permitan la comunicación. Es posible que se indique a los usuarios que ignoren el mensaje porque la llamada funcionará, incluso si la advertencia se descarta.

![Captura de pantalla de un cuadro de diálogo Alerta de seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de bloqueo para los protocolos TCP y UDP.

### <a name="mac"></a>Mac

Los usuarios de Mac pueden instalar Teams mediante el uso de un archivo PKG de instalación para equipos macOS. Se requiere acceso administrativo para instalar el cliente de Mac. El cliente de macOS se instala en la carpeta /Applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Instalar Teams con el archivo PKG 

1. Desde la [página de descarga de Teams](https://teams.microsoft.com/downloads), en **Mac**, haga clic en **Descargar**.
2. Haga doble clic en el archivo PKG.
3. Siga los pasos del asistente de instalación para completar la instalación.
4. Se instalará Teams en la carpeta /Applications. Es una instalación de todo el equipo.

> [!NOTE]
> Durante la instalación, el PKG solicitará las credenciales de administrador. El usuario debe escribir las credenciales de administrador, independientemente de si el usuario es un administrador.

Si un usuario actualmente tiene una instalación DMG de Teams y quiere reemplazarla con la instalación del PKG, el usuario debe:

1. Salir de la aplicación de Teams.
2. Desinstalar la aplicación de Teams.
3. Instale el archivo PKG.

Los administradores de TI pueden usar la implementación administrada de Teams para distribuir los archivos de instalación en todos los equipos Mac en su organización, como Jamf Pro.

> [!NOTE]
> Si tiene problemas para instalar el PKG, háganoslo saber. En la sección **Comentarios** al final de este artículo, haga clic en **Comentarios sobre el producto**.

<a name="web-client"></a>Cliente web 
----------

El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo y funcional que puede utilizarse desde una variedad de exploradores. El cliente web es compatible con Llamadas y Reuniones mediante webRTC, por lo que no se requiere ningún complemento o descarga para ejecutar Teams en un explorador web. El explorador debe configurarse para permitir cookies de terceros. 

[!INCLUDE [browser-support](includes/browser-support.md)]

El cliente web detecta la versión del explorador al conectarse con [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Si se detecta una versión no admitida, se bloquea el acceso a la interfaz web y se recomienda al usuario que descargue el cliente de escritorio o la aplicación móvil.

<a name="mobile-clients"></a>Clientes móviles
--------------

Las aplicaciones móviles de Microsoft Teams están disponibles para iOS y Android, y están pensadas para que los usuarios que no están en un lugar fijo participen en conversaciones basadas en chat y para permitir las llamadas de audio de par a par. Para las aplicaciones móviles, vaya a la tienda móvil correspondiente: Google Play y App Store de Apple. La aplicación de Windows Phone se retiró el 20 de julio de 2018 y podría dejar de funcionar. 

Las siguientes son las plataformas móviles admitidas para Microsoft Teams:

-   **Android** 4.4 o posterior

-   **iOS**: 10.0 o posterior

> [!NOTE]
> La versión móvil debe estar disponible para el público para que Teams funcione según lo esperado.

Las aplicaciones móviles se distribuyen y actualizan solo en la tienda de aplicaciones de la plataforma móvil correspondiente. Microsoft no admite la distribución de aplicaciones móviles a través de MDM o de carga. Una vez instalada la aplicación móvil en una plataforma móvil compatible, se admitirá la aplicación móvil Teams en sí, siempre y cuando la versión esté en un plazo de tres meses a partir de la versión actual.


| | | |
|---------|---------|---------|
|![Un icono que muestra un punto de decisión](media/Get_clients_for_Microsoft_Teams_image4.png)      |Punto de decisión         |¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?         |
|![Un icono que representa los siguientes pasos](media/Get_clients_for_Microsoft_Teams_image5.png)     |Siguientes pasos         |Si su organización restringe la instalación de software, asegúrese de que el proceso sea compatible con Microsoft Teams. Nota: No se requieren derechos de administrador para instalar el cliente en PC, pero sí son necesarios para Mac.         |

<a name="client-update-management"></a>Administración de actualizaciones del cliente
------------------------

En la actualidad, los clientes se actualizan automáticamente con el servicio de Microsoft Teams sin necesidad de intervención del administrador de ti. Si hay una actualización disponible, el cliente descargará la actualización automáticamente y cuando la aplicación haya inactivado durante un período de tiempo, se iniciará el proceso de actualización.

<a name="client-side-configurations"></a>Configuración del lado del cliente
---------------------------

Actualmente, no hay opciones disponibles para configurar el cliente a través del administrador de inquilinos, PowerShell, Group Policy Objects ni el registro.

<a name="notification-settings"></a>Configuración de notificaciones
----------------------------

En este momento, no hay opciones disponibles para que los administradores de TI puedan configurar las notificaciones para los clientes. Todas las opciones de notificaciones las establece el usuario. En la siguiente figura se detalla la configuración predeterminada del cliente.

![Captura de pantalla de la configuración de Notificaciones.](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>Ejemplo de Script de PowerShell
----------------------------

Este script de ejemplo, que tiene que ejecutarse en los equipos de cliente en el contexto de una cuenta de administrador con privilegios elevados, creará una nueva regla de firewall de entrada para cada carpeta de usuario que se encuentra en c:\users. Cuando Teams encuentra esta regla, impedirá que la aplicación de Teams solicite a los usuarios crear reglas de firewall cuando los usuarios realicen su primera llamada de Teams. 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
