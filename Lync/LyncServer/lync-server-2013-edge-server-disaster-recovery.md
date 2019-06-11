---
title: 'Lync Server 2013: Recuperación ante desastres del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Recuperación ante desastres del servidor perimetral en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-12_

Al igual que con otros roles de servidor, la mejor manera de proporcionar alta disponibilidad para los servidores perimetrales es implementar varios servidores perimetrales en grupos en cada sitio. Si un servidor perimetral deja de funcionar, los otros servidores del grupo seguirán proporcionando servicios de extremo.

Para habilitar los procedimientos de recuperación ante desastres, debe disponer de grupos de servidores perimetrales separados en sitios diferentes. No es necesario emparejar de manera explícita las agrupaciones periféricas como se hace con los grupos de aplicaciones para el usuario, pero tener varios grupos de límites aún proporciona la disponibilidad para funcionar si se produce la baja de un grupo de bordes completo. En las siguientes secciones se proporcionan detalles sobre la recuperación de desastres para las distintas funciones de los servidores perimetrales.

<div>

## <a name="remote-access"></a>Acceso remoto

Si tiene varios sitios, cada uno con un grupo de servidores perimetrales y se produce un error en una agrupación perimetral completa, los servicios de acceso remoto seguirán funcionando sin necesidad de acción de administrador. Al crear grupos de borde en diferentes sitios, no se puede usar el mismo FQDN. Cada grupo perimetral debe tener FQDN únicos (internos y externos). Los conjuntos de bordes no usan reglas de publicación de proxy invertida para hablar con los servidores de aplicaciones para el usuario. La conmutación por error automática se produce cuando el cliente vuelve a consultar los registros del servicio DNS de acceso remoto y los usuarios remotos se enrutan a los servidores perimetrales de otro sitio. El cliente intenta cada FQDN de borde externo según la prioridad de los registros SRV de DNS.

<div>


> [!NOTE]  
> Para que la conmutación por error funcione sin problemas, asegúrese de que el Firewall permite que los servidores front-end de cada grupo se comuniquen con todos los servidores perimetrales.



</div>

</div>

<div>

## <a name="federation"></a>Federación

Para las relaciones de Federación con otras organizaciones que ejecutan Lync Server, las solicitudes de Federación entrante seguirán funcionando siempre y cuando tenga soluciones como el DNS geográfica GTM. Es importante comprender que la conmutación por error de la Federación no proporciona la conmutación por error con prioridad en los registros SRV. Una solución proporcionada anteriormente puede ayudarle a proporcionar capacidades de recuperación ante desastres para la Federación entrante.

La Federación saliente siempre se configura a través de un grupo perimetral publicado o un servidor perimetral en la organización. Si este grupo de límites ha desaparecido, debe usar el generador de topología para cambiar la ruta de Federación saliente para usar un grupo de límites que aún se esté ejecutando. Para obtener más información, consulte [conmutación por error del grupo perimetral usado para la Federación de Lync Server en Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Federación XMPP

Para la Federación XMPP, se producirá un error en el tráfico entrante y saliente si el grupo perimetral designado como la puerta de enlace de Federación XMPP deja de funcionar. Para hacer que la Federación XMPP vuelva a funcionar, debe cambiar la Federación de XMPP para usar un grupo de borde diferente. Para obtener más información, consulte [conmutación por error del grupo perimetral usado para la Federación XMPP en Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>El grupo Edge falla pero el grupo de servidores front-end aún se está ejecutando

Si se produce un error en un grupo de límites del sitio, pero el grupo de servidores front-end de ese sitio aún se está ejecutando, tendrá que cambiar el grupo de servidores front-end para usar un grupo de borde diferente en un sitio diferente mientras el primer grupo perimetral esté inactivo. Para obtener más información, vea [cambiar el grupo perimetral asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

