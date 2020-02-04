---
title: Purgado manual de las bases de datos de grabación de detalles de llamadas y calidad de la experiencia
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
ms.openlocfilehash: 50d7de2fdb63b9152731214edeff3bf9c03aa634
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Purgar manualmente las bases de datos de grabación de detalles de llamadas y de calidad de la experiencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-07_

Los administradores pueden configurar las bases de datos de Registro detallado de llamadas (CDR) o de Calidad de experiencia (QoE) para depurar automáticamente registros antiguos de la base de datos; esto sucede si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si existe algún registro que haya estado en la base de datos durante más tiempo del especificado. Por ejemplo, cada día a la 01:00 los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.

Además de esta purga automática, se han agregado dos cmdlets nuevos (Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge) a Microsoft Lync Server 2013. Estos cmdlets permiten a los administradores purgar manualmente registros de las bases de datos de CDR y QoE en cualquier momento. Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos de CDR puede utilizar un comando similar al siguiente:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

En el comando anterior, los registros de detalles de la llamada y los registros de datos de diagnóstico de más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com. (Los registros de detalles de llamadas son informes de usuario o sesión. Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente como Lync 2013.

Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge es preciso incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays. Pero, no es necesario establecer estos parámetros en el mismo valor. Por ejemplo, es posible depurar registros detallados de llamadas con más de 10 días de antigüedad e incluso, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos. Para ello, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0. Por ejemplo:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que necesite depurarse:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Es preciso escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:

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

