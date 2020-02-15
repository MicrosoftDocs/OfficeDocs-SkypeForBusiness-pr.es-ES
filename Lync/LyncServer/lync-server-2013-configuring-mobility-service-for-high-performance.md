---
title: 'Lync Server 2013: configuración del servicio de movilidad para alto rendimiento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 460c56a9e51ab64491402eed22d40d60ad7d89c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Configurar el servicio de movilidad para alto rendimiento en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Este tema solo se aplica al servicio de movilidad de Lync Server 2013 (MCX) y no se aplica a la API Web de comunicaciones unificadas (UCWA), tal y como se proporciona en las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.



</div>

Al instalar el servicio de movilidad (MCX) en Internet Information Services (IIS) 7,5, el instalador del servicio de movilidad configura algunas opciones de rendimiento en el servidor front-end. Se recomienda usar IIS 7.5 para la movilidad. Los parámetros afectan al número máximo de solicitudes de usuario simultáneas y al número máximo de subprocesos permitidos para el servicio de movilidad.

Estas son las opciones de configuración de rendimiento:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Configuración de MCX en IIS 7,5

1.  **maxConcurrentThreadsPerCPU** está configurado en cero (0).

2.  **maxConcurrentRequestsPerCPU** está configurado en cero (0).

3.  El modelo del proceso ASP.NET está configurado en AutoConfig (solo para IIS 7.5).

4.  El límite de cola HTTP.sys está configurado en 1.000 (de manera predeterminada).

</div>

</div>

<span> </span>

</div>

</div>

</div>

