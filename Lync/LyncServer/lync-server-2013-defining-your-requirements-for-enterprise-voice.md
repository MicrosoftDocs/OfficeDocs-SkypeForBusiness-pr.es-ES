---
title: 'Lync Server 2013: Definición de los requisitos para la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definición de los requisitos para la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-07_

En este tema se proporciona una descripción general de las consideraciones que debe tener en las regiones, los sitios y los vínculos entre los sitios de su topología y cómo son importantes cuando implementa la telefonía IP empresarial. Para obtener detalles que le ayuden a tomar estas decisiones, consulte [configuración de red para las características de telefonía avanzada empresarial de Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) en la documentación de planeación.

<div>

## <a name="sites-and-regions"></a>Sitios y regiones

En primer lugar, identifique los sitios de su topología en los que va a implementar Enterprise Voice y las regiones de red a las que pertenecen dichos sitios. En concreto, tenga en cuenta la forma en que se va a proporcionar conectividad de red telefónica conmutada (RTC) a cada sitio. Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo. Decidir dónde se implementarán las puertas de enlace de forma local, donde se implementarán los dispositivos de sucursal (SBAs) supervivientes, y donde puede configurar los troncos SIP (ya sea de forma local o en el sitio central) a un proveedor de servicios de telefonía por Internet (ITSP).

</div>

<div>

## <a name="network-links-between-sites"></a>Vínculos de red entre sitios

También debe considerar el uso de ancho de banda que espera en los vínculos de red entre su sitio central y sus sitios de sucursales. Si tiene, o planea implementar, vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de marcado directo local (sí) para los usuarios de esos sitios. Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo. Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en el sitio de la sucursal y no dispone de administradores de Lync Server capacitados locales, le recomendamos que implemente una aplicación de mayor supervivencia en el sitio de la sucursal. Si se aloja entre usuarios de 1000 y 5000 en su sitio de sucursal, carece de una conexión WAN resistente y tiene disponibles administradores de Lync Server capacitados, le recomendamos que implemente un servidor de sucursal con una pequeña puerta de enlace en el sitio de la sucursal. También debe considerar habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admite la omisión de medios.

</div>

<div>

## <a name="see-also"></a>Vea también


[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

