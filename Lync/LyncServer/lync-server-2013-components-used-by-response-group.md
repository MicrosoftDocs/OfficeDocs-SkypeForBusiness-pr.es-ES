---
title: 'Lync Server 2013: Componentes usados por el grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f52ceb18c355f6d867b5b3b4485434df83683d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Componentes usados por el grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

La aplicación de grupo de respuesta se habilita automáticamente al implementar la telefonía IP empresarial. En esta sección se describen los componentes que admiten la aplicación de grupo de respuesta.

<div>

## <a name="response-group-components"></a>Componentes de grupo de respuesta

Los siguientes componentes de Microsoft Lync Server 2013 son compatibles con la aplicación de grupo de respuesta:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas, como grupo de respuesta. El servicio de aplicación se instala automáticamente en todos los servidores front-end de un grupo de servidores front-end y en todos los servidores Standard Edition.

  - **Aplicación de grupo de respuesta**   la aplicación de grupo de respuesta es una de las aplicaciones de comunicaciones unificadas que se hospedan en el servicio de aplicación. Se incluye automáticamente al implementar el grupo de respuesta. La aplicación de grupo de respuesta enruta y pone en cola las llamadas entrantes a grupos de agentes.

  - **Paquete de idioma**   se necesita un paquete de idioma para admitir texto a voz y reconocimiento de voz. Estas tecnologías de voz se usan al configurar mensajes, como el mensaje de bienvenida y otras solicitudes de respuesta de voz interactiva (IVR) y las respuestas. De forma predeterminada, los 26 paquetes de idioma admitidos se instalan al implementar Lync Server 2013.

  - **Archivos de audio**   los archivos de audio se usan para los mensajes y la música en espera.

  - ****   El grupo de respuesta del almacén de archivos usa el almacén de archivos para almacenar archivos de audio. Varios grupos de grupos de respuesta pueden usar la misma instancia del almacén de archivos.

  - **Herramienta de configuración de grupo**   de respuesta la herramienta Configuración de grupo de respuesta es una herramienta basada en Web que se usa para crear y configurar grupos de respuesta. La herramienta de configuración de grupos de respuesta se incluye al instalar servicios Web.

  - **Panel de control de Microsoft Lync Server 2013**   puede usar el panel de control de Lync Server para configurar y configurar colas y grupos de agentes para grupos de respuesta.

  - **Shell de administración de Lync Server**   todas las opciones del grupo de respuesta se pueden configurar mediante los cmdlets del shell de administración de Lync Server.

  - **Agentes formales Microsoft Lync 2013**   (agentes que deben iniciar sesión en el grupo antes de que puedan aceptar llamadas para el grupo) usar Lync 2013 para iniciar y cerrar sesión en el grupo. Si un grupo de agentes está configurado para agentes formales, los agentes deben hacer clic en un elemento de menú de Lync 2013 para abrir Internet Explorer y mostrar una consola de página web para iniciar y cerrar sesión en el grupo.

  - ****   Los servicios Web de servicios web son necesarios para la herramienta de configuración de grupos de respuesta, la consola de inicio y cierre de sesión de los agentes, el panel de control de Lync Server y el servicio Web de cliente de grupo de respuesta.

  - ****   Aplicación de grupo de respuesta de servicio Web cliente de grupo de respuesta proporciona un servicio Web cliente, que puede ser usado por aplicaciones de terceros para recuperar información sobre agentes, la pertenencia a grupos del agente, el estado de inicio de sesión del agente, el estado de la llamada de los grupos, y los grupos que admiten llamadas anónimas. El operador de Lync 2013 y Lync 2010 use el servicio Web de cliente de grupo de respuesta para recuperar la lista de grupos de respuesta que los agentes pueden usar para realizar llamadas anónimas. El servicio Web de cliente se incluye cuando se instalan los servicios Web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

