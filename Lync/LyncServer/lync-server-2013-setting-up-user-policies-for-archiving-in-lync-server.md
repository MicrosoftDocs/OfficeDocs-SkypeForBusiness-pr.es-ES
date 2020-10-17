---
title: 'Lync Server 2013: configuración de directivas de usuario para archivado en Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee2074aa9608dad4adcfe85845e7b2e045276f59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497517"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Configuración de directivas de usuario para archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

La habilitación o deshabilitación del archivado para usuarios específicos hospedados en Lync Server 2013 requiere la creación y configuración de una o varias directivas de usuario y, a continuación, la aplicación de la directiva correspondiente a usuarios o grupos de usuarios específicos. Las directivas de usuario invalidan las directivas globales y de sitio, pero solo para los usuarios hospedados en Lync Server 2013.

Los usuarios siempre se hospedan en Lync Server. Si la integración de Microsoft Exchange está habilitada, los usuarios cuyos buzones estén en Microsoft Exchange Server 2013 no necesitan tener las directivas de archivado en Lync Server administradas. Los usuarios con archivado se administrarán con Exchange In-Place Hold.

Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planeación, la documentación sobre la implementación o las operaciones.

<div>


> [!NOTE]  
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios hospedados en Exchange 2013. El archivado para estos usuarios requiere que tengan sus buzones colocados en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.<BR>Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado. Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Creación y configuración de directivas de usuario para archivado en Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Aplicar una directiva de archivado de Lync Server a un usuario en Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

