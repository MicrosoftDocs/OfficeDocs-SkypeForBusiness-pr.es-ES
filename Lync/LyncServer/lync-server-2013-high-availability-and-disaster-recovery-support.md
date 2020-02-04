---
title: 'Lync Server 2013: Compatibilidad entre la alta disponibilidad y la recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Compatibilidad entre la alta disponibilidad y la recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

Lync Server 2013 ofrece alta disponibilidad por redundancia de servidores a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores. Para obtener más información sobre los roles de servidor, vea [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 también proporciona medidas de recuperación ante desastres mediante la habilitación del emparejamiento de grupos. Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada. Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.

Lync Server 2013 también admite la alta disponibilidad del servidor back-end. Esta es una topología opcional en la que implementa dos servidores back-end para un grupo de servidores front-end y configura el reflejo sincrónico de SQL Server para todas las bases de datos de Lync que se ejecutan en los servidores back-end.

Para obtener más información sobre el emparejamiento de grupos y el reflejo de servidor, consulte [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Vea también


[Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md)  
[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

