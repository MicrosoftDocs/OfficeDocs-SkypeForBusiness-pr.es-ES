---
title: 'Lync Server 2013: Nuevas funciones de alta disponibilidad y recuperación ante desastres'
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
ms.openlocfilehash: aabac29c5e866c4bfeff8ad79d392578d52ba650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Nuevas funciones de alta disponibilidad y recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-20_

Como en Lync Server 2010, el esquema de alta disponibilidad (HA) principal para Lync Server 2013 se basa en la redundancia del servidor a través de la agrupación. Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor. Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.

Lync Server 2013 agrega nuevas medidas de recuperación ante desastres permitiéndole emparejar grupos de servidores front-end ubicados en dos centros de recursos. Si una de las agrupaciones emparejadas deja de funcionar, un administrador puede migrar por error los usuarios de ese grupo al otro grupo en el par, para proporcionar la continuación del servicio. Esta funcionalidad no requiere soluciones costosas de red o de hardware, como redes de almacenamiento o discos compartidos.

Lync Server 2013 también agrega la alta disponibilidad del servidor back end. Esta es una topología opcional en la que se implementan dos servidores de servicios de fondo para un grupo de servidores front-end y se configuran los reflejos de SQL sincrónico para todas las bases de datos de Lync que se ejecutan en los servidores back-end. Puede elegir si desea implementar un testigo para el reflejo.

<div>

## <a name="see-also"></a>Vea también


[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

