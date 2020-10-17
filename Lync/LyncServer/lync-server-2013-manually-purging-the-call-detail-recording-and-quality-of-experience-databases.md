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
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="1a578-103">Purgado manual del registro detallado de llamadas y de las bases de datos de calidad de la experiencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a578-103">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a578-104">_**Última modificación del tema:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="1a578-104">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="1a578-105">Los administradores pueden configurar el registro de detalles de llamadas (CDR) o las bases de datos de calidad de la experiencia (QoE) para depurar automáticamente los registros antiguos de la base de datos; Esto ocurre si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si hay registros que han estado en la base de datos durante más tiempo que la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="1a578-105">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="1a578-106">Por ejemplo, cada día a la 1:00 AM los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="1a578-106">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="1a578-107">Además de esta purga automática, se han agregado dos cmdlets nuevos (Invoke-CsCdrDatabasePurge y Invoke-CsQoEDatbasePurge) a Microsoft Lync Server 2013; Estos cmdlets permiten a los administradores depurar manualmente los registros de las bases de datos de CDR y QoE en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="1a578-107">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="1a578-108">Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos CDR puede utilizar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a578-108">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="1a578-109">En el comando anterior tanto los registros de detalles de llamadas como los registros de datos de diagnóstico que tengan más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1a578-109">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="1a578-110">(Los registros de detalles de llamadas son informes de usuario/sesión.</span><span class="sxs-lookup"><span data-stu-id="1a578-110">(Call detail records are user/session reports.</span></span> <span data-ttu-id="1a578-111">Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente como Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="1a578-111">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="1a578-112">Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge debe incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="1a578-112">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="1a578-113">Sin embargo, no es necesario establecer estos parámetros en el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="1a578-113">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="1a578-114">Por ejemplo, es posible depurar registros de detalles de llamadas con más de 10 días de antigüedad y sin embargo, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1a578-114">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="1a578-115">Para ello, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0.</span><span class="sxs-lookup"><span data-stu-id="1a578-115">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="1a578-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1a578-116">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="1a578-117">De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que deba depurarse:</span><span class="sxs-lookup"><span data-stu-id="1a578-117">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="1a578-p105">Debe escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="1a578-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="1a578-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1a578-120">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="1a578-121">Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.</span><span class="sxs-lookup"><span data-stu-id="1a578-121">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="1a578-122">Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:</span><span class="sxs-lookup"><span data-stu-id="1a578-122">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

