---
title: 'Lync Server 2013: Enrutamiento entre troncos'
TOCTitle: Enrutamiento entre troncos
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49889818
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enrutamiento entre troncos en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-08_

Lync Server 2013 ofrece opciones básicas de administración de sesión mediante el enrutamiento entre troncos. Esta nueva capacidad permite a Lync Server ofrecer funcionalidades de control de llamadas para conectar sistemas de telefonía en dirección descendente. El enrutamiento entre troncos puede interconectar sistemas IP-PBX con una puerta de enlace de red de telefonía conmutada (RTC) pública para que las llamadas realizadas desde un teléfono de central de conmutación PBX se puedan enrutar a la RTC y las llamadas RTC entrantes se puedan enrutar a un teléfono PBX. Del mismo modo, Lync Server puede interconectar dos o más sistemas IP-PBX para que se puedan realizar y recibir llamadas entre teléfonos PBX de diferentes sistemas IP-PBX.

En la figura siguiente se puede ver un Lync Server 2013 ofreciendo interconexión a una puerta de enlace RTC y un sistema IP-PBX.

![Diagrama de conexión pasarela RTC/IP-PBX en Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagrama de conexión pasarela RTC/IP-PBX en Lync Server")

En la figura siguiente se ve un Lync Server 2013 conectando dos sistemas IP-PBX.

![Diagrama de interconexión de los sistemas IP-PAX en Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de interconexión de los sistemas IP-PAX en Lync Server")

