---
title: 'Lync Server 2013: Tiempo de recuperación para la conmutación por error y por recuperación del grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a746eb96de7b1e22291cf7a147851b313469bed5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Tiempo de recuperación para la conmutación por error y por recuperación del grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-10_

Para la conmutación por error de grupo y la conmutación por recuperación del grupo, el objetivo de ingeniería del objetivo de tiempo de recuperación (RTO) es de 30 minutos. Este es el tiempo necesario para que se produzca el failover, después de que los administradores hayan determinado que se ha producido un desastre y se hayan iniciado los procedimientos de conmutación por error. No incluye el tiempo necesario para que los administradores evalúen la situación y tomen una decisión, como tampoco el tiempo necesario para que los usuarios vuelvan a iniciar sesión una vez que finalice la conmutación por error.

Para la conmutación por error de grupo y la conmutación por recuperación de grupos, el objetivo de ingeniería para objetivo de punto de recuperación (RPO) es de 30 minutos. Esto representa la medida de tiempo de los datos que se podrían perder debido al desastre, debido a la latencia de replicación del servicio de copia de seguridad. Por ejemplo, si un grupo se desconecta a las 10:00 A.M. y el RPO es de 30 minutos, los datos escritos en el grupo van de la 9:30 A.M. y 10:00 a. M es posible que no se haya replicado en el grupo de copia de seguridad y se perdería.

Para todas las cantidades de RTO y RPO de este documento se asume que los dos centros de datos se encuentran en la misma región del mundo con un transporte de alta velocidad y baja latencia entre los dos sitios. Estas cantidades se miden para un grupo de 40 000 usuarios activos simultáneamente y 200 000 usuarios habilitados para Lync con respecto a un modelo de usuario predefinido en el que no hay trabajo pendiente en la replicación de datos. Están sujetas a cambios a partir de las pruebas de rendimiento y validación.

</div>

<span> </span>

</div>

</div>

</div>

