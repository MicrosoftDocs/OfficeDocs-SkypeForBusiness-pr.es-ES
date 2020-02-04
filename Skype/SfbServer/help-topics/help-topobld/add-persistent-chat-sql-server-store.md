---
title: Agregar almacén SQL Server de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configure los almacenes de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o el grupo de servidores de chat persistente.
ms.openlocfilehash: 794ad4a1b5427fab7a8409fbbbd76448c33e918e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685063"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="6229a-103">Agregar almacén SQL Server de chat persistente</span><span class="sxs-lookup"><span data-stu-id="6229a-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="6229a-104">Configure los almacenes de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6229a-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="6229a-105">**Almacén de SQL Server**: Seleccione un SQL Server existente y, opcionalmente, una instancia para una conversación persistente.</span><span class="sxs-lookup"><span data-stu-id="6229a-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="6229a-106">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos persistentes del chat.</span><span class="sxs-lookup"><span data-stu-id="6229a-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="6229a-107">Seleccione la casilla habilitar el reflejo de la **tienda SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcione una base de datos espejada para los datos persistentes del chat.</span><span class="sxs-lookup"><span data-stu-id="6229a-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="6229a-108">Seleccione en la lista **reflejo de SQL Server** un SQL Server y una instancia opcional para actuar como SQL Server Mirror para el servidor SQL Server de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6229a-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="6229a-109">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el reflejo de SQL Server de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6229a-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="6229a-110">En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="6229a-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="6229a-111">El servidor testigo no refleja ni hospeda datos para los servidores de chat persistentes, pero garantiza que solo un SQL Server en una configuración duplicada es el servidor SQL activo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="6229a-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="6229a-112">Haga clic en **nuevo** para definir un nuevo testigo de SQL Server opcionalmente una instancia para el testigo de reflejo de SQL Server de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6229a-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="6229a-113">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6229a-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="6229a-114">Haga clic en **siguiente** cuando haya terminado de escribir las opciones para la configuración de la tienda SQL Server de este grupo y continúe con la definición del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6229a-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="6229a-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="6229a-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="6229a-116">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="6229a-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6229a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6229a-117">See also</span></span>

[<span data-ttu-id="6229a-118">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6229a-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="6229a-119">Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6229a-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="6229a-120">Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6229a-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="6229a-121">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6229a-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="6229a-122">Conceptos básicos de topología de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6229a-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="6229a-123">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="6229a-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
