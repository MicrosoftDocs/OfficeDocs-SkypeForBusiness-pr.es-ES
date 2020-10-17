---
title: 'Lync Server 2013: configurar 9-1-1 mejorado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 642117d89936741cf2610b4d76e1a20125336e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537117"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Configurar 9-1-1 mejorado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Enhanced 9-1-1 (E9-1-1) es una característica de notificación de emergencia que asocia el número de teléfono de la persona que llama con una dirección de la ciudad o la calle. Con esta información, el punto de respuesta de seguridad pública (PSAP) puede enviar inmediatamente los servicios de emergencia al autor de la llamada en peligro.

Para admitir E9-1-1, Lync Server 2013 debe poder asociar correctamente una ubicación con un cliente y asegurarse de que esta información se usa para enrutar la llamada de emergencia al PSAP más cercano.

Para obtener más información acerca de la planeación de una implementación de E9-1-1, consulte [Planning for Emergency Services (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

<div>


> [!IMPORTANT]  
> Lync Server 2013 solo admite E9-1-1 en los Estados Unidos. Para implementar E9-1-1, tiene que configurar una conexión SIP a un proveedor de servicios E9-1-1 calificado o implementar una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en teléfono conmutada (RTC). Para obtener más información, consulte <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) y Mediation Server in Lync Server 2013</A>. Para obtener más información sobre cómo configurar conexiones troncales, consulte <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurar un tronco con la omisión de medios en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar una ruta de voz E9-1-1 en Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Configurar la información del sitio para E9-1-1 en Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Configurar las características avanzadas de E9-1-1 en Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

