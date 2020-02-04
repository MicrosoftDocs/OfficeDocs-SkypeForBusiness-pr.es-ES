---
title: 'Lync Server 2013: implementación de telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf57d55899d556ddfde633c975ae9f0516e48e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Implementación de telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Lync Server 2013, Enterprise Voice, forma parte de la infraestructura de Lync Server 2013.

La implementación de la telefonía IP empresarial requiere que:

<div id="sectionSection0" class="section">

1.  Revise la sección [planear la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) de la documentación de planeación.

2.  Finalizar planes de características y componentes para implementar con esta carga de trabajo.

3.  Ejecute la herramienta de planeación para diseñar una topología que refleje las decisiones de implementación.

4.  Abra el diseño de topología en el generador de topologías, como se describe en [definir y configurar la topología de Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) en la documentación de implementación.
    
    <div>
    

    > [!NOTE]  
    > La instalación de Topology Builder forma parte del proceso de implementación del grupo interno. Para obtener más información, vea <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar las herramientas administrativas 2013 de Lync Server</A> en la documentación de implementación.

    
    </div>

Además, debe haber implementado ya implementado Lync Server, Enterprise Edition en sitios centrales y sitios de sucursales que corresponden a la topología de referencia que elige implementar. No puede implementar componentes de voz empresarial hasta que haya definido, publicado e instalado archivos para al menos un grupo interno, y debe usar el generador de topología para definir y publicar un grupo interno.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Para ver las topologías de referencia con ejemplos de dónde se pueden implementar los roles de servidor de telefonía IP (y su relación entre sí y otros roles de servidor de Lync Server 2013), vea [topologías de referencia en Lync server 2013](lync-server-2013-reference-topologies.md) en la documentación de planificación.

Para ver una topología de referencia que ilustre y explique una implementación de control de admisión de llamadas de ejemplo, incluidas las regiones de red, los sitios de red y las subredes, vea [ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación de planeación.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Para implementar la telefonía IP empresarial en un sitio central, siga leyendo los temas de esta sección. Para implementar la telefonía IP empresarial en un sitio de sucursal, vaya a <A href="lync-server-2013-deploying-branch-sites.md">implementar sitios de sucursales en Lync Server 2013</A> en la documentación de implementación.



</div>

La documentación de esta sección incluye procedimientos para implementaciones en las que se instala un servidor de mediación en cada servidor front-end o servidor Standard Edition, como se recomienda, y también para implementaciones con un grupo de servidores de mediación independiente.

Puede omitir el siguiente contenido si usó el generador de topología para definir y publicar una topología que collocates un servidor de mediación en cada servidor front-end o un servidor Standard Edition, ya que el Asistente para la implementación ya instaló automáticamente los archivos para Servidor de mediación al instalar archivos para el grupo de servidores front-end o el servidor Standard Edition:

  - [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md)

Si usó el generador de topología para definir y publicar un servidor de mediación en un grupo independiente, puede usar el siguiente contenido:

  - Compruebe que su topología cumpla los requisitos previos del software y el entorno, según se describe en [requisitos previos de telefonía IP empresarial para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - <span></span>  
    [Requisitos previos de la telefonía IP empresarial para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Exportar e importar la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Implementar la mensajería unificada de Exchange local para proporcionar correo de voz de Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Configuración de la integración de Lync Server 2013 local con Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Implementación de características avanzadas de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Acerca de las regiones de red, sitios y subredes en Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Crear o modificar una región de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configurar 9-1-1 mejorado en Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configurar la omisión de medios en Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Habilitar usuarios para telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementación de sitios de sucursales en Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configurar una conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configurar el estacionamiento de llamadas en Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configuración de anuncios para números sin asignar en Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Implementación de la supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

