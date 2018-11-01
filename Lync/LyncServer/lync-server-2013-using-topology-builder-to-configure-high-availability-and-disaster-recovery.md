---
title: "Usar Topology Builder para alta disponibilidad y la recuperación ante desastres"
TOCTitle: Usar Topology Builder para configurar la alta disponibilidad y la recuperación ante desastres
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48276317
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar Topology Builder para configurar la alta disponibilidad y la recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

Siga estos pasos en el Generador de topologías para configurar la disponibilidad alta y la recuperación ante desastres para el Servidor de chat persistente.

1.  Agregue los almacenas de las bases de datos reflejadas y de las bases de datos secundarias de trasvase de registros de SQL Server.

2.  Edite las propiedades de servicio de Servidor de chat persistente en:
    
    1.  Habilite el reflejo para la base de datos principal.
    
    2.  Agregue el almacén SQL Server reflejado principal.
    
    3.  Habilite la base de datos de trasvase de registros SQL Server.
    
    4.  Agregue el almacén SQL Server Trasvase de registros secundarios SQL Server.
    
    5.  Agregue el reflejo del almacén SQL Server para la base de datos secundaria.
    
    6.  Publique la topología.

