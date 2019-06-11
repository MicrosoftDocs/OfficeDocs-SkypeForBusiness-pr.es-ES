---
title: 'Lync Server 2013: Procedimientos recomendados para el servicio de control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89be654a01615c750ce4f49f866e9339bc7e261
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Procedimientos recomendados para el servicio de control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Para mejorar el rendimiento y facilitar la implementación, sigue los procedimientos recomendados descritos a continuación a la hora de implementar el servicio de control de admisión de llamadas:

  - Comprueba que las redes WAN estén correctamente aprovisionadas para el tráfico de medios actual y previsto.
    
    <div>
    

    > [!NOTE]  
    > Recomendamos tener en cuenta un búfer además de los límites de ancho de banda. Existen escenarios, como condiciones de carrera, que afectan al ancho de banda total usado y pueden dar lugar a situaciones en que se supera el límite de ancho de banda. Por ejemplo, si se intentan iniciar dos llamadas cuando el tráfico de medios está alcanzando un límite de ancho de banda, es posible que una de ellas sea denegada porque la otra intentó iniciarse primero.

    
    </div>

  - Supervisa el uso de red y los registros de detalles de llamadas para que puedas elegir una configuración óptima de CAC y actualizarla conforme el uso de la red va cambiando.

  - Usa directivas de ancho de banda de CAC para complementar la configuración de QoS.

  - Si deseas volver a redirigir llamadas bloqueadas a la RTC, comprueba la capacidad y las funciones de la RTC. Para obtener más información, consulte [planear el enrutamiento de voz saliente en Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    
    <div>
    

    > [!NOTE]  
    > La capacidad hace referencia a la cantidad de puertos que necesitas abrir para admitir un nuevo posible enrutamiento de la RTC.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

