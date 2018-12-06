---
title: Configuración de los equipos Lync Server sometidos a supervisión
TOCTitle: Configuración de los equipos Lync Server sometidos a supervisión
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48276235
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de los equipos Lync Server sometidos a supervisión

 

_**Última modificación del tema:** 2012-10-20_

Dado que Lync Server 2013 no utiliza el proceso de detección centralizado que se emplea en Microsoft Lync Server 2010, cada equipo de Lync Server 2013 que desee supervisar deberá tener la capacidad de autonotificar su existencia al servidor de administración. Para hacerlo posible, debe instalar los archivos del agente Operations Manager en cada uno de los equipos que vaya a supervisar. Una vez instalados los archivos del agente, deberá configurar el equipo para que actúe como proxy de System Center. Tenga en cuenta que estos procedimientos deben llevarse a cabo después de haber instalado y configurado Lync Server en los equipos en cuestión.

