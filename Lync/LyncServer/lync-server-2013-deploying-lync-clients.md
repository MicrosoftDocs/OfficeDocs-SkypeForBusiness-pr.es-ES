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
ms.openlocfilehash: 0004e3ce0b3e00cb90fc93cee148844ebc5d4d7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Implementar clientes de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Lync 2013 presenta un enfoque diferente para la implementación de clientes. En una salida de versiones anteriores, Lync 2013 ya no tiene su propio instalador. En su lugar, Lync se incluye con el programa de instalación de Office 2013. Para implementar Lync 2013 para sus usuarios, puede usar los métodos de instalación y las herramientas de personalización de Office 2013.

  - **Office 2013 Windows Installer** es un paquete de instalación basado en Windows Installer que consta de varios archivos MSI. Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo. La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios. En los temas de esta sección se describe cómo usar y personalizar el Office 2013 Windows Installer para implementar Lync 2013.

  - **Office 2013 hacer clic y ejecutar** es un programa de instalación que transmite los archivos de instalación de Office al usuario desde el portal de Microsoft Office 365. Los administradores pueden personalizar la instalación utilizando la herramienta de implementación de Office para Click-to-Run. Como Office 2013 hacer clic y ejecutar se usa principalmente en el entorno de Microsoft Office 365, este método de instalación no se describe en detalle en esta sección. Encontrará información detallada sobre cómo usar y personalizar la instalación de hacer clic y ejecutar en la documentación del kit de recursos de Office 2013. Los administradores también pueden descargar los archivos de origen de idioma y programa de hacer clic y ejecutar de Office 2013 en una ubicación local, lo que resulta útil cuando se desea minimizar la demanda en la red o impedir que los usuarios instalen software desde Internet debido a requisitos de seguridad corporativos.

Los temas de esta sección se centran en cómo implementar clientes mediante el instalador basado en MSI de Office 2013. La referencia principal debe ser la documentación del kit de recursos de Office 2013, que describe detalladamente cómo preparar la infraestructura, personalizar la instalación e implementar Office 2013. Sin embargo, debe usar la documentación de Office junto con los temas de esta sección, que indican las consideraciones de implementación específicas de Lync 2013.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>El complemento para reunión en línea para Lync 2013, que admite la administración de reuniones desde el cliente de colaboración y mensajería de Outlook, se instala automáticamente con Lync 2013.</P>
> <LI>
> <P>El programa de instalación de Office 2013 no desinstala versiones anteriores de Lync u Office Communicator. El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Personalización de la instalación del cliente en Lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Personalización del comportamiento de Lync y la interfaz de usuario en Lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personalización del complemento para reunión en línea en Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configuración de la página de participación en la reunión en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configuración de versiones de cliente admitidas en Lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Configurar el modo de privacidad de presencia mejorada en Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

