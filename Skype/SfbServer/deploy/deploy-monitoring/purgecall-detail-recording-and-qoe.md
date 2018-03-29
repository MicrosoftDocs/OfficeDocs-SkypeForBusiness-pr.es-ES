---
title: Purgar manualmente el registro detallado de llamadas y las bases de datos de la calidad de la experiencia en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumen: Conozca cómo purgar manualmente los registros de bases de datos QoE utilizados Skype para Business Server 2015 y el CDR.'
ms.openlocfilehash: 805bf72b3d4846bb00d3c3772b033242976cd7c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server-2015"></a>Purgar manualmente el registro detallado de llamadas y las bases de datos de la calidad de la experiencia en Skype Empresarial Server 2015
 
**Resumen:** Aprenda cómo purgar manualmente los registros de bases de datos QoE utilizados Skype para Business Server 2015 y el CDR.
  
Las bases de datos de CDR y QoE pueden purgar los registros de forma manual o automática. Purgar registros puede ser importante para que los datos no se queden obsoletos o cuando sea necesario para restablecer informes desde una línea base de inicio.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Purgar manualmente los registros de bases de datos de CDR y QoE

Los administradores pueden configurar las bases de datos de Registro detallado de llamadas (CDR) o de Calidad de experiencia (QoE) para depurar automáticamente registros antiguos de la base de datos; esto sucede si se ha habilitado la depuración para la base de datos especificada (CDR o QoE) y si existe algún registro que haya estado en la base de datos durante más tiempo del especificado. Por ejemplo, cada día a la 01:00 los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.
  
Además de eso automático purga, dos nuevos cmdlets & #x 2014; Invocar-CsCdrDatabasePurge y CsQoEDatbasePurge invocan & #x 2014; se han agregado a Skype para Business Server 2015; estos cmdlets permiten a los administradores Purgar manualmente los registros de lo CDR y las bases de datos de calidad de la experiencia en cualquier momento. Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos de CDR puede utilizar un comando similar al siguiente:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

En el comando anterior llaman a registros de detalle y más antigua de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com de registros de datos de diagnóstico. (Registros de detalle de llamada son informes de sesión del usuario. Registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones de cliente como Skype para Business Server 2015.)
  
Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge es preciso incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays. Pero, no es necesario establecer estos parámetros en el mismo valor. Por ejemplo, es posible depurar registros detallados de llamadas con más de 10 días de antigüedad e incluso, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos. Para ello, establezca PurgeCallDetailDataOlderThanDays a 10 y PurgeDiagnosticDataOlderThanDays en 0. Por ejemplo:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que necesite depurarse:
  
```
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
```

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


