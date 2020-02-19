---
title: 'Lync Server 2013: componentes usados por el grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6cf167917dc7d72484eb0fa833a688b0b4e4b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Componentes usados por el grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

La aplicación de grupo de respuesta se habilita automáticamente al implementar la telefonía IP empresarial. En esta sección se describen los componentes que admiten la aplicación grupo de respuesta.

<div>

## <a name="response-group-components"></a>Componentes del grupo de respuesta

Los siguientes componentes de Microsoft Lync Server 2013 admiten la aplicación grupo de respuesta:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como el grupo de respuesta. El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en cada servidor Standard Edition.

  - **Aplicación de grupo de respuesta**   la aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación. Se incluye automáticamente al implementar el grupo de respuesta. La aplicación de grupo de respuesta enruta y pone en cola las llamadas entrantes a grupos de agentes.

  - **Paquete de idioma**   se requiere un paquete de idioma para admitir el texto a voz y el reconocimiento de voz. Estas tecnologías de voz se usan cuando se configuran los mensajes, como el mensaje de bienvenida y otros mensajes, y se responde a las preguntas y respuestas interactivas de respuesta de voz (IVR). De forma predeterminada, los 26 paquetes de idioma admitidos se instalan al implementar Lync Server 2013.

  - **Archivos de audio**   los archivos de audio se usan para los mensajes y la música en espera.

  - ****   El grupo de respuesta del almacén de archivos usa el almacén de archivos para almacenar los archivos de audio. Varios grupos de grupos de respuesta pueden usar la misma instancia del almacén de archivos.

  - **Herramienta de configuración**   de grupos de respuesta la herramienta de configuración de grupos de respuesta es una herramienta basada en Web que se usa para crear y configurar grupos de respuesta. La herramienta de configuración de grupos de respuesta se incluye al instalar los servicios Web.

  - **Panel de control de Microsoft Lync Server 2013**   puede usar el panel de control de Lync Server para instalar y configurar grupos de agentes y colas para grupos de respuesta.

  - **Shell de administración de Lync Server**   toda la configuración del grupo de respuesta se puede configurar mediante los cmdlets del shell de administración de Lync Server.

  - **Microsoft Lync 2013**   : agentes formales (agentes que son necesarios para iniciar sesión en el grupo antes de que puedan aceptar llamadas para el grupo) Use Lync 2013 para iniciar sesión en el grupo y cerrarla. Si un grupo de agentes está configurado para los agentes formales, los agentes hacen clic en un elemento de menú en Lync 2013 para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.

  - **Servicios web**servicios web es necesario para la herramienta de configuración de grupos de respuesta, la consola de inicio y de cierre de sesión de los agentes, el panel de control de Lync Server y el servicio Web de cliente del grupo de respuesta.   

  - ****   La aplicación grupo de respuesta del servicio Web cliente de grupo de respuesta proporciona un servicio Web de cliente, que puede ser utilizado por aplicaciones de terceros para recuperar información sobre agentes, pertenencia a grupos de agentes, estado de inicio de sesión de agentes, estado de llamadas para grupos y grupos que admiten llamadas anónimas. Lync 2013 y el operador de Lync 2010 usan el servicio Web cliente de grupo de respuesta para recuperar la lista de grupos de respuesta que los agentes pueden usar para realizar llamadas anónimas. El servicio web de cliente se incluye al instalar los servicios web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

