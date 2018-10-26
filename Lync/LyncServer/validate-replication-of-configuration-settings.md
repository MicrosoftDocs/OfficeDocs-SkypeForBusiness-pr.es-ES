---
title: Validar replicación de los valores de configuración
TOCTitle: Validar replicación de los valores de configuración
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48275844
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Validar replicación de los valores de configuración

 

_**Última modificación del tema:** 2012-10-19_

Puede validar la replicación de la información de configuración para Edge Server al ejecutar el cmdlet Lync Server 2013**Get-CsManagementStoreReplicationStatus** en la PC interna en la que se encuentra el Almacén de administración central (o en cualquier PC unida al dominio en el que los componentes principales de Lync Server 2013 (OcsCore.msi) estén instalados.

Los resultados iniciales pueden indicar el estado como "False" en lugar de "True" para la replicación. En ese caso, ejecute el cmdlet **Invoke-CsManagementStoreReplication** y deje tiempo para que se complete la replicación antes de ejecutar el cmdlet **Get-CsManagementStoreReplicationStatus** de nuevo .

