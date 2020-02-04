---
title: Usar un grupo de servidores de chat persistente estirado para la recuperación ante desastres
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d5091623e381191d23ae0c8a62835577a1f66a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Usar un grupo de servidores de chat persistente estirado para la recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

La solución de recuperación ante desastres para el servidor de chat persistente se crea en un grupo de servidores de chat persistente ampliado. Esto es similar a la resistencia de sitios metropolitana en Lync Server 2010; sin embargo, no hay ningún requisito para una red de área local virtual extendida (VLAN). Al estirar el grupo de servidores de chat persistente, se configura esencialmente un grupo en la topología de forma lógica, pero los servidores del grupo se colocan físicamente en dos centros de datos diferentes. Configure la creación de reflejos de SQL Server para la base de datos de la misma manera e implemente la base de datos y el reflejo en el mismo centro de datos. Tiene que configurar una base de datos de copia de seguridad en el centro de datos secundario (con un reflejo opcional para proporcionar alta disponibilidad durante la recuperación ante desastres). Esta es la base de datos de copia de seguridad que se usa para la conmutación por error durante la recuperación ante desastres.

Para obtener más información sobre cómo configurar el reflejo de SQL Server para una alta disponibilidad, consulte [reflejos de SQL Server en Lync server 2013](lync-server-2013-sql-server-mirroring.md). Para obtener detalles sobre el failover de la base de datos para recuperación ante desastres, consulte [configurar el trasvase de registros de SQL Server en Lync server 2013 para la base de datos principal del servidor de chat persistente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) y [configurar el trasvase de registros de SQL Server entre el reflejo principal y la base de datos secundaria de trasvase de registros en Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).

</div>

<span> </span>

</div>

</div>

</div>

