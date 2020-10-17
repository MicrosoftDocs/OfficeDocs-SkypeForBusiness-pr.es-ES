---
title: 'Lync Server 2013: esquema de base de datos de chat persistente'
description: 'Lync Server 2013: esquema de la base de datos de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66151201f65310cc8e6d3f2251be4f86ce2be15d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545156"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Esquema de base de datos de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-18_

Esto documenta el esquema de la base de datos de chat persistente en el software de comunicaciones Lync Server 2013.

La base de datos de chat persistente hace referencia a la base de datos correspondiente a **las funciones de** servidor back-end 2013 de Lync Server (correspondiente a la base de datos MGC) y **PersistentChatComplianceStore** (correspondiente a la base de datos mgccomp). El objetivo de la publicación de este esquema es permitirle crear consultas y obtener información sobre cómo crear informes útiles sobre el uso de chat, las salas activas, los pósteres principales, etc.

<div>


> [!IMPORTANT]  
> Nos reservamos el derecho de desarrollar este esquema. Microsoft no garantiza ninguna garantía para mantener la compatibilidad completa con versiones anteriores con este esquema publicado.



</div>

Siga estos procedimientos recomendados:

  - No \* se admite Select//porque la lista de columnas puede crecer.

  - No se admiten modificaciones de esquema generadas por el usuario.

  - No se admiten las operaciones de escritura.

  - Pruebe las consultas que cree en bases de datos de tamaño representativo para asegurarse de que las consultas pueden realizarse en un nivel para satisfacer sus necesidades.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Lista de tablas del servidor de chat persistente en Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Detalles de la tabla del servidor de chat persistente en Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Consultas de base de datos de chat persistente de ejemplo para Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

