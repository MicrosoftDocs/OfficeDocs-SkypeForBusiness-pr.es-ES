---
title: 'Lync Server 2013: definición de los requisitos para la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88a70796282fe09941ce7632d8c13258defc515
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definición de los requisitos para la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-07_

En este tema se proporciona una introducción a las consideraciones que se deben tener en cuenta sobre las regiones, los sitios y los vínculos entre los sitios de la topología y cómo son importantes cuando se implementa la telefonía IP empresarial. Para obtener detalles que le ayuden a tomar estas decisiones, consulte [configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) en la documentación referente a la planeación.

<div>

## <a name="sites-and-regions"></a>Sitios y regiones

En primer lugar, identifique los sitios de la topología en los que va a implementar la telefonía IP empresarial y las regiones de red a las que pertenecen dichos sitios. En concreto, tenga en cuenta la forma en que proporcionará conectividad de red telefónica conmutada (RTC) a cada sitio. Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo. Decida dónde se implementarán las puertas de enlace localmente, donde se implementarán las aplicaciones de sucursal con funciones de supervivencia (las) y dónde puede configurar los troncos SIP (ya sea localmente o en el sitio central) a un proveedor de servicios de telefonía por Internet (ITSP).

</div>

<div>

## <a name="network-links-between-sites"></a>Vínculos de red entre sitios

También debe tener en cuenta el uso de ancho de banda que espera en los vínculos de red entre el sitio central y sus sitios de sucursal. Si tiene, o planea implementar, vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de marcado entrante directo local (DID) para los usuarios de dichos sitios. Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo. Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en el sitio de sucursal y no tiene administradores de Lync Server entrenados locales, le recomendamos que implemente una aplicación de sucursal con funciones de supervivencia en el sitio de sucursal. Si hospeda entre 1000 y 5000 usuarios en el sitio de sucursal, carecen de una conexión WAN resistente y tienen disponibles administradores de Lync Server entrenados, le recomendamos que implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña en el sitio de sucursal. También debe considerar la posibilidad de habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admite la omisión de medios.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

