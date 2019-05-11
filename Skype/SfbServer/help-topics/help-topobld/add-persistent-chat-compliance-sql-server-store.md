---
title: Agregar almacén SQL Server de cumplimiento del chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Configurar los almacenes de SQL Server de cumplimiento que proporcionará bases de datos para el servidor de Chat persistente o la característica de cumplimiento del servidor de Chat persistente.
ms.openlocfilehash: 02caeac7641cd592f6ca16d1e739253b0f48a30d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897628"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="7ef4f-103">Agregar almacén SQL Server de cumplimiento del chat persistente</span><span class="sxs-lookup"><span data-stu-id="7ef4f-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="7ef4f-104">Configurar los almacenes de SQL Server de cumplimiento que proporcionará bases de datos para el servidor de Chat persistente o la característica de cumplimiento del servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="7ef4f-105">**Almacén de SQL Server**: seleccione un SQL Server existente y, opcionalmente, una instancia de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="7ef4f-106">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de cumplimiento de normas de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="7ef4f-107">Seleccione la casilla de verificación de **la creación de reflejo de almacén de habilitar SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de cumplimiento de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="7ef4f-108">Seleccione en la lista **almacén de SQL Server de reflejo** un SQL Server y una instancia opcional para actuar como el reflejo de SQL Server para el cumplimiento de Chat persistente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="7ef4f-109">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el servidor SQL de Chat persistente la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="7ef4f-110">En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="7ef4f-111">El servidor testigo realiza datos no reflejado o de host para los servidores de Chat persistente, pero garantiza que un solo servidor de SQL en una configuración duplicada es el servidor SQL activo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="7ef4f-112">Haga clic en **nuevo** para definir un nuevo testigo de SQL Server y, opcionalmente, una instancia para el testigo de reflejo de SQL Server de cumplimiento de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="7ef4f-113">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="7ef4f-114">Haga clic en **siguiente** cuando haya terminado de introducir las opciones de configuración de almacén de SQL Server copia de seguridad de este grupo de servidores y para continuar con la definición de grupo de servidores de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="7ef4f-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="7ef4f-116">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="7ef4f-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ef4f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ef4f-117">See also</span></span>

[<span data-ttu-id="7ef4f-118">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ef4f-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7ef4f-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ef4f-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="7ef4f-120">Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ef4f-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="7ef4f-121">Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7ef4f-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
