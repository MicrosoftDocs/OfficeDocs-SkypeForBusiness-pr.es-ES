---
title: Lync Server 2013 tiempo de recuperación para la conmutación por error del grupo y la conmutación por recuperación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8692e01ed9691f69da7be78a2e0437e7829594cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Tiempo de recuperación para la conmutación por error del grupo y la conmutación por recuperación del grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-10_

Para conmutación por error y conmutación por recuperación de grupos de servidores, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 30 minutos. Este es el tiempo necesario para que tenga lugar la conmutación por error, una vez que el administrador ha determinado que se ha producido un desastre e inicia los procedimientos de conmutación por error. No incluye el tiempo necesario para que el administrador evalúe la situación y tome una decisión, como tampoco el tiempo necesario para que los usuarios vuelvan a iniciar sesión una vez que finalice la conmutación por error.

Para conmutación por error y conmutación por recuperación de grupos de servidores, el objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 30 minutos. Esto representa la medición de tiempo de los datos que se podría perder debido a un desastre, debido a la latencia de replicación del Servicio de copia de seguridad. Por ejemplo, si un grupo de servidores deja de estar disponible a las 10:00 A.M. y el RPO es de 30 minutos, los datos escritos en el grupo de entre 9:30 A.M. y 10:00 a. M. podrían no haberse replicado en el grupo de copia de seguridad y se perdería.

En todos los números de RTO y RPO de este documento se asume que los dos centros de datos se encuentran en la misma región del mundo con un transporte de alta velocidad y baja latencia entre las dos ubicaciones. Estos números se miden para un grupo con 40.000 usuarios activos de forma concurrente y 200.000 usuarios habilitados para Lync con respecto a un modelo de usuario predefinido en el que no hay un atasco en la replicación de datos. Están sujetos a cambios a partir de las pruebas de rendimiento y validación.

</div>

<span> </span>

</div>

</div>

</div>

