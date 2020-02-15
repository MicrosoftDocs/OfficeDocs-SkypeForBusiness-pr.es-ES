---
title: 'Lync Server 2013: procedimientos recomendados para el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00dbaa2f47d34f06424c9013a5b691caab56499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Procedimientos recomendados para el control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Para mejorar el rendimiento y facilitar la implementación, siga los procedimientos recomendados descritos a continuación a la hora de implementar el control de admisión de llamadas:

  - Compruebe que las redes WAN estén correctamente aprovisionadas para el tráfico de medios actual y previsto.
    
    <div>
    

    > [!NOTE]  
    > Se recomienda tener en cuenta un búfer además de los límites de ancho de banda. Existen escenarios, como condiciones de carrera, que afectan al ancho de banda total usado y pueden dar lugar a situaciones en que se supera el límite de ancho de banda. Por ejemplo, si se intentan iniciar dos llamadas cuando el tráfico de medios está alcanzando un límite de ancho de banda, es posible que una de ellas sea denegada porque la otra intentó iniciarse primero.

    
    </div>

  - Supervise el uso de red y los registros de detalles de llamadas para que pueda elegir una configuración óptima de control de admisión de llamadas y actualizarla conforme el uso de la red va cambiando.

  - Use directivas de ancho de banda de control de admisión de llamadas para complementar la configuración de QoS.

  - Si desea volver a enrutar llamadas bloqueados a la RTC, compruebe la capacidad y las funciones de la RTC. Para obtener más información, consulte [planeación de enrutamiento de voz saliente en Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > La capacidad hace referencia al número de puertos que necesita abrir para poder volver a enrutar la RTC.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

