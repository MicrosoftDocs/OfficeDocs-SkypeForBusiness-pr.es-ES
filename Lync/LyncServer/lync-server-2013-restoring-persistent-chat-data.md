---
title: 'Lync Server 2013: restauración de datos de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38fe2e05629dea4b9194fdc0102d89232c3f6309
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Restauración de datos de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

El contenido del salón de chat persistente se almacena en la base de datos de chat persistente (MGC. MDF). Se trata de datos críticos para la empresa de los que se debe hacer una copia de seguridad de forma regular. Además del contenido del salón de chat, las entidades de identidad (como usuarios y grupos) y los roles y el acceso que tienen a los salones de chat y el contenido de los salones de chat, también se almacenan en la base de datos de chat persistente.

La forma de restaurar los datos de chat persistente depende del método que usó para realizar la copia de seguridad.

  - Si usó procedimientos de copia de seguridad de SQL Server, debe usar los procedimientos de restauración de SQL Server.

  - Si usó el cmdlet **Export-CsPersistentChatData** para hacer una copia de seguridad de los datos del chat persistente, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos.

</div>

<span> </span>

</div>

</div>

</div>

