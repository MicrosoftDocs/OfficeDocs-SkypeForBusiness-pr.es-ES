---
title: Agregar almacén SQL Server de chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configurar los almacenes de SQL Server que proporcionan las bases de datos para el servidor de charla persistente o el grupo de servidores de charla persistente.
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="94266-103">Agregar almacén SQL Server de chat persistente</span><span class="sxs-lookup"><span data-stu-id="94266-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="94266-104">Configurar los almacenes de SQL Server que proporcionan las bases de datos para el servidor de charla persistente o el grupo de servidores de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="94266-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="94266-105">**SQL Server almacenar**: seleccione una existente de SQL Server y, opcionalmente, una instancia de Chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="94266-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="94266-106">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia de los datos persistentes de charla.</span><span class="sxs-lookup"><span data-stu-id="94266-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="94266-107">Seleccione la casilla de verificación **Habilitar SQL Server almacén espejado** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos persistentes de charla.</span><span class="sxs-lookup"><span data-stu-id="94266-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="94266-108">Seleccione en la lista **almacén de creación de reflejos de SQL Server** un SQL Server y una instancia opcional para actuar como la duplicación de SQL Server para la persistente de SQL Server de Chat.</span><span class="sxs-lookup"><span data-stu-id="94266-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="94266-109">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el espejado de SQL Server persistente de Chat.</span><span class="sxs-lookup"><span data-stu-id="94266-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="94266-110">En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="94266-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="94266-111">El servidor testigo no no datos espejo o host para los servidores de charla persistente, pero asegura que sólo uno de SQL Server en una configuración duplicada es el activo de SQL Server en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="94266-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="94266-112">Haga clic en **nuevo** para definir a un testigo SQL Server nuevo, opcionalmente, una instancia de testigo de creación de reflejos de SQL Server de Chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="94266-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="94266-113">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="94266-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="94266-114">Haga clic en **siguiente** cuando haya terminado de especificar las opciones de configuración del almacén de la agrupación de SQL Server y continuar con la definición de grupo del servidor de Chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="94266-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="94266-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir el nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="94266-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="94266-116">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="94266-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="94266-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="94266-117">See also</span></span>

#### 

[<span data-ttu-id="94266-118">Plan para el servidor de charla persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94266-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="94266-119">Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015</span><span class="sxs-lookup"><span data-stu-id="94266-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="94266-120">Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94266-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="94266-121">Requisitos del servidor para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94266-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="94266-122">Conceptos básicos de topología para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94266-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="94266-123">Configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94266-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

