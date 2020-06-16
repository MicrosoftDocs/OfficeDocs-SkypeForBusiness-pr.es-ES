---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrar la federación XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Las versiones anteriores de Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que podía implementarse como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP. En Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica. La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral de Lync Server 2013 y la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.

Desde el punto de vista de la migración, una cuenta de usuario de Office Communications Server 2007 R2 puede moverse a un grupo de servidores de Lync Server 2013 y seguir usando la puerta de enlace XMPP de Office Communications Server 2007 R2. Esto solo es posible si el socio federado XMPP no está configurado en Lync Server 2013.

En Resumen, si se ha implementado Office Communications Server con la puerta de enlace XMPP Office Communications Server 2007 R2 y la Federación XMPP se ha habilitado para los usuarios heredados de Office Communications Server 2007 R2, para migrar la Federación XMPP a Lync Server 2013:

1.  Implementar un grupo de servidores de Lync Server 2013.

2.  Implementar un servidor perimetral de Lync Server 2013.

3.  Mueva todos los usuarios al grupo de servidores de Lync 2013.

4.  Cree certificados y directivas de acceso de XMPP para el servidor perimetral.

5.  Habilite la Federación XMPP en Lync Server 2013. 

6.  Actualice las entradas DNS para que apunten a la puerta de enlace XMPP de Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

