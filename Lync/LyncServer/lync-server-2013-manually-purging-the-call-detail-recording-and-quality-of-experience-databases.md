---
title: Purgado manual del registro detallado de llamadas y de las bases de datos de calidad de la experiencia
description: Purgar manualmente el registro detallado de llamadas y las bases de datos de calidad de la experiencia.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7903431d28bf1a829991ce35c2ee7351168b4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556566"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Purgado manual del registro detallado de llamadas y de las bases de datos de calidad de la experiencia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-07_

Los administradores pueden configurar el registro de detalles de llamadas (CDR) o las bases de datos de calidad de la experiencia (QoE) para depurar automáticamente los registros antiguos de la base de datos; Esto ocurre si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si hay registros que han estado en la base de datos durante más tiempo que la cantidad especificada. Por ejemplo, cada día a la 1:00 AM los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.

Además de esta purga automática, se han agregado dos cmdlets nuevos (Invoke-CsCdrDatabasePurge y Invoke-CsQoEDatbasePurge) a Microsoft Lync Server 2013; Estos cmdlets permiten a los administradores depurar manualmente los registros de las bases de datos de CDR y QoE en cualquier momento. Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos CDR puede utilizar un comando similar al siguiente:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

En el comando anterior tanto los registros de detalles de llamadas como los registros de datos de diagnóstico que tengan más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com. (Los registros de detalles de llamadas son informes de usuario/sesión. Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente como Lync 2013).

Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge debe incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays. Sin embargo, no es necesario establecer estos parámetros en el mismo valor. Por ejemplo, es posible depurar registros de detalles de llamadas con más de 10 días de antigüedad y sin embargo, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos. Para ello, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0. Por ejemplo:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que deba depurarse:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Debe escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:

    -Confirm:$False

Por ejemplo:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.

Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

