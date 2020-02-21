---
title: 'Lync Server 2013: Planeación de la emparejamiento de grupos de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d45434bf34cc5e7e158039851e8a7fb2cbd6e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Planeación de la emparejamiento de grupos de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Para las capacidades de recuperación ante desastres más adecuadas en Lync Server 2013, implemente pares de grupos de servidores front-end en dos sitios dispersos geográficamente. Cada sitio contiene un grupo de servidores front-end emparejado con otro grupo correspondiente en el otro sitio. Ambos sitios están activos y el servicio de copia de seguridad de Lync Server proporciona replicación de datos en tiempo real para mantener sincronizados los grupos. El servicio de copia de seguridad es una nueva característica de Lync Server 2013, diseñada para admitir la solución de recuperación ante desastres. Se instala en un grupo de servidores front-end cuando se empareja el grupo de servidores con otro grupo de servidores front-end.

Si el grupo de servidores de un sitio falla, puede realizar una conmutación por error de los usuarios de dicho grupo de servidores al grupo de servidores del otro sitio, que proporcionará servicios a todos los servidores de ambos grupos. Para la planificación de capacidad, cada grupo de servidores debe estar diseñado para gestionar las cargas de trabajo de todos los usuarios de ambos grupos en caso de desastre.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Opciones de emparejamiento de grupo admitidas y procedimientos recomendados para Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relaciones de registrador de reserva en Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Tiempo de recuperación para la conmutación por error del grupo y la conmutación por recuperación del grupo en Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Conmutación por error del almacén de administración central en Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Seguridad de datos de emparejamiento de grupo de servidores front-end en Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

