---
title: 'Lync Server 2013: Acerca de las regiones de red, sitios y subredes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Acerca de las regiones de red, sitios y subredes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Las características avanzadas de voz empresarial descritas en esta sección comparten ciertos requisitos de configuración para regiones de red, sitios de red y subredes. Por ejemplo, las tres características avanzadas requieren que cada subred de su topología esté asociada a un sitio de *red*específico, y cada sitio de red debe estar asociado a una *región de red*.

<div>


> [!IMPORTANT]  
> Antes de comenzar con la configuración de red de control de admisión de llamadas, E9-1-1 o omisión de medios, asegúrese de que ha revisado información adicional sobre la configuración de red en la <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configuración de red para las características avanzadas de telefonía empresarial de Lync Server 2013</A> tema en la documentación de planificación. Para obtener información sobre la configuración de red principalmente sobre el control de admisión de llamadas, vea también <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">definir los requisitos para el control de admisión de llamadas en Lync Server 2013</A> en la documentación de planeación.



</div>

El control de admisión de llamadas y E9-1-1 tienen requisitos de configuración adicionales para los sitios de red:

  - El control de admisión de llamadas requiere que se especifique un   *perfil de directiva de ancho de banda* para cada uno de los sitios restringidos con limitaciones de ancho de banda WAN. Si planea implementar el control de admisión de llamadas, debe [crear perfiles de directiva de ancho de banda en Lync Server 2013 antes de](lync-server-2013-create-bandwidth-policy-profiles.md) configurar los sitios de red.

  - E9-1-1 requiere que se especifique una *directiva de ubicación* para cada uno de los sitios. Si tiene previsto implementar E9-1-1, debe [crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md) antes de configurar los sitios de red.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Crear o modificar regiones de red, sitios de red y subredes

En los siguientes temas se proporcionan pasos para crear o modificar regiones de red y sitios de red, y para asociar subredes a sitios de red. Estos temas no son específicos de ninguna característica avanzada empresarial de voz en particular.

  - [Crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

