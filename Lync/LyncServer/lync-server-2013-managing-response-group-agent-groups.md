---
title: 'Lync Server 2013: administración de grupos de agentes de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Administrar grupos de agentes de grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Un grupo de agentes consta de un grupo de personas que están designadas para responder llamadas a un grupo de respuesta. Al crear un grupo de agentes, seleccione los agentes que están asignados al grupo y especifique la configuración adicional del grupo, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.

<div>


> [!NOTE]  
> Los usuarios deben estar habilitados para telefonía IP empresarial antes de que pueda agregarlos a grupos de agentes. Para obtener más información sobre cómo habilitar un usuario para telefonía IP empresarial, consulte <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar usuarios para telefonía IP empresarial en Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Solo los usuarios locales pueden ser agentes. Si un agente se mueve de local a conectado, las llamadas a grupos de respuesta no se dirigirán a ese agente.



</div>

Un agente que debe iniciar y cerrar sesión en el grupo, lo cual difiere de la sesión o de la salida de Lync Server, se denomina *agente formal*. Los agentes formales deben iniciar sesión en el grupo antes de que puedan recibir llamadas dirigidas al grupo. Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada. Agentes formales inicie y cierre sesión en sus grupos haciendo clic en un elemento de menú de Lync 2013 para abrir el explorador de Internet de Windows Internet Explorer y mostrar una consola de página web.

Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de  *agente informal*. Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Lync Server y no pueden cerrar sesión en el grupo.

<div>


> [!IMPORTANT]  
> Cuando asigne usuarios como agentes de grupo de respuesta, indíqueles que, si tienen habilitado el modo de privacidad, deberán buscar contactos de "Observador de presencia de RGS" y agregarlos a su lista de contactos. Los agentes que tengan el modo de privacidad habilitado, pero que no tengan "Observador de presencia RGS" en su lista de contactos no podrán recibir llamadas en el grupo de respuesta. Los agentes que no tengan habilitado el modo de privacidad, no se verán afectados.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Crear o modificar un grupo de agentes en Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Eliminar un grupo de agentes en Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

