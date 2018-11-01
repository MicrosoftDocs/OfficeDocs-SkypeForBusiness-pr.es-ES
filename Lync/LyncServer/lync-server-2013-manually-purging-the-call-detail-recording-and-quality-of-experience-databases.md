---
title: "Depuración manual de DB de grabación de detalles de llamada y calidad de experiencia"
TOCTitle: "Purge man. des BD de l’enr. des détails des appels et de la qual. de l’exp."
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48274966
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Depuración manual de las bases de datos de grabación de detalles de llamada y de calidad de la experiencia

 

_**Última modificación del tema:** 2014-07-07_

Como se observó en la sección anterior, los administradores pueden configurar las bases de datos de Registro de detalles de llamadas (CDR) y/o de Calidad de experiencia (QoE) para depurar automáticamente registros viejos de la base de datos; esto sucede si la depuración ha sido habilitada para la base de datos especificada (CDR o QoE) y si existe algún registro que haya estado en la base de datos por más tiempo del especificado. Por ejemplo, cada día a la 1:00 AM los administradores podrían configurar el sistema de modo tal que los registros de QoE que tengan más de 60 días de antigüedad se eliminen de la base de datos de QoE.

Además de la depuración automática, se han agregado dos nuevos cmdlets --Invoke-CsCdrDatabasePurge y Invoke-CsQoEDatbasePurge-- a Microsoft Lync Server 2013; estos cmdlets permiten a los administradores depurar manualmente los registros de las bases de datos CDR y QoE en cualquier momento. Por ejemplo, para depurar manualmente todos los registros que tengan más de 10 días de antigüedad de la base de datos CDR puede utilizar un comando similar al siguiente:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

En el comando anterior tanto los registros de detalles de llamadas como los registros de datos de diagnóstico que tengan más de 10 días se eliminan de la base de datos de supervisión en atl-sql-001.litwareinc.com. (Los registros de detalles de llamadas son informes de usuario/sesión. Los registros de datos de diagnóstico son registros de diagnóstico cargados por aplicaciones cliente como Lync 2013).

Como se ha mostrado anteriormente, al ejecutar el cmdlet Invoke-CsCdrDatabasePurge debe incluir tanto el parámetro PurgeCallDetaiDataOlderThanDays como el parámetro PurgeDiagnosticDataOlderThanDays. Sin embargo, no es necesario establecer estos parámetros en el mismo valor. Por ejemplo, es posible depurar registros de detalles de llamadas con más de 10 días de antigüedad y sin embargo, al mismo tiempo, dejar todos los registros de datos de diagnóstico en la base de datos. Para realizar eso, establezca PurgeCallDetailDataOlderThanDays en 10 y PurgeDiagnosticDataOlderThanDays en 0. Por ejemplo:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

De manera predeterminada, cuando ejecute Invoke-CsCdrDatabasePurge verá una solicitud similar a esta para cada tabla de base de datos que deba depurarse:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Debe escribir Y (para Sí) o A (para Sí a todo) antes de que se lleve a cabo realmente la depuración de la base de datos. Si deseara eliminar estas solicitudes de confirmación, agregue el siguiente parámetro al final de su llamada para Invoke-CsCdrDatabasePurge:

    -Confirm:$False

Por ejemplo:

    Invoke-CsCdrDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Si realiza eso, las solicitudes de confirmación no se mostrarán, y la depuración de la base de datos se realizará de inmediato.

Para depurar la base de datos de QoE, utilice el cmdlet Invoke-CsQoEDatabasePurge y especifique la antigüedad (en días) de los registros que se eliminarán:

    Invoke-CsQoEDatabasePurge -Identity MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

