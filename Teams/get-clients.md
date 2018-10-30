---
title: Obtener clientes para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: vichau, majafry
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar los distintos clientes disponibles para Microsoft Teams, que incluyen web, escritorio (Windows y Mac) y móvil (Android, iOS y Windows Phone).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1eeb32f86f678672a14d42b241e56eb9ab92b02
ms.sourcegitcommit: 9138325ba2652a9ee3602d259de811082080e358
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842087"
---
<a name="get-clients-for-microsoft-teams"></a>Obtener clientes para Microsoft Teams 
===========================

Microsoft Teams tiene los clientes disponibles para escritorio web (Windows y Mac) y para dispositivos móviles (Android, iOS y Windows Phone). Todos estos clientes requieren una conexión a Internet activa y no admiten el modo sin conexión.

> [!NOTE]
> 29 de noviembre eficaz de 2018, ya no podrá usar el Teams Microsoft para la aplicación de Windows 10 S (vista previa), esté disponible de Microsoft Store. Se recomienda que use una de las aplicaciones de los equipos que se describe a continuación en este artículo después de 29 de noviembre.

<a name="desktop-client"></a>Cliente de escritorio
--------------

> [!Tip]
> Vea la sesión para conocer las ventajas del escritorio de Windows de cliente, cómo planear para él y cómo implementarlo siguiente: [Los equipos cliente de escritorio de Windows](https://aka.ms/teams-clients)

El cliente de escritorio de Microsoft Teams es una aplicación independiente y actualmente no forma parte de Office 365 ProPlus. Los equipos está disponible para Windows (7 +), versiones de 32 bits y 64 bits y Mac OS (10.10 +). En Windows, los equipos requiere .NET Framework 4.5 o posterior; el programa de instalación de los equipos ofrecerá a instalarlo automáticamente si no lo tiene. 

Los clientes de escritorio proporcionan compatibilidad con las comunicaciones en tiempo real (audio, vídeo y contenido de uso compartido) para las reuniones de equipo, grupo realiza la llamada y privada proporcionó las llamadas.

Los clientes de escritorio pueden ser descargados e instalados por los usuarios finales directamente desde [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) si tienen los permisos adecuados locales (derechos de administrador no son necesarios para instalar el cliente de los equipos en un PC pero se requieren en un Mac).

Los administradores de TI pueden elegir su método preferido para distribuir los archivos de instalación en los equipos de su organización, como System Center Configuration Manager (Windows) o Jamf Pro (Mac OS). Para obtener el paquete de MSI para la distribución de Windows, vea [instalar los equipos de Microsoft con MSI](msi-deployment.md).

> [!NOTE]
> La distribución del cliente a través de estos mecanismos es solo para la instalación inicial de los clientes de Microsoft Teams y no para futuras actualizaciones.

### <a name="windows"></a>Windows

La instalación de Microsoft Teams para Windows proporciona a instaladores que se pueden descargar en la arquitectura de 32 bits y 64 bits.

> [!NOTE]
> La arquitectura (32 bits frente a 64 bits) de Microsoft Teams es independiente de la arquitectura de Windows y Office que está instalado.

El cliente de Windows se implementa en la carpeta AppData que se encuentra en el perfil del usuario. Implementar en el perfil del usuario local permite que el cliente esté instalado sin necesidad de derechos con privilegios elevados. El cliente de Windows aprovecha las siguientes ubicaciones:

- % LocalAppData %\\Microsoft\\los equipos

- % LocalAppData %\\Microsoft\\TeamsMeetingsAddin

- % AppData %\\Microsoft\\los equipos

- % LocalAppData %\\SquirrelTemp

Cuando los usuarios inician una llamada mediante el cliente de Microsoft Teams por primera vez, es posible que observe el una advertencia con la configuración de firewall de Windows que se pregunta a los usuarios permitir la comunicación. Los usuarios que se le indique para omitir este mensaje debido a que funcione la llamada, incluso cuando se descarta la advertencia.

![Captura de pantalla de un cuadro de diálogo Alerta de seguridad de Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configuración del firewall de Windows se modificará incluso si el mensaje se descarta seleccionando "Cancelar". Se crearán dos reglas de entrada para teams.exe con la acción de bloqueo para los protocolos TCP y UDP.

### <a name="mac"></a>Mac

Los usuarios de Mac pueden instalar los equipos mediante un archivo de instalación del paquete para Mac OS equipos. Se requiere acceso de administrador para instalar el cliente de Mac. El cliente de Mac OS está instalado en la carpeta /Applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Instalación de los equipos mediante el archivo de paquete

1. Desde la [página de descarga de los equipos](https://teams.microsoft.com/downloads), en **Mac**, haga clic en **Descargar**.
2. Haga doble clic en el archivo de paquete.
3. Siga el Asistente para instalación para completar la instalación.
4. Los equipos se instalará en la carpeta /Applications. Se trata de una instalación de todo el equipo.

> [!NOTE]
> Durante la instalación, el paquete solicitará las credenciales de administrador. El usuario debe escribir las credenciales de administrador, independientemente de si el usuario es un administrador.

Si un usuario tiene una instalación de dmg para de los equipos y desea reemplazar con la instalación del paquete actualmente, el usuario debe:

1. Salga de la aplicación de los equipos.
2. Desinstalación de la aplicación de los equipos.
3. Instalar el archivo de paquete.

Los administradores de TI pueden utilizar implementación administrada de los equipos para distribuir los archivos de instalación a todos los equipos Mac en su organización, como Jamf Pro.

> [!NOTE]
> Si experimenta problemas al instalar el paquete, háganoslo saber. En la sección de **comentarios** al final de este artículo, haga clic en **comentarios sobre el producto**.

<a name="web-client"></a>Cliente web 
----------

El cliente web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) es un cliente completo, funcional que se puede usar desde una variedad de exploradores. El cliente web admite llamadas y reuniones mediante webRTC, por lo que hay no complemento o descargar necesarios para ejecutar los equipos en un explorador web. El explorador debe configurarse para permitir que las cookies de terceros. 

[!INCLUDE [browser-support](includes/browser-support.md)]

El cliente web realiza la detección de versión de explorador al conectarse a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Si se detecta una versión de explorador incompatible, se bloquee el acceso a la interfaz web y se recomienda que el usuario descargue el cliente de escritorio o una aplicación móvil.

<a name="mobile-clients"></a>Clientes móviles
--------------

Las aplicaciones móviles de Microsoft Teams están disponibles para Android y iOS y están diseñadas para usuarios de en vaya que participan en conversaciones de chat y permitir que las llamadas de audio de punto a punto. Para las aplicaciones móviles, vaya a los almacenes móviles relevantes Google reproducir y Apple App Store. Se ha retirado la aplicación de Windows Phone 20 de julio de 2018 consulte [aquí](https://support.microsoft.com/en-us/help/4230833/windows-phone-app-for-microsoft-teams-is-retiring) para obtener más información.

Las siguientes son las plataformas móviles admitidas para Microsoft Teams:

-   **Android** 4.4 o posterior

-   **iOS**: 10.0 o posterior

> [!NOTE]
> La versión móvil debe estar disponible al público en orden para los equipos para que funcione como se esperaba.

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
