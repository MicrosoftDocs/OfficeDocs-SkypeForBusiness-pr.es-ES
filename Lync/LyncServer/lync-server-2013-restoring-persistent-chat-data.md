---
title: 'Lync Server 2013: restauración de datos de chat persistentes'
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
ms.openlocfilehash: 5734296a9b3463740b28e6ead33cc64234640432
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Restauración de datos de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

El contenido del salón de chat persistente se almacena en la base de datos de chat persistente (MGC. MDF). Se debería realizar una copia de seguridad de estos datos importantes para la empresa de forma regular. Además del contenido del salón de chat, los principales (como usuarios y grupos), así como los roles y el acceso que tienen a los salones de chat y el contenido del salón de chat, también se almacenan en la base de datos de chat persistente.

La manera en que se restauran los datos del chat persistente depende del método que usó para realizar la copia de seguridad.

  - Si utilizó los procedimientos de copia de seguridad de SQL Server, necesita usar los procedimientos de restauración de SQL Server.

  - Si usó el cmdlet **Export-CsPersistentChatData** para realizar copias de seguridad de datos de chat persistentes, debe usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos.

</div>

<span> </span>

</div>

</div>

</div>

