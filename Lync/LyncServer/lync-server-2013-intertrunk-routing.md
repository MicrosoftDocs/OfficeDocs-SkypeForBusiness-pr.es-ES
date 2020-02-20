---
title: 'Lync Server 2013: enrutamiento intertroncal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce206c0f20dc00c6abc1304db8c1f933cbefdbca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Enrutamiento intertroncal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Lync Server 2013 puede interconectar un IP-PBX con una puerta de enlace de red telefónica conmutada (RTC) para que las llamadas de un teléfono PBX se puedan enrutar a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono de central de conmutación (PBX). De forma similar, Lync Server 2013 puede interconectar dos o más sistemas de IP-PBX para que las llamadas se puedan realizar y recibir entre los teléfonos PBX desde los diferentes sistemas IP-PBX.

Esta característica de enrutamiento entre tronco se puede configurar con el cmdlet del shell de administración de Lync Server, **set-CsTrunkConfiguration**, con el nuevo parámetro, PstnUsages. Este parámetro especifica el conjunto de registros de uso RTC que usar. Un tronco usa esta RTC para determinar una ruta y para enrutar todas las llamadas entrantes como corresponda.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

El siguiente diagrama ilustra el 2013 de Lync Server, que proporciona interconectividad entre una puerta de enlace RTC y una IP-PBX.

**Enrutamiento entre troncos entre puerta de enlace e IP PBX**

![Diagrama de la puerta de enlace RTC/IP-PBX que conecta Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagrama de la puerta de enlace RTC/IP-PBX que conecta Lync Server")

El siguiente diagrama ilustra cómo Lync Server 2013 interconectando dos sistemas IP-PBX.

**Enrutamiento entre troncos entre dos IP PBX**

![El diagrama de sistemas de IP-PAX que interconectan con Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "El diagrama de sistemas de IP-PAX que interconectan con Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

