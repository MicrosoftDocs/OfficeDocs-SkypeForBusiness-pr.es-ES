---
title: Purgar manualmente el registro detallado de llamadas y las bases de datos de calidad de la experiencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumen: obtenga información sobre cómo purgar manualmente los registros de las bases de datos cdr y qoe usadas por Skype Empresarial Server.'
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802150"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="04993-103">Purgar manualmente el registro detallado de llamadas y las bases de datos de calidad de la experiencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="04993-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="04993-104">**Resumen:** Obtenga información sobre cómo purgar manualmente los registros del CDR y las bases de datos de QoE usadas por Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="04993-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="04993-105">Las bases de datos de CDR y QoE se pueden purgar manualmente o automáticamente de los registros.</span><span class="sxs-lookup"><span data-stu-id="04993-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="04993-106">Purgar registros puede ser importante para que los datos no se vuelvan obsoletos o cuando necesiten restablecer informes desde una línea base inicial.</span><span class="sxs-lookup"><span data-stu-id="04993-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="04993-107">Purgar manualmente registros de bases de datos CDR y QoE</span><span class="sxs-lookup"><span data-stu-id="04993-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="04993-108">Los administradores pueden configurar las bases de datos de registro detallado de llamadas (CDR) o calidad de la experiencia (QoE) para purgar automáticamente los registros antiguos de la base de datos; esto ocurre si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si hay registros que han estado en la base de datos durante más tiempo del especificado.</span><span class="sxs-lookup"><span data-stu-id="04993-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="04993-109">Por ejemplo, cada día a la 1:00 AM los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="04993-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="04993-110">Además de esa purga automática, se han agregado dos nuevos cmdlets &#x2014; Invoke-CsCdrDatabasePurge y Invoke-CsQoEDatbasePurge &#x2014; a Skype Empresarial Server; Estos cmdlets permiten a los administradores purgar manualmente los registros de las bases de datos de CDR y QoE en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="04993-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="04993-111">Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos CDR puede utilizar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="04993-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="04993-112">En el comando anterior tanto los registros de detalles de llamadas como los registros de datos de diagnóstico que tengan más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="04993-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="04993-113">(Los registros de detalles de llamadas son informes de usuario/sesión.</span><span class="sxs-lookup"><span data-stu-id="04993-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="04993-114">Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente como Skype Empresarial Server).</span><span class="sxs-lookup"><span data-stu-id="04993-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="04993-115">Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge debe incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="04993-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="04993-116">Sin embargo, no es necesario establecer estos parámetros en el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="04993-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="04993-117">Por ejemplo, es posible depurar registros de detalles de llamadas con más de 10 días de antigüedad y sin embargo, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="04993-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="04993-118">Para ello, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0.</span><span class="sxs-lookup"><span data-stu-id="04993-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="04993-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04993-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="04993-120">De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que deba depurarse:</span><span class="sxs-lookup"><span data-stu-id="04993-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="04993-p106">Debe escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="04993-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="04993-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04993-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="04993-124">Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.</span><span class="sxs-lookup"><span data-stu-id="04993-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="04993-125">Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:</span><span class="sxs-lookup"><span data-stu-id="04993-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


