---
title: "Obtener clientes para Microsoft Teams | Soporte técnico de Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Aprenda a usar los distintos clientes disponibles para Microsoft Teams, que incluyen web, escritorio (Windows y Mac) y móvil (Android, iOS y Windows Phone)."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 83cc4e58063c1dac9e3601a9f59673a2628914f5
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
<a name="get-clients-for-microsoft-teams"></a>Obtener clientes para Microsoft Teams 
===========================

Microsoft Teams tiene clientes disponibles para web, escritorio (Windows y Mac) y móvil (Android, iOS y Windows Phone). Todos estos clientes requieren una conexión a Internet activa y no admiten el modo sin conexión.

<a name="web-client"></a>Cliente web 
----------------

El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo y funcional que puede utilizarse desde una variedad de exploradores. En este momento, el cliente web no admite comunicaciones en tiempo real (por ejemplo, unirse a reuniones y realizar llamadas de uno a uno). Además, el explorador debe configurarse para permitir cookies de terceros.

No se requiere un complemento ni una descarga para utilizar Microsoft Teams con un explorador web.

El cliente web detecta la versión del explorador al conectarse con [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) y, si se detecta una versión no admitida, se bloquea el acceso a la interfaz web y se recomienda al usuario que descargue el cliente de escritorio o la aplicación móvil.

Microsoft Teams admite los siguientes exploradores y versiones:

-   **Microsoft Edge**: 12 o posterior

-   **Internet Explorer:** 11 o posterior

-   **Chrome**: 51.0 o posterior

-   **Firefox**: 47.0 o posterior


| | |
|---------|---------|
|![](media/Get_clients_for_Microsoft_Teams_image1.png)<br></br>Importante:     |Safari no se admite todavía, pero se admitirá pronto.         |

<a name="desktop-clients"></a>Clientes de escritorio
------------------------

El cliente de escritorio de Microsoft Teams es una aplicación independiente y, actualmente, no forma parte de Office Pro Plus. Microsoft Teams está disponible para Windows (7+), en versiones de 32 y 64 bits, y para MacOs (10.10 y posteriores).

Los clientes de escritorio brindan asistencia en tiempo real para las comunicaciones (audio, vídeo y contenido compartido) para las reuniones de equipo, las llamadas grupales y las llamadas de uno a uno.

Los usuarios pueden descargar e instalar los clientes de escritorio directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos locales adecuados (no se requieren derechos de administrador para instalar el cliente de Teams en PC, pero sí son necesarios para Mac).

Los administradores de TI pueden elegir su método preferido para distribuir los archivos de instalación en las máquinas de su organización, como System Center Configuration Manager (Windows) o Casper Suite (MacOS).


| | |
|---------|---------|
|![](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>Nota    |La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.         |

#### <a name="windows"></a>Windows

La instalación de Microsoft Teams para Windows brinda instaladores que se pueden descargar en arquitecturas de 32 y 64 bits. La arquitectura debe coincidir con la del SO, que es el valor predeterminado que toma la descarga en línea.

| | |
|---------|---------|
|![](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>Nota    |La arquitectura (32 o 64 bits) de Microsoft Teams es independiente de la arquitectura de Office que esté instalada.        |

El cliente de Windows se implementa en la carpeta AppData ubicada en el perfil del usuario. La implementación en el perfil local del usuario permite instalar el cliente sin que se requieran derechos elevados. El cliente de Windows se instala en las siguientes ubicaciones:

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

Cuando los usuarios inician una llamada utilizando el cliente de Microsoft Teams, podrían recibir una advertencia con la configuración del firewall de Windows que les pide que permitan la comunicación. Es posible que se indique a los usuarios que ignoren el mensaje porque la llamada funcionará, incluso si la advertencia se descarta.

![](media/Get_clients_for_Microsoft_Teams_image3.png)

| | |
|---------|---------|
|![](media/Get_clients_for_Microsoft_Teams_image2.png)<br></br>Nota    |La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de bloqueo para los protocolos TCP y UDP.        |

#### <a name="mac"></a>Mac

Microsoft solo brinda un archivo de instalación DMG para equipos Mac OSX. Se requiere acceso de administrador para instalar el cliente de Mac. El cliente de Mac OSX se instala en la siguiente ubicación:

\~/Library/Application Support/Microsoft/Teams

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
|![](media/Get_clients_for_Microsoft_Teams_image4.png)      |Punto de decisión         |¿Hay alguna restricción que evite que los usuarios instalen el cliente de Microsoft Teams adecuado en sus dispositivos?         |
|![](media/Get_clients_for_Microsoft_Teams_image5.png)     |Siguientes pasos         |Si su organización restringe la instalación de software, asegúrese de que el proceso sea compatible con Microsoft Teams. Nota: No se requieren derechos de administrador para instalar el cliente en PC, pero sí son necesarios para Mac.         |


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

![](media/Get_clients_for_Microsoft_Teams_image6.png)
