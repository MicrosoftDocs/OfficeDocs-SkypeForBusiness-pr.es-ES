---
title: "Lync Server 2013: Opciones compatibles emparej. grupos servidores y prácticas recom."
TOCTitle: Opciones compatibles de emparejamiento de grupos de servidores y procedimientos recomendados
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48274517
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Opciones compatibles de emparejamiento de grupos de servidores y procedimientos recomendados para Lync Server 2013

 

_**Última modificación del tema:** 2017-03-09_

No hay ninguna restricción en la distancia entre dos centros de datos que están para incluir grupos de servidores front-end emparejados entre sí. Se recomienda usar dos centros de datos de la misma región del mundo, con vínculos de alta velocidad entre ellos. Es mejor si los dos centros de datos están separados lo suficiente como para evitar un desastre si se golpean ambos al mismo tiempo.

Tener dos centros de datos en regiones del mundo, es posible, pero podría provocar una pérdida de datos mayor debido a la latencia de replicación de datos.

Al planear qué grupos de servidores va a emparejar, debe tener en cuenta que solo se admiten los emparejamientos siguientes:

  - Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition. De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.

  - Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos. De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.

Ni el Generador de topologías ni la validación de topología prohibirán el emparejamiento de dos grupos de servidores de un modo que no siga estas recomendaciones. Por ejemplo, el Generador de topologías permite emparejar un grupo de servidores Enterprise Edition con un grupo de servidores Standard Edition. Sin embargo, estos tipos de emparejamientos no se admiten.

Cada grupo de servidores en un par debe tener la capacidad para servir a todos los usuarios de ambos grupos de servidores en caso de desastre

Si empareja grupos de servidores de Enterprise Edition, también puede implementar alta disponibilidad en los servidores back-end, pero para los pares de grupos de servidores de Standard Edition solo están disponibles las medidas de recuperación ante desastres.

