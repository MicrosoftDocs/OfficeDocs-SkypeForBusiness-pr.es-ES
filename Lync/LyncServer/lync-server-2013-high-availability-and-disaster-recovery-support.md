---
title: 'Lync Server 2013: compatibilidad de alta disponibilidad y recuperación ante desastres'
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
ms.openlocfilehash: f8c526f83929fafe9e61078b3ddb55fa9cc9d5f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Compatibilidad de alta disponibilidad y recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

Lync Server 2013 proporciona alta disponibilidad mediante la redundancia de servidores a través de la agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor. Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores. Para obtener más información sobre los roles de servidor, consulte [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 también proporciona medidas de recuperación ante desastres habilitando el emparejamiento de grupos de servidores. Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada. Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.

Lync Server 2013 también admite alta disponibilidad del servidor back-end. Se trata de una topología opcional en la que se implementan dos servidores back-end para un grupo de servidores front-end y se configuran los reflejos de SQL Server sincrónicos para todas las bases de datos de Lync que se ejecutan en los servidores back-end.

Para obtener más información sobre el emparejamiento de grupos y la creación de reflejos del servidor back-end, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Consulta también


[Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md)  
[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

