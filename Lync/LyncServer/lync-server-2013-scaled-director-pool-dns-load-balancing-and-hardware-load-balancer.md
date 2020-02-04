---
title: Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware
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
ms.openlocfilehash: 16203f7e291b7957793e71872483c93f2d1d04d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Un grupo de directores con escala, en el que hay más de un director implementado para manejar capacidad adicional y proporcionar una alta disponibilidad, requiere el equilibrio de carga para distribuir la comunicación entre el cliente y el servidor a todos los miembros del grupo. Un director hospeda servicios web muy parecidos a un grupo de servidores front-end. Para proporcionar el equilibrio de carga, puede usar el equilibrio de carga de hardware o el equilibrio de carga del sistema de nombres de dominio (DNS) y el equilibrio de carga de hardware. El equilibrio de carga de hardware se requiere para los servicios web y el equilibrio de carga de DNS solo no proporciona las capacidades necesarias para los servicios Web.

En los siguientes temas se describen las consideraciones de planeación para implementar un grupo de directores mediante el equilibrio de carga de DNS junto con el equilibrio de carga del hardware. Si tiene previsto usar el equilibrio de carga de hardware, pero no el equilibrio de carga de DNS para el grupo de directores, consulte el tema [grupo de directores escalados-equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que describe los requisitos de planeación de esa topología.

![Grupo de directores a escala](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Grupo de directores a escala")

<div>

## <a name="in-this-section"></a>En esta sección

  - [Resumen de certificado - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de puerto - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Resumen de DNS - Carga equilibrada DNS y HLB en Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

