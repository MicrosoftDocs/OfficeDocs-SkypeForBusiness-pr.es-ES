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
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="04644-103">Esquema de base de datos de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04644-103">Persistent Chat database schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04644-104">_**Última modificación del tema:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="04644-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="04644-105">Esto documenta el esquema de la base de datos de chat persistente en el software de comunicaciones Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04644-105">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="04644-106">La base de datos de chat persistente hace referencia a la base de datos correspondiente a **las funciones de** servidor back-end 2013 de Lync Server (correspondiente a la base de datos MGC) y **PersistentChatComplianceStore** (correspondiente a la base de datos mgccomp).</span><span class="sxs-lookup"><span data-stu-id="04644-106">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="04644-107">El objetivo de la publicación de este esquema es permitirle crear consultas y obtener información sobre cómo crear informes útiles sobre el uso de chat, las salas activas, los pósteres principales, etc.</span><span class="sxs-lookup"><span data-stu-id="04644-107">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="04644-108">Nos reservamos el derecho de desarrollar este esquema.</span><span class="sxs-lookup"><span data-stu-id="04644-108">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="04644-109">Microsoft no garantiza ninguna garantía para mantener la compatibilidad completa con versiones anteriores con este esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="04644-109">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="04644-110">Siga estos procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="04644-110">Follow these best practices:</span></span>

  - <span data-ttu-id="04644-111">No \* se admite Select//porque la lista de columnas puede crecer.</span><span class="sxs-lookup"><span data-stu-id="04644-111">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="04644-112">No se admiten modificaciones de esquema generadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="04644-112">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="04644-113">No se admiten las operaciones de escritura.</span><span class="sxs-lookup"><span data-stu-id="04644-113">No write operations are supported.</span></span>

  - <span data-ttu-id="04644-114">Pruebe las consultas que cree en bases de datos de tamaño representativo para asegurarse de que las consultas pueden realizarse en un nivel para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="04644-114">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="04644-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="04644-115">In This Section</span></span>

  - [<span data-ttu-id="04644-116">Lista de tablas del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04644-116">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="04644-117">Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04644-117">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="04644-118">Detalles de la tabla del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04644-118">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="04644-119">Consultas de base de datos de chat persistente de ejemplo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04644-119">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

