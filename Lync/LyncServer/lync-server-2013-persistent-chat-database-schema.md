---
title: 'Lync Server 2013: Esquema de la base de datos de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Esquema de la base de datos de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-18_

Esto documenta el esquema de la base de datos de chat persistente en el software de comunicaciones de Lync Server 2013.

La base de datos de chat persistente se refiere a la base de datos correspondiente a las funciones de servidor de **PersistentChatStore** back-end de Lync Server 2013 (correspondiente a la base de datos MGC) y **PersistentChatComplianceStore** (correspondiente a la mgccomp base de datos). El objetivo de publicar este esquema es permitirle crear consultas y obtener información útil para crear informes útiles sobre el uso de la conversación, las salas activas, los pósteres principales, etc.

<div>


> [!IMPORTANT]  
> Nos reservamos el derecho de desarrollar este esquema. Microsoft no ofrece ninguna garantía de mantener la compatibilidad total con este esquema publicado.



</div>

Siga estos procedimientos recomendados:

  - No se\* admite Select//porque la lista de columnas puede crecer.

  - No se admiten modificaciones de esquema generadas por el usuario.

  - No se admiten las operaciones de escritura.

  - Pruebe las consultas que cree en bases de datos de tamaño representativas para asegurarse de que las consultas pueden realizarse en un nivel que satisfaga sus necesidades.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Lista de tablas de servidores de chat persistente en Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Detalles de la tabla del servidor de chat persistente en Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Consultas de base de datos del chat persistente de ejemplo para Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

