---
title: 'Lync Server 2013: asociar subredes con sitios de red para el desvío de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe244426b6c2b7f83ef8070f995305a2a02ef31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Asociar subredes con sitios de red para el desvío de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

<div>


> [!NOTE]  
> En este tema se da por supuesto que ha realizado la configuración global de desvío de medios, así como una región de red y los sitios de red para el desvío de medios.



</div>

Todas las subredes de la red debe estar asociadas con un sitio de red específico. Por este motivo la información de las subredes se usa para determinar el sitio de red en el que se encuentra un extremo. Cuando se conocen las ubicaciones de ambas partes de una sesión, el desvío de medios puede determinar si envía medios para su procesamiento.

El desvío de medios no tiene requisitos especiales para asociar subredes con sitios de red. Para crear una asociación entre las subredes y los sitios de red de la topología, siga los procedimientos que se indican en [asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Pasos siguientes: Crear perfiles de directivas de ancho de banda

Una vez asociadas las subredes con sitios de red para el desvío de medios, deberá crear uno o varios perfiles de directiva de ancho de banda que particionen las subredes entre las que tienen buena conectividad y aquellas cuyo propósito no es el desvío de medios. Todas las subredes de una región de red que poseen sitios de red sin restricciones de ancho de banda tienen buena conectividad y, por lo tanto, pueden usar el desvío de medios.

Para conocer los procedimientos para configurar los perfiles de directiva de ancho de banda, consulte [Create Bandwidth Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

