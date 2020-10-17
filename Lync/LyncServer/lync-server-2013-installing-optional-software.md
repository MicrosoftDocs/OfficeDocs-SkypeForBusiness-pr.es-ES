---
title: 'Lync Server 2013: instalar software opcional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f56d856aa0a97125812f68ede9a2bff5b49f036
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498537"
---
# <a name="installing-optional-software-in-lync-server-2013"></a>Instalación de software opcional en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La herramienta de planeación 2013 de Microsoft Lync Server está diseñada para exportar a Microsoft Excel y Microsoft Visio. Aunque estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, agregan un valor significativo a la implementación y la documentación del diseño.

<div>

## <a name="optional-software"></a>Software opcional

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

La exportación de su diseño a Microsoft Excel genera un informe que muestra siete pestañas en la hoja de cálculo:

  - Resumen: muestra información sobre la configuración del sitio, incluidos el número de usuarios, la configuración de capacidad y la información de perfil del servidor.

  - Perfil de hardware: muestra un informe sobre las configuraciones de hardware recomendadas para los servidores que se especifican en la topología, incluida la CPU, la memoria, el disco y la interfaz de red. También se incluye la cantidad y las especificaciones recomendadas para los componentes del servidor. Además, cada servidor se define por sitio para proporcionar una representación completa de los requisitos del servidor por sitio.

  - Requisitos de puertos: muestra un informe de todos los puertos que están habilitados y la asociación con el equilibrio de carga del sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB). Debe usar este informe para planear el firewall y las configuraciones de DNS LB y HLB.

  - Informe de Resumen: muestra el resumen general de la configuración necesaria para configurar la red del servidor perimetral.

  - Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de sujeto necesarios para los certificados necesarios para obtener los servidores perimetrales que ejecutan.

  - Informe de Firewall: muestra los puertos de origen y de destino, así como las direcciones IP de las interfaces externas e internas.

  - Informe de DNS: muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesarias para cada entrada de DNS que cree.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

La exportación de su diseño a Microsoft Visio crea un diagrama para su uso en los fines de documentación de la topología y la infraestructura configuradas. El diagrama importado puede editarse y reorganizarse para satisfacer las necesidades de documentación. El diagrama típico de Visio incluirá:

<div>


> [!NOTE]  
> Si el diseño es lo suficientemente grande como para requerir más de tres servidores front-end, se creará una página adicional para el grupo de servidores front-end, los servidores front-end, el equipo que ejecuta SQL Server, las direcciones IP y los FQDN.



</div>

  - Topología global: Diagrama de sitios configurados de Lync Server 2013.

  - Ficha nombre de sitio: muestra la topología de configuración de sitio con servidor perimetral, firewall, red telefónica conmutada (RTC) con puertas de enlace y la implementación de servidor interna. La implementación interna consta de servidores y grupos de servidores, incluidos los grupos de servidores front-end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada de Exchange, los servidores de buzones de Exchange, los servidores de Office Web Apps, los servidores de mediación y los servidores de chat persistente.

  - Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con las direcciones IP y los FQDN asociados. También se incluyen equilibrio de carga de DNS y equilibradores de carga de hardware. Además, se muestran los directores y el servidor front-end o el grupo de servidores front-end, con el DNS LB o HLB asociado y la dirección IP asignada (la herramienta de planeación admite direcciones IPv4 e IPv6) y el FQDN.

</div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Instalar la herramienta de planeación en Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

