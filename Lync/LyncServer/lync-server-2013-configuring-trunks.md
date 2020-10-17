---
title: 'Lync Server 2013: configuración de troncos'
description: 'Lync Server 2013: configuración de troncos.'
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
ms.openlocfilehash: 07d9503cd38419a7145796a6edf8484a14cdeb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544156"
---
# <a name="configuring-trunks-in-lync-server-2013"></a>Configuración de troncos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes homólogos para proporcionar conectividad de red telefónica conmutada (RTC) para clientes y dispositivos de telefonía IP empresarial en su organización:

  - Conexión basada en troncos SIP para un proveedor de servicio s de telefonía

  - Puerta de enlace RTC

  - Central de conmutación (PBX)

Para obtener más información, consulte [planeación de la conectividad con RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) en la documentación referente a la planeación.

<div>


> [!IMPORTANT]  
> Antes de iniciar la configuración de troncos, verifique que se ha creado la topología y que el servidor de mediación y su par se han configurado y asociado entre sí. Para obtener más información, consulte <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir una puerta de enlace en el generador de topologías en Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>


> [!NOTE]  
> Como parte de la configuración del tronco, puede habilitar la característica de omisión de medios de Lync Server 2013, que permite que los medios omitan el servidor de mediación. Los troncos pueden configurarse con el desvío de medios habilitado o deshabilitado, aunque le recomendamos que lo habilite. Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planeación de la omisión de medios en Lync Server 2013</A> en la documentación referente a la planeación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Compatibilidad con varios tronco en Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Enrutamiento entre tronco en Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Ver la información de configuración de tronco en Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Crear una nueva colección de opciones de configuración de tronco en Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Eliminar una colección existente de opciones de configuración de tronco SIP en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modificar las opciones de configuración de tronco SIP en Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Probar las opciones de configuración de tronco SIP en Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Ver información sobre troncos SIP individuales en Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Definir una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Planeación de la conectividad con RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

