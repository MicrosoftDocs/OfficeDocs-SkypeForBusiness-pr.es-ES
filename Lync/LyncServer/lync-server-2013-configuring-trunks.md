---
title: 'Lync Server 2013: Configuración de troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Configuración de troncos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes elementos para proporcionar conectividad de red telefónica conmutada (RTC) pública para los clientes y dispositivos de voz de su organización:

  - Conexión basada en troncos SIP para un proveedor de servicio s de telefonía

  - Puerta de enlace RTC

  - Central de conmutación (PBX)

Para obtener más información, consulte [planificación de la conectividad RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) en la documentación de planeación.

<div>


> [!IMPORTANT]  
> Antes de comenzar con la configuración troncal, verifique que se haya creado la topología y que el servidor de mediación y sus pares se hayan configurado y asociado entre sí. Para obtener más información, vea <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir una puerta de enlace en el generador de topologías de Lync Server 2013</A> en la documentación de implementación.



</div>

<div>


> [!NOTE]  
> Como parte de la configuración troncal, puede habilitar la característica de omisión de medios de Lync Server 2013, que permite a los medios omitir el servidor de mediación. Los troncos se pueden configurar con o sin omisión de medios habilitados, pero le recomendamos encarecidamente que lo habilite. Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planificación de la omisión de medios en Lync Server 2013</A> en la documentación de planeación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Compatibilidad con varios troncales en Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Enrutamiento entre troncales en Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Ver la información de configuración troncal en Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Crear una nueva colección de opciones de configuración de troncal en Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Eliminar una colección existente de parámetros de configuración del tronco de SIP en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modificar la configuración de los enlaces de SIP en Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Probar la configuración del tronco del SIP en Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Ver información sobre los troncos SIP individuales en Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Definir una puerta de enlace en el generador de topología de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Planificación de la conectividad RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

