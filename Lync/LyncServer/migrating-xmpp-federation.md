---
title: Migrar la federación XMPP
description: Migrar la Federación XMPP.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543216"
---
# <a name="migrating-xmpp-federation"></a>Migrar la federación XMPP

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP. En Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica. La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral de Lync Server 2013 y la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.

Desde el punto de vista de la migración, una cuenta de usuario de Lync Server se puede mover a un grupo de servidores de Lync Server 2013 y seguir usando la puerta de enlace XMPP heredada. Esto solo es posible si el socio federado XMPP no está configurado en Lync Server 2013.

En Resumen, si se ha implementado Lync Server 2010 con la puerta de enlace XMPP Office Communications Server 2007 R2 y la Federación XMPP se ha habilitado para los usuarios de Lync Server 2010 heredados, migrar la Federación XMPP a Lync Server 2013:

1.  Implementar un grupo de servidores de Lync Server 2013.

2.  Implementar un servidor perimetral de Lync Server 2013.

3.  Mover todos los usuarios al grupo de servidores de Lync 2013

4.  Cree certificados y directivas de acceso de XMPP para el servidor perimetral.

5.  Habilite la Federación XMPP en Lync Server 2013. 

6.  Actualice las entradas DNS para que apunten a la puerta de enlace XMPP de Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

