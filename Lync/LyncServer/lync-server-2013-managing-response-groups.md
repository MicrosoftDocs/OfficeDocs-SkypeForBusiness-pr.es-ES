---
title: 'Lync Server 2013: administración de grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee9ee5808263f1e10489a09a711c60f93a13429d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a>Administración de grupos de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2018-02-01_

Los grupos de respuesta son una característica para la administración de llamadas que habilitan poner en cola las llamadas que se realizan a un área específica, como el servicio de asistencia técnica, y de ahí se enrutan a un grupo designado de personas, que se denominan *agentes*.

Para administrar grupos de respuesta, deberá configurar grupos de agentes, colas y flujos de trabajo, que definen lo que ocurre con una llamada desde el momento que se realiza hasta que es atendida por un agente.

<div>


> [!NOTE]  
> Si tiene más de 300 flujos de trabajo en un único grupo de servidores de la implementación del grupo de respuesta, es mejor usar los cmdlets del shell de administración de Lync Server para crear los flujos de trabajo. Si usa la herramienta de configuración de grupos de respuesta para crear flujos de trabajo para un grupo de servidores con más de 300 flujos de trabajo, la página web tardará mucho tiempo en cargarse. El número de agentes que se asocian de forma indirecta con flujos de trabajo a través de las colas también tiene un efecto proporcional en la carga de la página.



</div>

Los temas de esta sección proporcionan procedimientos paso a paso para las tareas que puede realizar para personalizar y mantener la aplicación de grupo de respuesta en su implementación

<div>

## <a name="in-this-section"></a>En esta sección

  - [Administración de grupos de agentes de grupo de respuesta en Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)

  - [Administración de colas de grupo de respuesta en Lync Server 2013](lync-server-2013-managing-response-group-queues.md)

  - [Administración de flujos de trabajo de grupos de respuesta en Lync Server 2013](lync-server-2013-managing-response-group-workflows.md)

  - [Administración de la configuración del grupo de respuesta de nivel de aplicación en Lync Server 2013](lync-server-2013-managing-application-level-response-group-settings.md)

  - [Mover grupos de respuesta a un nuevo grupo de servidores en Lync Server 2013](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [Administración de grupos de respuesta en Lync Server 2013 durante un desastre](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

