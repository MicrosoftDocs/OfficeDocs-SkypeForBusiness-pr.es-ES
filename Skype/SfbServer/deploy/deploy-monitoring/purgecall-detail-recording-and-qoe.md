---
title: Purgar manualmente los detalles de las llamadas y las bases de datos de calidad de la experiencia en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumen: Obtenga información sobre cómo purgar manualmente los registros de CDR y las bases de datos de QoE usados por Skype para Business Server.'
ms.openlocfilehash: 55582d28541e798e8ab1c488fb6eeed266bd29b9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879836"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Purgar manualmente los detalles de las llamadas y las bases de datos de calidad de la experiencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo purgar manualmente los registros de CDR y las bases de datos de QoE usados por Skype para Business Server.
  
Las bases de datos de CDR y QoE pueden purgar los registros de forma manual o automática. Purgar registros puede ser importante para que los datos no se queden obsoletos o cuando sea necesario para restablecer informes desde una línea base de inicio.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Purgar manualmente los registros de bases de datos de CDR y QoE

Los administradores pueden configurar las bases de datos de Registro detallado de llamadas (CDR) o de Calidad de experiencia (QoE) para depurar automáticamente registros antiguos de la base de datos; esto sucede si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si existe algún registro que haya estado en la base de datos durante más tiempo del especificado. Por ejemplo, cada día a la 01:00 los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.
  
A la que la eliminación automática, dos nuevos cmdlets & #x 2014; Invoke-CsCdrDatabasePurge y & CsQoEDatbasePurge invocar #x 2014; se han agregado a Skype para Business Server; estos cmdlets permiten a los administradores Purgar manualmente los registros de CDR y las bases de datos de QoE en cualquier momento. Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos de CDR puede utilizar un comando similar al siguiente:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

En el comando anterior llaman a registros de detalle y registros de datos de diagnóstico más antiguos que 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com. (Los registros de detalles de llamadas son informes o sesión de usuario. Registros de datos de diagnóstico son registros de diagnóstico cargados por las aplicaciones de cliente como Skype para Business Server).
  
Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge es preciso incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays. Pero, no es necesario establecer estos parámetros en el mismo valor. Por ejemplo, es posible depurar registros detallados de llamadas con más de 10 días de antigüedad e incluso, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos. Para ello, establezca PurgeCallDetailDataOlderThanDays a 10 y PurgeDiagnosticDataOlderThanDays en 0. Por ejemplo:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que necesite depurarse:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Es preciso escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:
  
```
-Confirm:$False
```

Por ejemplo:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.
  
Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


