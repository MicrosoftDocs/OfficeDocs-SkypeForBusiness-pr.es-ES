---
title: 'Lync Server 2013: instalación de software opcional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6723d005a41b52025c7e3e475bc3b3a108f2c3d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Instalar software opcional en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La herramienta de planeación de Microsoft Lync Server 2013 está diseñada para exportar a Microsoft Excel y Microsoft Visio. Si bien estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, pueden agregar valor significativo a la implementación y la documentación del diseño.

<div>

## <a name="optional-software"></a>Software opcional

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:

  - Resumen: Muestra información sobre la configuración local, incluidos el recuento de usuario, la configuración de capacidad, los roles virtualizados e información del perfil del servidor.

  - Perfil de hardware: Muestra un informe sobre las configuraciones de hardware recomendadas para los servidores que se especifican en la topología, incluidos la CPU, la memoria, el disco y la interfaz de red. También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor. De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.

  - Requisitos de los puertos: Muestra un informe de todos los puertos que están habilitados y la asociación con el equilibrio de carga del Sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB). Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.

  - Informe Resumen: muestra el resumen general de la configuración necesaria para configurar la red de su servidor perimetral.

  - Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de asunto necesarios para los certificados necesarios para obtener los servidores perimetrales.

  - Informe de firewall: Muestra los puertos de origen y de destino y direcciones IP de las interfaces tanto interna como externa.

  - Informe DNS: Muestra el nombre de dominio completo (FQDN) y direcciones IP/VIP que se necesitan para cada entrada DNS que se cree.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:

<div>


> [!NOTE]  
> Si el diseño es lo suficientemente grande para requerir más de tres servidores front-end, se creará una página adicional para el grupo front-end, los servidores front-end, el equipo con SQL Server, las direcciones IP y los FQDN.



</div>

  - Topología global: Diagrama de sitios de 2013 de Lync Server configurados.

  - Ficha nombre del sitio: muestra la topología de configuración del sitio con servidor perimetral, firewall, red de telefonía pública conmutada (RTC) con puertas de enlace y la implementación de servidor interno. La implementación interna consta de servidores y grupos de servidores, entre los que se incluyen las secciones front end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada de Exchange (UM), los servidores de buzón de Exchange y los servidores de Office Web Apps. Servidores de mediación y servidores de chat persistentes.

  - Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con las direcciones IP y FQDN asociados. El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos. Además, se muestran los directores y el servidor front-end o el grupo front-end, con el DNS LB o HLB asociado y la dirección IP asignada (la herramienta de planeación admite direcciones IPv4 e IPv6) y FQDN.

</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Instalar la herramienta de planeación en Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

