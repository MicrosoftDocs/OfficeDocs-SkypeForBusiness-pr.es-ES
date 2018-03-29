---
title: Esquema de la base de datos de chat persistente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Esto documenta el esquema de la base de datos persistente Chat de Skype para Business Server.
ms.openlocfilehash: 1c78ea53438484fb0ad573a815c10ad76f08edca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="153d2-103">Esquema de la base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="153d2-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="153d2-104">Esto documenta el esquema de la base de datos persistente Chat de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="153d2-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="153d2-105">La base de datos persistente charla hace referencia a la base de datos correspondiente a la Skype para funciones de Business Server atrás End Server **PersistentChatStore** (correspondiente a la base de datos de CGM) y **PersistentChatComplianceStore** (correspondiente a la base de datos de mgccomp).</span><span class="sxs-lookup"><span data-stu-id="153d2-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="153d2-106">El objetivo de la publicación de este esquema es que le permite generar consultas y tener algunos conocimientos a la creación de informes útiles alrededor de uso de chat, salas de activos, publicadores principales y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="153d2-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="153d2-107">Nos reservamos el derecho a evolucionar este esquema.</span><span class="sxs-lookup"><span data-stu-id="153d2-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="153d2-108">Microsoft no realiza garantía alguna para mantener la compatibilidad completa con este esquema publicado.</span><span class="sxs-lookup"><span data-stu-id="153d2-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="153d2-109">Siga estas recomendaciones:</span><span class="sxs-lookup"><span data-stu-id="153d2-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="153d2-110">No seleccione\* / / se admite porque puede aumentar la lista de columnas.</span><span class="sxs-lookup"><span data-stu-id="153d2-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="153d2-111">No se admiten modificaciones de esquema generados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="153d2-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="153d2-112">No hay ninguna operación de escritura se admite.</span><span class="sxs-lookup"><span data-stu-id="153d2-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="153d2-113">Probar todas las consultas que se generación en tamaño representativo de bases de datos para asegurarse de que las consultas se pueden realizar en un nivel para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="153d2-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="153d2-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="153d2-114">In this section</span></span>

- [<span data-ttu-id="153d2-115">Lista de tablas del servidor de Chat persistentes</span><span class="sxs-lookup"><span data-stu-id="153d2-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="153d2-116">Lista de tablas de cumplimiento de normas de servidor de charla persistente en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="153d2-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="153d2-117">Detalles de tabla de servidor de charla persistentes</span><span class="sxs-lookup"><span data-stu-id="153d2-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="153d2-118">Ejemplos de consultas de base de datos persistente de charla</span><span class="sxs-lookup"><span data-stu-id="153d2-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

