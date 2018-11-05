---
title: "Lync Server 2013: Comprobar conectividad entre servidores internos y perimetrales"
TOCTitle: Comprobar la conectividad entre servidores internos y servidores perimetrales
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48274640
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar la conectividad entre servidores internos y servidores perimetrales en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

En Lync Server 2013 había disponible un asistente de validación por separado que servía para validar la conectividad entre los servidores perimetrales y los servidores internos. Ahora, en Lync Server 2013 esta validación se efectúa automáticamente al instalar los servidores perimetrales.

Para validar la replicación de la información de configuración en el servidor perimetral, ejecute el cmdlet del Windows PowerShell**Get-CsManagementStoreReplicationStatus** en el equipo interno en el que se encuentra el Almacén de administración central (o en cualquier equipo unido al dominio en el que los componentes principales de Lync Server 2013 (OcsCore.msi) estén instalados). Los resultados iniciales pueden indicar un estado "False" en lugar de "True" para la replicación. Si así es, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**.

La conectividad de los usuarios externos se puede comprobar por separado, además de usar el Analizador de conectividad remota de Office Communications Server para comprobar la conectividad remota de los usuarios. Para obtener información detallada, consulte [Comprobar la conectividad de usuarios externos en Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).

