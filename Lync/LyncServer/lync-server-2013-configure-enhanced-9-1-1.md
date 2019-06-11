---
title: 'Lync Server 2013: Configurar 9-1-1 mejorado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Configurar 9-1-1 mejorado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

9-1-1 mejorado (E9-1-1) es una característica de notificación de emergencia que asocia el número de teléfono de la persona que llama con una dirección postal o una calle. Con esta información, el PSAP (punto de respuesta de seguridad pública) puede enviar servicios de emergencia de forma inmediata a la persona que llama y tiene dificultades.

Para admitir E9-1-1, Lync Server 2013 debe poder asociar correctamente una ubicación con un cliente y asegurarse de que esta información se use para enrutar la llamada de emergencia a la PSAP más cercana.

Para obtener más información sobre cómo planear una implementación de E9-1-1, consulte [planificación de servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

<div>


> [!IMPORTANT]  
> Lync Server 2013 solo admite E9-1-1 dentro de los Estados Unidos. Para implementar E9-1-1, necesita configurar una conexión SIP a un proveedor de servicios E9-1-1 calificado o implementar una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios de telefonía pública conmutada (RTC) y E9-1-1. Para obtener más información, consulte <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) and Media Server in Lync Server 2013</A>. Para obtener más información sobre cómo configurar conexiones troncales, vea <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurar un tronco con la omisión de medios en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar una ruta de voz E9-1-1 en Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Configurar la información del sitio para E9-1-1 en Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Configurar características avanzadas de E9-1-1 en Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

