---
title: Esquema de la base de datos de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Esto documenta el esquema de la base de datos de chat persistente en Skype empresarial Server.
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295618"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="ef990-103">Esquema de la base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ef990-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="ef990-104">Esto documenta el esquema de la base de datos de chat persistente en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ef990-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="ef990-105">La base de datos de chat persistente se refiere a la base de datos correspondiente a las funciones del servidor back-end de Skype empresarial Server **PersistentChatStore** (correspondiente a la base de datos MGC) y **PersistentChatComplianceStore** (correspondiente al base de datos mgccomp).</span><span class="sxs-lookup"><span data-stu-id="ef990-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="ef990-106">El objetivo de publicar este esquema es permitirle crear consultas y obtener información útil para crear informes útiles sobre el uso de la conversación, las salas activas, los pósteres principales, etc.</span><span class="sxs-lookup"><span data-stu-id="ef990-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ef990-107">Nos reservamos el derecho de desarrollar este esquema.</span><span class="sxs-lookup"><span data-stu-id="ef990-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="ef990-108">Microsoft no ofrece ninguna garantía de mantener la compatibilidad total con este esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="ef990-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="ef990-109">Siga estos procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="ef990-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="ef990-110">No se\* admite Select//porque la lista de columnas puede crecer.</span><span class="sxs-lookup"><span data-stu-id="ef990-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="ef990-111">No se admiten modificaciones de esquema generadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ef990-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="ef990-112">No se admiten las operaciones de escritura.</span><span class="sxs-lookup"><span data-stu-id="ef990-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="ef990-113">Pruebe las consultas que cree en bases de datos de tamaño representativas para asegurarse de que las consultas pueden realizarse en un nivel que satisfaga sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="ef990-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="ef990-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ef990-114">In this section</span></span>

- [<span data-ttu-id="ef990-115">Lista de tablas de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ef990-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="ef990-116">Lista de tablas de cumplimiento del servidor de chat persistente en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ef990-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="ef990-117">Detalles de la tabla del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ef990-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="ef990-118">Consultas de base de datos del chat persistente de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef990-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

