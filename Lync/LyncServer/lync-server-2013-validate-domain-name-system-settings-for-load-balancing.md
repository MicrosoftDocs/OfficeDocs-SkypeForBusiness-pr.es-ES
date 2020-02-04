---
title: 'Lync Server 2013: validar la configuración del sistema de nombres de dominio para el equilibrio de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0178d179a9684cf07450cdee839af1c8c1ebc22d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Validar la configuración del sistema de nombres de dominio para el equilibrio de carga en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-02_

Para admitir el FQDN que usa el equilibrio de carga de DNS, necesita aprovisionar el DNS, de modo que resuelva el FQDN del grupo (como, por ejemplo, pool01.contoso.com) en las direcciones IP de todos los servidores del grupo (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Necesita incluir solo las direcciones IP de los servidores implementados actualmente.

Además, si usa el equilibrio de carga de DNS para los grupos de límites, se requieren las siguientes entradas DNS:

  - Para el servicio perimetral de acceso de Lync Server, debe tener una entrada para cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de acceso de Lync Server (por ejemplo, sip.contoso.com) a la dirección IP del servicio perimetral de acceso de Lync Server en uno de los servidores perimetrales del grupo.

  - Para el servicio perimetral de conferencias web de Lync Server, debe tener una entrada para cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de conferencias web de Lync Server (por ejemplo, webconf.contoso.com) a la dirección IP del servicio perimetral de conferencias web de Lync Server en uno de los servidores perimetrales del grupo.

  - Para el servicio perimetral de audio/vídeo de Lync Server, debe tener una entrada para cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de audio/vídeo de Lync Server (por ejemplo, av.contoso.com) a la dirección IP del servicio perimetral de audio/vídeo de Lync Server en uno de los servidores perimetrales del grupo.

  - Si desea usar el equilibrio de carga de DNS en la interfaz interna del grupo Edge, debe agregar un registro DNS, que resuelve el nombre completo interno del grupo Edge a la dirección IP de cada servidor del grupo.

Para comprobar que DNS está devolviendo los valores correctos para el equilibrio de carga de DNS, debe usar la herramienta nslookup. Para devolver todos los valores de un registro DNS con Nslookup, debe ejecutar el comando siguiente:

`nslookup <FQDN >`

Debe ejecutar este comando para cada FQDN usado en la configuración del equilibrio de carga de DNS para comprobar que cada registro configurado para el equilibrio de carga de DNS ha devuelto todas las entradas correctas.

</div>

<span> </span>

</div>

</div>

</div>

