---
title: Purgar manualmente las bases de datos de grabación de detalles de llamadas y de calidad de la experiencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumen: Aprenda a purgar manualmente registros de las bases de datos de CDR y de QoE que usa Skype empresarial Server.'
ms.openlocfilehash: ba87e05dd72e5da22cfe4e01cd68be1a9fac6242
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239881"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="0dec2-103">Purgar manualmente las bases de datos de grabación de detalles de llamadas y de calidad de la experiencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0dec2-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="0dec2-104">**Resumen:** Aprenda a purgar manualmente registros de las bases de datos de CDR y de QoE que usa Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0dec2-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="0dec2-p101">Las bases de datos de CDR y QoE pueden purgar los registros de forma manual o automática. Purgar registros puede ser importante para que los datos no se queden obsoletos o cuando sea necesario para restablecer informes desde una línea base de inicio.</span><span class="sxs-lookup"><span data-stu-id="0dec2-p101">The CDR and QoE databases can be manually or automatically purged of records. Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="0dec2-107">Purgar manualmente los registros de bases de datos de CDR y QoE</span><span class="sxs-lookup"><span data-stu-id="0dec2-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="0dec2-p102">Los administradores pueden configurar las bases de datos de Registro detallado de llamadas (CDR) o de Calidad de experiencia (QoE) para depurar automáticamente registros antiguos de la base de datos; esto sucede si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si existe algún registro que haya estado en la base de datos durante más tiempo del especificado. Por ejemplo, cada día a la 01:00 los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="0dec2-p102">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="0dec2-110">Además de esta purga automática, se han agregado dos cmdlets nuevos &#x2014; Invoke-CsCdrDatabasePurge y Invoke-CsQoEDatbasePurge &#x2014; a Skype empresarial Server. Estos cmdlets permiten a los administradores purgar manualmente registros de las bases de datos de CDR y QoE en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="0dec2-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="0dec2-111">Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos de CDR puede utilizar un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0dec2-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="0dec2-112">En el comando anterior, los registros de detalles de la llamada y los registros de datos de diagnóstico de más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="0dec2-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="0dec2-113">(Los registros de detalles de llamadas son informes de usuario o sesión.</span><span class="sxs-lookup"><span data-stu-id="0dec2-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="0dec2-114">Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente, como Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0dec2-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="0dec2-115">Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge es preciso incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="0dec2-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="0dec2-116">Pero, no es necesario establecer estos parámetros en el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="0dec2-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="0dec2-117">Por ejemplo, es posible depurar registros detallados de llamadas con más de 10 días de antigüedad e incluso, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0dec2-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="0dec2-118">Para ello, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0.</span><span class="sxs-lookup"><span data-stu-id="0dec2-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="0dec2-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0dec2-119">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="0dec2-120">De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que necesite depurarse:</span><span class="sxs-lookup"><span data-stu-id="0dec2-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="0dec2-p106">Es preciso escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="0dec2-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="0dec2-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0dec2-123">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="0dec2-124">Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.</span><span class="sxs-lookup"><span data-stu-id="0dec2-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="0dec2-125">Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:</span><span class="sxs-lookup"><span data-stu-id="0dec2-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


