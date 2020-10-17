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
ms.openlocfilehash: 11e0c0c022b1925831737d70a10c2a193b9732bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497957"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Administración de grupos de agentes de grupo de respuesta en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Un grupo de agentes consiste en un grupo de personas designado para responder llamadas de un grupo de respuesta. Cuando se crea un grupo de agentes, se seleccionan los agentes que se asignan al grupo y se especifica la configuración de grupo adicional, como el método de enrutamiento y si un agente puede iniciar y cerrar sesión en el grupo.

<div>


> [!NOTE]  
> Los usuarios deben estar habilitados para telefonía IP empresarial para poder agregarlos a los grupos de agentes. Para obtener más información sobre cómo habilitar a un usuario para la telefonía IP empresarial, consulte <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar usuarios para telefonía IP empresarial en Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Solo los usuarios locales pueden ser agentes. Si un agente deja de ser local para estar en línea, las llamadas al grupo de respuesta no se enrutarán a dicho agente.



</div>

Un agente que debe iniciar y cerrar sesión en el grupo, que es distinto de iniciar o cerrar sesión en Lync Server, se denomina *agente formal*. Los agentes formales deben iniciar sesión en el grupo para poder recibir llamadas enrutadas al grupo. Esto puede resultar útil para los agentes que atienden llamadas del grupo a media jornada. Los agentes formales iniciar y cerrar sesión en sus grupos haciendo clic en un elemento de menú en Lync 2013 para abrir el explorador de Internet Internet Explorer y mostrar una consola de página web.

Un agente que no inicia ni cierra sesión en el grupo recibe el nombre de *agente informal*. Los agentes informales inician sesión automáticamente en el grupo cuando inician sesión en Lync Server y no pueden cerrar sesión en el grupo.

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

