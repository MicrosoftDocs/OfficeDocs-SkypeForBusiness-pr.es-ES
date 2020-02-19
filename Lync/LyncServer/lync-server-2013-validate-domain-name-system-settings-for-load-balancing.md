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
ms.openlocfilehash: fc91b9f3c4ce28946830f6d91bd8cb90dd0544ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Validar la configuración del sistema de nombres de dominio para el equilibrio de carga en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-02_

Para admitir el FQDN que usa el equilibrio de carga DNS, debe aprovisionar el DNS de modo que resuelva el FQDN del grupo de servidores (como, por ejemplo, pool01.contoso.com) como las direcciones IP de todos los servidores del grupo de servidores (por ejemplo, 192.168.1.1, 192.168.1.2, etc.). Solo deberá incluir las direcciones IP de los servidores implementados actualmente.

Además, si usa el equilibrio de carga de DNS para los grupos de servidores perimetrales, se requieren las siguientes entradas DNS:

  - Para el servicio perimetral de acceso de Lync Server, debe tener una entrada por cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de acceso de Lync Server (por ejemplo, sip.contoso.com) a la dirección IP del servicio perimetral de acceso de Lync Server en uno de los servidores perimetrales del grupo.

  - Para el servicio perimetral de conferencia Web de Lync Server, debe tener una entrada por cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de conferencia Web de Lync Server (por ejemplo, webconf.contoso.com) en la dirección IP del servicio perimetral de conferencia Web de Lync Server en uno de los servidores perimetrales del grupo.

  - Para el servicio perimetral de audio y vídeo de Lync Server, debe tener una entrada por cada servidor del grupo. Cada entrada debe resolver el FQDN del servicio perimetral de audio y vídeo de Lync Server (por ejemplo, av.contoso.com) en la dirección IP del servicio perimetral de audio y vídeo de Lync Server en uno de los servidores perimetrales del grupo.

  - Si desea usar el equilibrio de carga de DNS en la interfaz interna del grupo de servidores perimetrales, debe agregar un registro DNS, que resuelva el FQDN interno del grupo de servidores perimetrales en la dirección IP de cada servidor del grupo.

Para comprobar que el DNS devuelve los valores correctos para el equilibrio de carga de DNS, debe usar la herramienta nslookup. Para devolver todos los valores de un registro DNS con Nslookup, debe ejecutar el comando:

`nslookup <FQDN >`

Debe ejecutar este comando para cada FQDN usado en la configuración de equilibrio de carga de DNS para comprobar que cada registro configurado para el equilibrio de carga de DNS devolvió todas las entradas correctas.

</div>

<span> </span>

</div>

</div>

</div>

