---
title: 'Lync Server 2013: Enrutamiento entre troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Enrutamiento entre troncos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Lync Server 2013 puede interconectar un IP-PBX con una puerta de enlace de red telefónica conmutada (RTC) para que las llamadas desde un teléfono PBX se puedan enrutar a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono de la central de conmutación (PBX). De forma similar, Lync Server 2013 puede interconectar dos o más sistemas IP-PBX para que las llamadas se puedan realizar y recibir entre teléfonos PBX desde los diferentes sistemas IP-PBX.

Esta característica de enrutamiento de intertroncalización se puede configurar mediante el cmdlet del shell de administración de Lync Server, **set-CsTrunkConfiguration**, con el nuevo parámetro, PstnUsages. Este parámetro especifica el conjunto de registros de uso de RTC que se va a usar. Un tronco usa este uso de RTC para determinar una ruta y para enrutar todas las llamadas entrantes.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

En el siguiente diagrama se muestra cómo Lync Server 2013 ofrece interconectividad entre una puerta de enlace PSTN y una IP-PBX.

**Enrutamiento de intertroncalización entre puerta de enlace y IP PBX**

![Lync Server que conecta la puerta de enlace RTC/IP-diagrama PBX] (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server que conecta la puerta de enlace RTC/IP-diagrama PBX")

En el siguiente diagrama se muestra cómo Lync Server 2013 interconectando dos sistemas IP-PBX.

**Enrutamiento de intertroncalización entre dos IP PBX**

![Interconexión de Lync Server: Diagrama de sistemas IP-pax] (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Interconexión de Lync Server: Diagrama de sistemas IP-pax")

</div>

<span> </span>

</div>

</div>

</div>

