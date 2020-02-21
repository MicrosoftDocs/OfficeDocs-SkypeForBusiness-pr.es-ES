---
title: Lync Server 2013 opciones de emparejamiento de grupo admitidas y procedimientos recomendados
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
ms.openlocfilehash: d33bc5e9622728fb4ee9c2a6a566e6010466d577
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Opciones de emparejamiento de grupo admitidas y procedimientos recomendados para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-09_

No hay ninguna restricción en la distancia entre dos centros de datos que están para incluir grupos de servidores front-end emparejados entre sí. Se recomienda usar dos centros de datos de la misma región del mundo, con vínculos de alta velocidad entre ellos. Es mejor si los dos centros de datos están separados lo suficiente como para evitar un desastre si se golpean ambos al mismo tiempo.

Tener dos centros de datos en regiones del mundo, es posible, pero podría provocar una pérdida de datos mayor debido a la latencia de replicación de datos.

Al planear qué grupos de servidores emparejar, debe tener en cuenta que solo se admiten las parejas siguientes:

  - Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition. De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.

  - Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos. De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.

  - Los grupos que están emparejados juntos deben ejecutar el mismo sistema operativo.

Ningún Generador de topologías ni ninguna validación de topología prohibirá el emparejamiento de dos grupos de servidores de forma que no siga estas recomendaciones. Por ejemplo, el Generador de topologías permite emparejar un grupo de servidores de Enterprise Edition con un grupo de servidores de Standard Edition. Sin embargo, no se admiten estos tipos de emparejamientos.

Cada grupo de servidores en un par debe tener la capacidad para servir a todos los usuarios de ambos grupos de servidores en caso de desastre

Si empareja grupos de servidores de Enterprise Edition, también puede implementar alta disponibilidad en los servidores back-end, pero para los pares de grupos de servidores de Standard Edition solo están disponibles las medidas de recuperación ante desastres.

</div>

<span> </span>

</div>

</div>

</div>

