---
title: 'Lync Server 2013: Enrutamiento entre troncos'
TOCTitle: Enrutamiento entre troncos
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48276770
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enrutamiento entre troncos en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-20_

Lync Server 2013 puede interconectar una puerta de enlace IP-PBX con una RTC de modo que las llamadas realizadas desde un teléfono PBX se puedan enrutar a RTC y las llamadas RTC entrantes se puedan enrutar e un teléfono PBX. De manera similar, Lync Server 2013 puede interconectar dos o más sistemas IP-PBX de modo que las llamadas se puedan realizar y recibir entre teléfonos PBX de los diferentes sistemas IP-PBX.

Esta característica de enrutamiento entre troncos se puede configurar mediante el cmdlet de Shell de administración de Lync Server, **Set-CsTrunkConfiguration**, con el nuevo parámetro PstnUsages. Este parámetro especifica el conjunto de registros de uso RTC que usar. Un tronco usa esta RTC para determinar una ruta y para enrutar todas las llamadas entrantes como corresponda.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

En el siguiente diagrama se ilustra Lync Server 2013 proporcionando interconectividad entre una puerta de enlace RTC y una IP-PBX.

**Enrutamiento entre troncos entre puerta de enlace e IP PBX**

![Diagrama de conexión pasarela RTC/IP-PBX en Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagrama de conexión pasarela RTC/IP-PBX en Lync Server")

En el siguiente diagrama se ilustra Lync Server 2013 interconectando dos sistemas IP-PBX.

**Enrutamiento entre troncos entre dos IP PBX**

![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de interconexión de los sistemas IP-PAX en Lync Server")

