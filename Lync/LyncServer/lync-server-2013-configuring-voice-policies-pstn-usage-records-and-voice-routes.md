---
title: Configuración de directivas de voz, registros de uso de RTC y rutas de voz
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3a87063503d373c8ef318633c5113624fef00b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a>Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Las directivas de voz, los registros de uso de RTC y las rutas de voz están totalmente relacionados. Para configurar las directivas de voz, debe seleccionar un grupo de características de llamada y luego asignar a la directiva un grupo de registros de uso de RTC, que especifican los derechos que se otorgarán a los usuarios o grupos a los que se les asigne la directiva de voz. A las rutas de voz también se les asignan registros de uso de RTC, que sirven para asociar las rutas con los usuarios autorizados para usarlas. Es decir, los usuarios solo pueden realizar llamadas que usan rutas para las que tienen registros de uso de RTC coincidentes.

El flujo de trabajo recomendado para una nueva implementación de Enterprise Voice es comenzar configurando una directiva de voz que incluya los registros de uso de RTC adecuados y, a continuación, asociar las rutas apropiadas para cada registro de uso de RTC.

<div>


> [!NOTE]
> También puede crear directivas de voz con ámbito de <EM>usuario</EM> y asignarlas a usuarios individuales o grupos.



</div>

Para consultar los pasos detallados que se deben seguir para realizar cada una de estas tareas, consulte los procedimientos que se explican en esta sección.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar directivas de voz y registros de uso de la RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Ver los registros de uso de RTC en Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)

  - [Configuración de rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Exportar e importar la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

