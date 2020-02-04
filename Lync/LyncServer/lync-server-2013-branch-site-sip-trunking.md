---
title: 'Lync Server 2013: Troncalización SIP de sitio de sucursal'
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
ms.openlocfilehash: 9c31f0f42a10905f784536b08f10370be9694800
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Branch site SIP trunking in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En algunos casos, es posible que necesites implementar el troncal de SIP distribuido en los sitios de sucursales seleccionados. Para determinar si es necesario un tronco de SIP para un sitio de sucursal, revise la información en [cómo implementar la Troncalización SIP en Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Para obtener más información sobre las opciones de topología compatibles para implementar los troncos SIP en sitios de sucursales, consulte [soluciones de resistencia de sitio de sucursal en Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Ejemplo de análisis de requisitos de un tronco SIP de sitio de sucursal

Si decide implementar un tronco SIP de sitio de sucursal, debe realizar un análisis de costos específico del sitio. Por ejemplo, una empresa que tiene un sitio central en Redmond, Washington y un sitio de sucursal en Nueva York debe realizar un análisis para determinar si implementar un tronco SIP desde el sitio de Nueva York a un proveedor de servicios locales.

Para determinar si un tronco SIP distribuido en Nueva York es rentable, identifica qué números de llamada directa a la extensión (DID) usarán el tronco SIP y analiza la cantidad de llamadas que Nueva York realiza a áreas que no sean Redmond (425). Puede haber finalizado el sitio de la sucursal en el sitio central. Por ejemplo, el sitio central de Redmond puede hospedar números para el sitio de sucursal de Nueva York. Si el precio de la implementación de un tronco de SIP distribuido es menor que el precio de esas llamadas, considere la posibilidad de implementar un tronco del SIP en el sitio de la sucursal de Nueva York.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Otros requisitos de un tronco SIP de sitio de sucursal

La elección entre implementar un tronco SIP en lugar de una puerta de enlace se basa en la diferencia entre las tarifas de la red telefónica conmutada (RTC) de larga distancia de cada opción. Si implementa un tronco SIP de sitio de sucursal, también necesita determinar los requisitos de resistencia y ancho de banda. Si el vínculo entre el sitio de la sucursal y el sitio central es resistente y tiene suficiente ancho de banda, puede implementar un tronco SIP o una puerta de enlace. No es necesario implementar una aplicación de rama que sea superviviente en el sitio de la sucursal. Si el vínculo entre el sitio de la sucursal y el sitio central no es resistente, implemente un dispositivo de sucursal con la supervivencia o implemente un servidor de sucursal que sea reviviente con una puerta de enlace o un tronco SIP en el sitio de la sucursal.

</div>

</div>

<span> </span>

</div>

</div>

</div>

