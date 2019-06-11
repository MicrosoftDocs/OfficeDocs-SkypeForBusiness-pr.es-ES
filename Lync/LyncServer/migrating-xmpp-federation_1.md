---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrar la federación XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-16_

Las versiones anteriores de Office Communications Server proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con implementaciones de XMPP. En Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica. La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral 2013 de Lync Server y la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.

Desde el punto de vista de la migración, una cuenta de usuario de Office Communications Server 2007 R2 puede moverse a un grupo de servidores de Lync Server 2013 y seguir usando la puerta de enlace XMPP de Office Communications Server 2007 R2. Esto solo es posible si el socio de XMPP federado no está configurado en Lync Server 2013.

En Resumen, si Office Communications Server se ha implementado con la puerta de enlace XMPP de Office Communications Server 2007 R2 y se ha habilitado la Federación XMPP para los usuarios heredados de Office Communications Server 2007 R2, para migrar la Federación XMPP a Lync Server 2013:

1.  Implementar un grupo de 2013 de Lync Server.

2.  Implementar un servidor perimetral 2013 de Lync Server.

3.  Mueva todos los usuarios al grupo de servidores de Lync Server 2013.

4.  Cree certificados y directivas de acceso XMPP para el servidor perimetral.

5.  Habilite la Federación XMPP en Lync Server 2013. 

6.  Actualice las entradas DNS para que apunten a la puerta de enlace de Lync Server 2013 XMPP.

</div>

<span> </span>

</div>

</div>

</div>

