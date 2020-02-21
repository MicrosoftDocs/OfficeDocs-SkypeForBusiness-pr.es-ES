---
title: 'Lync Server 2013: nuevas características de recuperación ante desastres y alta disponibilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7845f919f04985e67d6825b8722904a9158606b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Nuevas características de recuperación ante desastres y alta disponibilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-20_

Como en Lync Server 2010, el esquema principal de alta disponibilidad (HA) para Lync Server 2013 se basa en la redundancia de servidores a través de la agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor. Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.

Lync Server 2013 agrega nuevas medidas de recuperación ante desastres al permitirle emparejar grupos de servidores front-end ubicados en dos centros de recursos. Si uno de los grupos emparejadas se desactiva, un administrador puede conmutar por error los usuarios de un grupo a otro grupo de la pareja, para proporcionar continuidad del servicio. Estas funciones no necesitan una red o soluciones de hardware caras como redes de almacenamiento o discos compartidos.

Lync Server 2013 también agrega alta disponibilidad del servidor back-end. Se trata de una topología opcional en la que se implementan dos servidores back-end para un grupo de servidores front-end y se configuran los reflejos de SQL sincrónicos para todas las bases de datos de Lync que se ejecutan en los servidores back-end. Puede elegir si desea implementar un testigo para el reflejo.

<div>

## <a name="see-also"></a>Consulta también


[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

