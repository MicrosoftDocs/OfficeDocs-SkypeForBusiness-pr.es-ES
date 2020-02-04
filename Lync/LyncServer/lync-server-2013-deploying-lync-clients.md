---
title: 'Lync Server 2013: implementación de clientes de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Implementar clientes de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Lync 2013 presenta un enfoque diferente para la implementación de clientes. En una salida de versiones anteriores, Lync 2013 ya no tiene su propio instalador. En su lugar, Lync se incluye con el programa de instalación de Office 2013. Para implementar Lync 2013 para los usuarios, puede usar los métodos de instalación y las herramientas de personalización de Office 2013.

  - **Office 2013 Windows Installer** es un paquete de instalación basado en Windows Installer que consta de varios archivos MSI. Un paquete MSI principal independiente del idioma se combina con uno o más paquetes específicos del idioma para formar un producto completo. La instalación combina los paquetes individuales y realiza tareas de mantenimiento y personalización durante y después de finalizar la instalación de Office en los equipos de los usuarios. En los temas de esta sección se describe cómo usar y personalizar Office 2013 Windows Installer para implementar Lync 2013.

  - **Office 2013 hacer clic y ejecutar** es un programa de instalación que transmite los archivos de instalación de Office al usuario desde el portal de Microsoft Office 365. Los administradores pueden personalizar la instalación con la Herramienta de implementación de Office para Hacer clic y ejecutar. Dado que Office 2013 hacer clic y ejecutar se usa principalmente en el entorno de Microsoft Office 365, este método de instalación no se describe detalladamente en esta sección. Encontrará información detallada sobre el uso y la personalización de la instalación de hacer clic y ejecutar en la documentación del kit de recursos de Office 2013. Los administradores también pueden descargar el programa de Office 2013 hacer clic y ejecutar y los archivos de origen del idioma a una ubicación local, lo cual es útil cuando desea minimizar la demanda de la red o impedir que los usuarios instalen software de Internet debido a requisitos de seguridad corporativas.

Los temas de esta sección se centran en cómo implementar clientes con el instalador de Office 2013 basado en MSI. La referencia principal debe ser la documentación del kit de recursos de Office 2013, que describe detalladamente cómo preparar su infraestructura, personalizar la instalación e implementar Office 2013. Sin embargo, debería usar la documentación de Office junto con los temas de esta sección, que destacan las consideraciones de implementación específicas de Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>El complemento de reunión en línea para Lync 2013, que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook, se instala automáticamente con Lync 2013.</P>
> <LI>
> <P>El programa de instalación de Office 2013 no desinstala versiones anteriores de Lync u Office Communicator. El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Personalizar la instalación del cliente en Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personalizar el comportamiento de Lync y la interfaz de usuario en Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personalizar el complemento de reunión en línea en Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configuración de la página de participación en reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configuración de las versiones de cliente compatibles en Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configuración del modo de privacidad de presencia mejorada en Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

