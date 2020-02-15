---
title: 'Lync Server 2013: configuración de directivas de archivado para usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5adef442b4e890a8f157208aa6e7055725c014e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>Configuración de directivas de archivado para usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Puede habilitar o deshabilitar el archivado para usuarios específicos creando y configurando una directiva de archivado para los usuarios y, a continuación, aplicando la Directiva a usuarios o grupos de usuarios específicos. Las directivas de usuario invalidan la directiva global o las directivas de sitio. Las directivas de archivado solo se aplican si no se usa la integración de Microsoft Exchange o si se usa la integración de Microsoft Exchange, pero hay algunos usuarios que no están hospedados en Exchange 2013 y cuyos buzones se van a poner en conservación local.

Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.

<div>


> [!NOTE]  
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de conservación local de Exchange controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que tienen sus buzones en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.<BR>Debe especificar las opciones correctas en la configuración del archivado antes de habilitar el archivado de las comunicaciones internas o externas en las directivas de archivado. Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de directivas de usuario para archivado en Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [Configuración de directivas para el archivado en Lync Server 2013 al usar la integración de Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

