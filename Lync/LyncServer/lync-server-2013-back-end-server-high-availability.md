---
title: 'Lync Server 2013: alta disponibilidad del servidor back-end'
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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Servidor back end de alta disponibilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-08-12_

Para garantizar la alta disponibilidad de los servidores de servicios de fondo, puede usar la creación de reflejos de SQL sincrónico o la organización en clústeres SQL. Uso de una de estas soluciones opcional, pero se recomienda para mantener la continuidad empresarial de su organización. El reflejo de SQL asincrónico no es compatible con la alta disponibilidad del servidor back-end en Lync Server 2013. En el resto de este documento, el reflejo SQL significa reflejos de SQL sincrónico, a menos que se indique lo contrario de forma explícita.

Puede configurar la creación de reflejos de SQL fácilmente con el generador de topología. Los clústeres de conmutación por error de SQL deben configurarse desde SQL Server.

Si utiliza la creación de reflejos de SQL o la agrupación de SQL en un grupo que está emparejado con otro grupo de servidores front-end para la recuperación de desastres, debe usar la solución de alta disponibilidad de back-end en ambos grupos. No debe emparejar un grupo con el reflejo de SQL con un grupo mediante el uso de clústeres de SQL.

Al implementar el reflejo de SQL, todas las bases de datos de Lync Server del grupo están reflejadas, incluido el almacén central de administración, si se encuentra en este grupo, así como la base de datos de aplicación de grupo de respuesta y la base de datos de aplicación de estacionamiento de llamadas, si dichas aplicaciones se están ejecutando en el grupo.

Con la creación de reflejos de SQL, no es necesario usar almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local.

Puede optar por implementar el reflejo de SQL con un testigo o sin él. Recomendamos usar un testigo, porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador tendrá que invocar manualmente la conmutación por error. Tenga en cuenta que, incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.

Si usa un testigo, puede usar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones en las que se emplea un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end.

Para obtener más información sobre la compatibilidad con clústeres de SQL, vea [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md). Para obtener más información sobre la implementación de clústeres de SQL, consulte [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>Tiempo de recuperación para la conmutación automática por error del servidor de back-end con reflejo SQL

Para el failover de back end automático con reflejo SQL, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos. A causa de la creación de reflejos de SQL sincrónicos, no se espera la pérdida de datos durante la falla del servidor de servicios de fondo, excepto en raras ocasiones, cuando los servidores front-end y el servidor back-end se desactivan simultáneamente mientras se mueven los datos entre los servidores. El objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 5 minutos.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>Experiencia del usuario durante el error del servidor back-end con reflejo SQL

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.

Si utiliza el reflejo de SQL y tiene un testigo configurado, y se produce un error en el principal, el failover del servidor de back-end se produce de forma automática y rápida. Los usuarios activos no tendrían que notar muchas interrupciones en sus sesiones en curso.

Si no hay ningún testigo configurado, tomará algún tiempo que el administrador invoque manualmente la conmutación por error. Durante ese tiempo, los usuarios activos probablemente lo notarán. Continuarán con sus sesiones normalmente durante unos 30 minutos. Si el principal aún no se restaura o un administrador no conmuta por error a la copia de seguridad, entonces los usuarios cambian al modo de resistencia, lo que significa que no pueden realizar tareas que requieran un cambio persistente en Lync Server (como agregar un contacto).

Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

