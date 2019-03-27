---
title: Esquema de la base de datos de chat persistente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Documenta el esquema de la base de datos de Chat persistente en Skype para Business Server.
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874061"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="9ac4b-103">Esquema de la base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9ac4b-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="9ac4b-104">Documenta el esquema de la base de datos de Chat persistente en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="9ac4b-105">La base de datos de Chat persistente hace referencia a la base de datos correspondiente a la Skype para funciones de servidor de Business Server Back-End **PersistentChatStore** (correspondiente a la base de datos de CGM) y **PersistentChatComplianceStore** (correspondiente a la base de datos de mgccomp).</span><span class="sxs-lookup"><span data-stu-id="9ac4b-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="9ac4b-106">El objetivo de este esquema de publicación es que le permite generar consultas y obtener algunos entendimiento de creación de informes útiles alrededor de uso de chat, salones de activos, Pósteres superiores y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9ac4b-107">Nos reservamos el derecho a evolucionar este esquema.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="9ac4b-108">Microsoft no realiza ninguna garantía para mantener la compatibilidad con versiones anteriores completa con este esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="9ac4b-109">Siga estos procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="9ac4b-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="9ac4b-110">No seleccione\* / / se admite porque la lista de columnas puede crecer.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="9ac4b-111">No se admiten modificaciones del esquema generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="9ac4b-112">No hay ninguna operación de escritura se admite.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="9ac4b-113">Pruebe las consultas que genere sobre bases de datos de tamaño representativo para asegurarse de que las consultas se pueden realizar a un nivel para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="9ac4b-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="9ac4b-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9ac4b-114">In this section</span></span>

- [<span data-ttu-id="9ac4b-115">Lista de tablas de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9ac4b-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="9ac4b-116">Lista de tablas de cumplimiento del servidor de Chat persistente en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="9ac4b-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="9ac4b-117">Detalles de la tabla del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9ac4b-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="9ac4b-118">Consultas de base de datos del chat persistente de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ac4b-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

