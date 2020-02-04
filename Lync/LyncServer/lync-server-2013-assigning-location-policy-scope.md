---
title: 'Lync Server 2013: ámbito de la Directiva de ubicación de asignación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395b8a4271338231b4c2c1927f7e40fb21a1cb14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>Asignación de un ámbito de directivas de ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

Al igual que con otras directivas de Lync Server, las directivas de ubicación se pueden asignar a varios niveles de ámbito: global, de sitio y usuario. Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario tiene un bit diferente al de otras directivas de Lync Server. No solo se pueden aplicar directivas de ubicación por usuario a los objetos de extremo (como usuarios y objetos de contacto de teléfono comunes), sino que también se pueden aplicar a sitios de red de Lync Server. Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o de un sitio de sucursal completo). Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red. Si la directiva de ubicación de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en el sitio de red sustituye a cualquier otra configuración de directiva por usuario.

Cada sitio de red tiene una directiva de ubicación asignada y cada directiva tendrá asignados valores diferentes de Usos de la RTC, URI de notificación y URI de conferencia.

<div>


> [!NOTE]  
> El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red, independientemente de a qué grupo o a qué sitio esté asignado el usuario.



</div>

</div>

<span> </span>

</div>

</div>

</div>

