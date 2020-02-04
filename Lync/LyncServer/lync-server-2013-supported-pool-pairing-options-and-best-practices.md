---
title: Prácticas recomendadas y opciones de emparejamiento de grupo compatibles con Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9090fefba4b80f14382b9b43b5e9ced7cb36b2e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Opciones de emparejamiento de bloque y procedimientos recomendados para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-09_

No hay restricciones en la distancia entre dos centros de datos que se van a incluir los grupos de frontales emparejados entre sí. Le recomendamos que use dos centros de datos en la misma región del mundo, con vínculos de alta velocidad entre ellos. Es mejor que los dos centros de datos estén lo suficientemente separados para evitar que se produzca un desastre único al mismo tiempo.

Es posible tener dos centros de datos en todas las regiones del mundo, pero podría provocar una mayor pérdida de datos debido a la latencia en la replicación de datos.

Al planificar qué grupos de servidores vas a emparejar, necesitas tener en cuenta que solo se admiten los emparejamientos siguientes:

  - Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition. De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.

  - Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos. De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.

  - Los grupos que están emparejados deben ejecutar el mismo sistema operativo.

Ni el generador de topologías ni la validación de topología prohibirán el emparejamiento de dos grupos de servidores de un modo que no siga estas recomendaciones. Por ejemplo, el generador de topologías permite emparejar un grupo de servidores Enterprise Edition con un grupo de servidores Standard Edition. En realidad, estos tipos de emparejamientos no se admiten.

Cada grupo de un par debe tener la capacidad de ofrecer a todos los usuarios de ambos grupos en caso de que se produzca un desastre.

Si empareja los grupos de servidores Enterprise Edition, también puede implementar una alta disponibilidad en los servidores back-end, pero para los pares de grupos Standard Edition solo están disponibles las medidas de recuperación ante desastres.

</div>

<span> </span>

</div>

</div>

</div>

