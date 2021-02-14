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
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Purgar manualmente el registro detallado de llamadas y las bases de datos de calidad de la experiencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo purgar manualmente los registros de las bases de datos cdr y qoe usadas por Skype Empresarial Server.
  
Las bases de datos de CDR y QoE se pueden purgar manualmente o automáticamente de los registros. Purgar registros puede ser importante para que los datos no se vuelvan obsoletos o cuando necesiten restablecer informes desde una línea base inicial.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Purgar manualmente registros de bases de datos CDR y QoE

Los administradores pueden configurar las bases de datos de registro detallado de llamadas (CDR) o calidad de la experiencia (QoE) para purgar automáticamente los registros antiguos de la base de datos; esto ocurre si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si hay registros que han estado en la base de datos durante más tiempo del especificado. Por ejemplo, cada día a la 1:00 AM los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.
  
Además de esa purga automática, se han agregado dos nuevos cmdlets &#x2014; Invoke-CsCdrDatabasePurge y Invoke-CsQoEDatbasePurge &#x2014; a Skype Empresarial Server; Estos cmdlets permiten a los administradores purgar manualmente los registros de las bases de datos de CDR y QoE en cualquier momento. Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos CDR puede utilizar un comando similar al siguiente:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

En el comando anterior tanto los registros de detalles de llamadas como los registros de datos de diagnóstico que tengan más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com. (Los registros de detalles de llamadas son informes de usuario/sesión. Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente como Skype Empresarial Server).
  
Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge debe incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays. Sin embargo, no es necesario establecer estos parámetros en el mismo valor. Por ejemplo, es posible depurar registros de detalles de llamadas con más de 10 días de antigüedad y sin embargo, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos. Para ello, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0. Por ejemplo:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que deba depurarse:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Debe escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:
  
```powershell
-Confirm:$False
```

Por ejemplo:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.
  
Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


