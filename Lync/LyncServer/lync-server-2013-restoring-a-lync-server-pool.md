---
title: 'Lync Server 2013: restauración de un grupo de servidores de Lync Server'
description: 'Lync Server 2013: restauración de un grupo de servidores de Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e92b4e7af9cf782d49c265425006e0118b9161
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543816"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a>Restauración de un grupo de servidores de Lync Server en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

La implementación de Lync Server puede incluir cualquiera de los siguientes tipos de grupos:

  - Servidor front-end

  - Servidor de mediación

  - Servidor de chat persistente

  - Servidor perimetral

Si un grupo completo experimenta una interrupción, siga estos procedimientos para cada servidor miembro del grupo.

  - Para un grupo de servidores front-end, restaure el servidor back-end en primer lugar y, a continuación, restaure cada servidor front-end. Para obtener más información, consulte [restaurar un servidor back-end de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) y [restaurar un servidor miembro de Enterprise Edition en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

  - En el resto de tipos de grupos, restaure cada uno de los servidores miembro. Para obtener más información, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

</div>

<span> </span>

</div>

</div>

</div>

