---
title: Obtener clientes para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Aprenda a usar los distintos clientes disponibles para Microsoft Teams, que incluyen web, escritorio (Windows y Mac) y móvil (Android, iOS y Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cc06497da95f6c9e0f4e6a39d851125922e8b31
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
<a name="get-clients-for-microsoft-teams"></a>Obtener clientes para Microsoft Teams 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams tiene clientes disponibles para web, escritorio (Windows y Mac) y móvil (Android, iOS y Windows Phone). Todos estos clientes requieren una conexión a Internet activa y no admiten el modo sin conexión.

<a name="web-client"></a>Cliente web 
----------------

El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo y funcional que se puede usar desde una variedad de exploradores. En este momento, el cliente web no admite comunicaciones en tiempo real (por ejemplo, unirse a reuniones y realizar llamadas de uno a uno). Además, el explorador debe configurarse para permitir cookies de terceros. 

No se requiere un complemento ni una descarga para utilizar Microsoft Teams con un explorador web.

El cliente Web realiza la detección de la versión de explorador al conectarse a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) y si se detecta una versión de explorador incompatible, se bloquea el acceso a la interfaz Web y se recomienda que el usuario descargue el cliente de escritorio o una aplicación móvil.

<a name="internet-browser-support"></a>Compatibilidad con exploradores web
------------------------------
[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="desktop-clients"></a>Clientes de escritorio
------------------------

El cliente de escritorio Teams de Microsoft es una aplicación independiente y no forma parte de Office Pro Plus actualmente. Equipos está disponible para Windows (7 +), versiones de 32 bits y 64 bits y MacOS (10.10 +). En Windows, los equipos requiere .NET framework 4.5 o posterior; el programa de instalación de equipos ofrecerá a instalarlo si no lo tiene.

Los clientes de escritorio ofrecen soporte de comunicaciones en tiempo real (audio, vídeo y contenido para compartir) para reuniones de equipo, llamadas uno-a-uno de grupo llamada y privada.

Pueden descargar e instalar los usuarios finales directamente desde los clientes de escritorio [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos adecuados locales (derechos de administrador no son necesarios para instalar el cliente de los equipos en un PC pero se requieren en un Mac).

Los administradores de TI pueden elegir su método preferido para distribuir los archivos de instalación en las máquinas de su organización, como System Center Configuration Manager (Windows) o Casper Suite (MacOS).



> [!NOTE]
> La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.


#### <a name="windows"></a>Windows

La instalación de Microsoft Teams para Windows brinda instaladores que se pueden descargar en arquitecturas de 32 y 64 bits. La arquitectura debe coincidir con la del SO, que es el valor predeterminado que toma la descarga en línea.



> [!NOTE]
> La arquitectura (32 o 64 bits) de Microsoft Teams es independiente de la arquitectura de Office que esté instalada.

El cliente de Windows se implementa en la carpeta AppData ubicada en el perfil del usuario. La implementación en el perfil local del usuario permite instalar el cliente sin que se requieran derechos elevados. El cliente de Windows se instala en las siguientes ubicaciones:

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

Cuando los usuarios inician una llamada utilizando el cliente de Microsoft Teams, podrían recibir una advertencia con la configuración del firewall de Windows que les pide que permitan la comunicación. Es posible que se indique a los usuarios que ignoren el mensaje porque la llamada funcionará, incluso si la advertencia se descarta.

![Captura de pantalla de un cuadro de diálogo Alerta de seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de bloqueo para los protocolos TCP y UDP.

#### <a name="mac"></a>Mac

Microsoft solo brinda un archivo de instalación DMG para equipos Mac OSX. Se requiere acceso de administrador para instalar el cliente de Mac. El cliente de Mac OSX se instala en la carpeta /Applications.


<a name="mobile-clients"></a>Clientes móviles
--------------

Las aplicaciones móviles de Microsoft Teams están disponibles para Android, iOS y Windows Phone, y están pensadas para que los usuarios que no están en un lugar fijo participen en conversaciones basadas en chat y para permitir las llamadas de audio de par a par. Para las aplicaciones móviles, vaya a la tienda móvil correspondiente: Google Play, App Store de Apple o Microsoft Store.

Las siguientes son las plataformas móviles admitidas para Microsoft Teams:

-   **Android** 4.4 o posterior

-   **iOS**: 10.0 o posterior

-   **Windows Phone**: Windows 10 Mobile

Las aplicaciones móviles se distribuyen y actualizan solo a través de la correspondiente tienda de aplicaciones para la plataforma móvil y no están disponibles para su distribución a través de soluciones de administración de dispositivos móviles (MDM) o de transferencia local.


| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Get_clients_for_Microsoft_Teams_image4.png)      |Punto de decisión         |¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?         |
|![Icono de Siguientes pasos.](media/Get_clients_for_Microsoft_Teams_image5.png)     |Siguientes pasos         |Si su organización restringe la instalación de software, asegúrese de que el proceso sea compatible con Microsoft Teams. Nota: No se requieren derechos de administrador para instalar el cliente en PC, pero sí son necesarios para Mac.         |


  <span id="_Hlk477176062" class="anchor"></span>  Punto de decisión   ¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?

<a name="client-update-management"></a>Administración de actualizaciones del cliente
------------------------

Actualmente, el servicio de Microsoft Teams actualiza los clientes en forma automática, sin que se necesite la intervención del administrador de TI. Si hay una actualización disponible, el cliente descargará automáticamente la actualización y, cuando la aplicación esté inactiva durante un tiempo, comenzará el proceso de actualización.

<a name="client-side-configurations"></a>Configuración del lado del cliente
---------------------------

Actualmente, no hay opciones disponibles para configurar el cliente a través del administrador de inquilinos, PowerShell, Group Policy Objects ni el registro.

<a name="notification-settings"></a>Configuración de notificaciones
----------------------------

En este momento, no hay opciones disponibles para que los administradores de TI puedan configurar las notificaciones para los clientes. Todas las opciones de notificaciones las establece el usuario. En la siguiente figura se detalla la configuración predeterminada del cliente.

![Captura de pantalla de la configuración de Notificaciones.](media/Get_clients_for_Microsoft_Teams_image6.png)
