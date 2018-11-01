---
title: Comprobar valores de configuración
TOCTitle: Comprobar valores de configuración
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48275228
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar valores de configuración

 

_**Última modificación del tema:** 2012-09-06_

Para validar la replicación de la información de configuración en el servidor perimetral, ejecute el cmdlet de Lync Server 2013**Get-CsManagementStoreReplicationStatus** en el equipo interno en el que se encuentra el Almacén de administración central (o en cualquier equipo unido al dominio en el que los componentes principales de Lync Server 2013(OcsCore.msi) estén instalados).

Los resultados iniciales pueden indicar un estado "False" en lugar de "True" para la replicación. Si es así, ejecute el cmdlet del **Invoke-CsManagementStoreReplication** y deje que la replicación termine antes de volver a ejecutar **Get-CsManagementStoreReplicationStatus**.

