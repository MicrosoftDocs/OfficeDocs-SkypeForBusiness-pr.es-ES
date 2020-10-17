---
title: Grupo de Director escalado-equilibrio de carga DNS y equilibrador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d05e579d8c4a2c54342b926b34ff20bbd722524c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510977"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Grupo de Director escalado-equilibrio de carga de DNS y equilibrador de carga de hardware en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Un grupo de servidores de Director escalado, donde hay más de un director implementado para controlar la capacidad adicional y proporcionar una alta disponibilidad, requiere equilibrio de carga para distribuir la comunicación entre el cliente y el servidor a todos los miembros del grupo. Un director hospeda servicios web muy similares a un grupo de servidores front-end. Para proporcionar el equilibrio de carga, puede usar el equilibrio de carga de hardware o equilibrio de carga del sistema de nombres de dominio (DNS) y equilibrio de carga de hardware. El equilibrio de carga de hardware se requiere para los servicios web y el equilibrio de carga de DNS independiente no proporciona las capacidades requeridas para los servicios web.

Los siguientes temas describen las consideraciones de planeación para implementar un grupo de directores mediante el equilibrio de carga de DNS junto con el equilibrio de carga de hardware. Si tiene previsto usar el equilibrio de carga de hardware, pero no el equilibrio de carga de DNS para el grupo de directores, consulte el tema [grupo de Director escalado-equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que describe los requisitos de planeación para esa topología.

![Grupo de director escalado](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Grupo de director escalado")

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado-carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de Puerto-carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de DNS-carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

