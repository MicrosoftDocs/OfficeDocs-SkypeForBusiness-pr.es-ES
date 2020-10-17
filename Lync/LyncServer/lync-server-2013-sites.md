---
title: Sitios de 2013 de Lync Server
description: Sitios de 2013 de Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59739c5a81fca1f1f3ab5c1b83a23f0be0a5ee2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558966"
---
# <a name="lync-server-sites-for-lync-server-2013"></a>Sitios de Lync Server para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

En Lync Server, puede definir *sitios* en la red que contengan componentes de Lync Server. Un sitio es un conjunto de equipos con una buena conexión de red de alta velocidad y baja latencia, como, por ejemplo, una red de área local (LAN) única o dos redes conectadas a través de una red de fibra óptica de alta velocidad. Tenga en cuenta que los sitios de Lync Server son un concepto independiente de los sitios de servicios de dominio de Active Directory y los sitios de Microsoft Exchange Server. No es necesario que los sitios de Lync Server correspondan con sus sitios de Active Directory.

<div>

## <a name="site-types"></a>Tipos de sitio

Cada sitio puede ser un *sitio central*, que contiene al menos un grupo de servidores front-end o un servidor Standard Edition, o un *sitio de sucursal*. Cada sitio de sucursal está asociado exactamente a un sitio central y los usuarios del sitio de sucursal obtienen la mayor parte de su funcionalidad de Lync Server de los servidores en el sitio central asociado.

Cada una de las sucursales contiene uno de los siguientes elementos:

  - Una aplicación de sucursal con funciones de *supervivencia (SBA)*, que es un servidor blade estándar de la industria con un registrador de Lync Server y un servidor de mediación que se ejecuta en Windows Server. La aplicación de sucursal con funciones de supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). La aplicación de sucursal con funciones de supervivencia está diseñada para sitios de sucursal con entre 25 y 1000 usuarios.

  - Un servidor de sucursal con funciones de *supervivencia (SBS)*, que es un servidor que ejecuta Windows Server y que cumple los requisitos de hardware especificados y que tiene instalado el software del servidor de mediación y el registrador de Lync Server. Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos. El servidor de sucursal con funciones de supervivencia está diseñado para sucursales de entre 1.000 y 5.000 usuarios.

  - Una puerta de enlace RTC y, opcionalmente, un *servidor de mediación*. Para obtener más información sobre este y otros roles de servidor, consulte [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md).

Una sucursal con un vínculo de red de área extensa (WAN) resistente hacia un sitio central puede usar la tercera opción, una puerta de enlace RTC y, opcionalmente, un servidor de mediación. Los sitios de sucursal con vínculos menos resistentes deben usar una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia, que proporcionan resistencia en momentos de errores de red de área extensa. Por ejemplo, en un sitio con una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia implementado, los usuarios pueden seguir realizando y recibiendo llamadas de telefonía IP empresarial si la WAN que conecta el sitio de sucursal al sitio central no está disponible. Para obtener más información sobre la aplicación de sucursal con funciones de supervivencia, el servidor de sucursal con funciones de supervivencia y la resistencia, consulte [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="site-topologies"></a>Topología de sitios

La implementación debe incluir un sitio central como mínimo, y puede incluir de ninguna a muchas sucursales. Cada una de las sucursales está afiliada a un sitio central. El sitio central proporciona los servicios de Lync Server al sitio de sucursal que no se hospedan de forma local en el sitio de sucursal, como la presencia y la Conferencia.

Si tiene varios sitios, puede emparejar los grupos de servidores de front-end en diferentes sitios para habilitar capacidades de recuperación ante desastres. Para obtener más información, consulte [compatibilidad con alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

</div>

<div>

## <a name="see-also"></a>Consulte también


[Roles de servidor en Lync Server 2013](lync-server-2013-server-roles.md)  
[Compatibilidad de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Planeación de la resistencia de la telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

