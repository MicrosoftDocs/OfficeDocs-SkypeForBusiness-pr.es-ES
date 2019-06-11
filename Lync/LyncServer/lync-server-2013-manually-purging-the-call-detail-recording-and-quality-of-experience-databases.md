---
title: Purgado manual de las bases de datos de grabación de detalles de llamadas y calidad de la experiencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979f05441bfb62c8b79c604127e23fe7b7b4909f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="15e6f-102">Purgar manualmente las bases de datos de grabación de detalles de llamadas y de calidad de la experiencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15e6f-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e6f-103">_**Última modificación del tema:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="15e6f-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="15e6f-p101">Los administradores pueden configurar las bases de datos de Registro detallado de llamadas (CDR) o de Calidad de experiencia (QoE) para depurar automáticamente registros antiguos de la base de datos; esto sucede si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si existe algún registro que haya estado en la base de datos durante más tiempo del especificado. Por ejemplo, cada día a la 01:00 los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="15e6f-p101">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="15e6f-106">Además de esta purga automática, se han agregado dos cmdlets nuevos (Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge) a Microsoft Lync Server 2013. Estos cmdlets permiten a los administradores purgar manualmente registros de las bases de datos de CDR y QoE en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="15e6f-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="15e6f-107">Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos de CDR puede utilizar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="15e6f-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="15e6f-108">En el comando anterior, los registros de detalles de la llamada y los registros de datos de diagnóstico de más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="15e6f-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="15e6f-109">(Los registros de detalles de llamadas son informes de usuario o sesión.</span><span class="sxs-lookup"><span data-stu-id="15e6f-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="15e6f-110">Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente como Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="15e6f-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="15e6f-111">Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge es preciso incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="15e6f-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="15e6f-112">Pero, no es necesario establecer estos parámetros en el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="15e6f-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="15e6f-113">Por ejemplo, es posible depurar registros detallados de llamadas con más de 10 días de antigüedad e incluso, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="15e6f-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="15e6f-114">Para ello, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0.</span><span class="sxs-lookup"><span data-stu-id="15e6f-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="15e6f-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="15e6f-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="15e6f-116">De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que necesite depurarse:</span><span class="sxs-lookup"><span data-stu-id="15e6f-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="15e6f-p105">Es preciso escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="15e6f-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="15e6f-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="15e6f-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="15e6f-120">Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.</span><span class="sxs-lookup"><span data-stu-id="15e6f-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="15e6f-121">Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:</span><span class="sxs-lookup"><span data-stu-id="15e6f-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

