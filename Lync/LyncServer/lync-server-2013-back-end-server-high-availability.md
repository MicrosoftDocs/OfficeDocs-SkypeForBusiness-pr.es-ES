---
title: 'Lync Server 2013: alta disponibilidad del servidor back-end'
description: 'Lync Server 2013: alta disponibilidad del servidor back-end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805cbf96e107329aa5c374cfa1e2d01234d360a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543776"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Alta disponibilidad del servidor back-end en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-08-12_

Para garantizar la alta disponibilidad de los servidores back-end, puede usar la creación de reflejos de SQL sincrónicos o clústeres SQL. El uso de una de estas soluciones es opcional, pero se recomienda para mantener la continuidad empresarial de la organización. La creación de reflejo de SQL asincrónico no es compatible con alta disponibilidad del servidor back-end en Lync Server 2013. En lo que resta de este documento, la creación de reflejos SQL significa la creación de reflejos SQL sincrónica, salvo que se aclare explícitamente lo contrario.

Puede configurar fácilmente la creación de reflejos de SQL con el generador de topologías. Para los clústeres de conmutación por error de SQL, debe usar SQL Server para la instalación.

Si usa la creación de reflejo de SQL o un clúster de SQL en un grupo que está emparejado con otro grupo de servidores front-end para la recuperación ante desastres, debe usar la solución de alta disponibilidad back-end en ambos grupos. No debe emparejar un grupo con la creación de reflejos de SQL con un grupo de servidores mediante clústeres de SQL.

Al implementar la creación de reflejos de SQL, todas las bases de datos de Lync Server del grupo están reflejadas, incluido el almacén de administración central, si se encuentra en este grupo, así como la base de datos de aplicación de grupo de respuesta y la base de datos de aplicación de estacionamiento de llamadas, si esas aplicaciones se ejecutan en el grupo.

Con la creación de reflejos SQL, no necesita utilizar almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local.

Puede elegir implementar una creación de reflejos SQL con o sin un testigo. Recomendamos utilizar un testigo porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador debe invocar manualmente la conmutación por error. Tenga en cuenta que incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.

Si utiliza un testigo, puede utilizar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones que utilizan un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end.

Para obtener más información acerca de la compatibilidad con clústeres de SQL, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md). Para obtener más información sobre la implementación de clústeres de SQL, vea [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Tiempo de recuperación para la conmutación por error del servidor back-end automático con reflejo SQL

Para la conmutación por error de back-end automática con creación de reflejos de SQL, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos. Debido a la creación de reflejos SQL sincrónica, no prevemos pérdida de datos durante los errores en el servidor back-end excepto en raras ocasiones, cuando tanto los servidores front-end y los servidores back-end dejan de funcionar simultáneamente mientras se mueven datos entre los servidores. El destino de ingeniería para objetivo de punto de recuperación (RPO) es de 5 minutos.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Experiencia del usuario durante el error del servidor back-end con la creación de reflejo de SQL

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.

Si usa la creación de reflejos de SQL y ha configurado un testigo, y se produce un error en la entidad de seguridad, el failover del servidor back-end se produce de forma automática y rápida. Los usuarios activos no deberían notar muchas interrupciones en sus sesiones en curso.

Si no hay ningún testigo configurado, llevará algún tiempo hasta que el administrador pueda invocar manualmente la conmutación por error. Durante este tiempo, es posible que los usuarios activos se vean afectados. Continuarán sus sesiones como normales durante unos 30 minutos. Si el principal todavía no se ha restaurado o un administrador no ha conmutado por error a la copia de seguridad, entonces los usuarios cambian al modo de resistencia, lo que significa que no pueden realizar tareas que requieran un cambio persistente en Lync Server (como agregar un contacto).

Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

