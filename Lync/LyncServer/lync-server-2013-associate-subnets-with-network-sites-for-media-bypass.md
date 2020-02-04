---
title: 'Lync Server 2013: asociar subredes con sitios de red para omitir elementos multimedia'
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
ms.openlocfilehash: dd45daa964b51639c7fe1db3ff10e334e21641f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a>Asociar subredes con sitios de red para evitar contenido multimedia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

<div>


> [!NOTE]  
> En este tema se supone que ha configurado la configuración global de omisión de medios y que ha configurado la región de red y los sitios de red para la omisión de medios.



</div>

Cada subred de su red debe estar asociada a un sitio de red específico. Esto se debe a que la información de subred se usa para determinar el sitio de red en el que se encuentra un extremo. Cuando se conocen las ubicaciones de ambas partes en una sesión, la omisión de medios puede determinar dónde enviar los medios para su procesamiento.

La omisión de elementos multimedia no tiene ningún requisito especial para asociar subredes a sitios de red. Para crear una asociación entre las subredes y los sitios de red de su topología, siga los procedimientos que se describen en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a>Pasos siguientes: crear perfiles de directiva de ancho de banda

Después de asociar subredes a sitios de red para omitir elementos multimedia, debe crear uno o varios perfiles de directiva de ancho de banda que crearán particiones de subredes para los usuarios con una buena conectividad y aquellos sin, a fin de omitir los medios. Todas las subredes de una región de red con sitios de red que no tienen restricciones de ancho de banda tienen una buena conectividad y, por lo tanto, estas subredes pueden usar la omisión de medios.

Para obtener información sobre los procedimientos para configurar perfiles de directiva de ancho de banda, consulte [crear perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

