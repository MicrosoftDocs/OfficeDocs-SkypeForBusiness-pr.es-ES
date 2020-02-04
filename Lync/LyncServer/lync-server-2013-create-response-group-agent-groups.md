---
title: 'Lync Server 2013: Crear grupos de agentes de grupos de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>Crear grupos de agentes de grupos de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.

Un agente que debe iniciar y cerrar sesión en el grupo, lo cual difiere de la sesión o de la salida de Lync Server, se denomina *agente formal*. Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo. Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada. Agentes formales inicie y cierre sesión en sus grupos haciendo clic en un elemento de menú de Lync 2013 para abrir el explorador de Internet de Windows Internet Explorer y mostrar una consola de página web.

Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de  *agente informal*. Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Lync Server y no pueden cerrar sesión en el grupo.

<div>


> [!NOTE]  
> Solo los usuarios locales pueden ser agentes. Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

[Crear o modificar un grupo de agentes en Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

