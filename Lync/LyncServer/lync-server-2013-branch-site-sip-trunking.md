---
title: 'Lync Server 2013: enlace troncal SIP de sitio de sucursal'
description: 'Lync Server 2013: enlace troncal SIP de sitio de sucursal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e408a462c21ffa6df6e6a2aee50d7b87dca1f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569326"
---
# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Enlace troncal SIP de sitios de sucursal en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En algunos casos, es posible que necesite implementar un enlace troncal SIP distribuido en los sitios de sucursal seleccionados. Para determinar si se necesita un tronco SIP para un sitio de sucursal, revise la información de [cómo se implementa el enlace troncal SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Para obtener más información sobre las opciones de topología compatibles para implementar troncos SIP en sitios de sucursal, consulte [soluciones de resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal

Cuando decida implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costos específicos del sitio. Por ejemplo, una empresa que tenga un sitio central en Redmond, Washington y un sitio de sucursal en Nueva York debe realizar un análisis para determinar si debe implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicios local.

Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifique qué números DID usarán el tronco SIP y analice la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425). Puede haber finalizado la terminación del sitio de sucursal en el sitio central. Por ejemplo, el sitio central de Redmond puede hospedar números DID para el sitio de sucursal de Nueva York. Si el costo de implementar un tronco SIP distribuido es menor que el costo de las llamadas, considere la posibilidad de implementar un tronco SIP en el sitio de sucursal de Nueva York.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Otros requisitos de un tronco SIP de sitio de sucursal

La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas RTC de larga distancia de cada opción. Si implementa un tronco SIP de sitio de sucursal, también necesita determinar los requisitos de resistencia y ancho de banda. Si el vínculo entre el sitio de sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o una puerta de enlace. No es necesario implementar una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal. Si el vínculo entre el sitio de sucursal y el sitio central no es resistente, implemente una aplicación de sucursal con funciones de supervivencia o implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace o un tronco SIP en el sitio de sucursal.

</div>

</div>

<span> </span>

</div>

</div>

</div>

