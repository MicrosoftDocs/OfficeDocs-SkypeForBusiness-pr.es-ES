---
title: Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configurar el cumplimiento de normas de servidor de Chat persistente que almacenes de SQL Server o almacenes de SQL Server de cumplimiento de copia de seguridad que proporcionará bases de datos de copia de seguridad para el servidor de Chat persistente.
ms.openlocfilehash: 2142ef6eba84d0f6645d735c1117b0be07a2a84f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875598"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="9201b-103">Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente</span><span class="sxs-lookup"><span data-stu-id="9201b-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="9201b-104">Configurar el cumplimiento de normas de servidor de Chat persistente que almacenes de SQL Server o almacenes de SQL Server de cumplimiento de copia de seguridad que proporcionará bases de datos de copia de seguridad para el servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9201b-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="9201b-105">**Almacén de SQL Server**: seleccione un SQL Server existente y, opcionalmente, una instancia de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9201b-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="9201b-106">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de copia de seguridad de cumplimiento de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9201b-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="9201b-107">Seleccione la casilla de verificación de **la creación de reflejo de almacén de habilitar SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de copia de seguridad de cumplimiento de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9201b-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="9201b-108">Seleccione en la lista **almacén de SQL Server de reflejo** un SQL Server y una instancia opcional para actuar como el reflejo de SQL Server para la copia de seguridad cumplimiento de Chat persistente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9201b-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="9201b-109">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el servidor SQL de Chat persistente la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="9201b-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="9201b-110">En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="9201b-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="9201b-111">El servidor testigo realiza datos no reflejado o de host para los servidores de Chat persistente, pero garantiza que un solo servidor de SQL en una configuración duplicada es el servidor SQL activo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="9201b-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="9201b-112">Haga clic en **nuevo** para definir un nuevo testigo de SQL Server y, opcionalmente, una instancia de la copia de seguridad cumplimiento de Chat persistente testigo de reflejo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9201b-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="9201b-113">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="9201b-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="9201b-114">Haga clic en **siguiente** cuando haya terminado de introducir las opciones de configuración de almacén de SQL Server copia de seguridad de este grupo de servidores y para continuar con la definición de grupo de servidores de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9201b-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="9201b-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9201b-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="9201b-116">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="9201b-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9201b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9201b-117">See also</span></span>

[<span data-ttu-id="9201b-118">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9201b-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="9201b-119">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9201b-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="9201b-120">Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9201b-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="9201b-121">Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9201b-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="9201b-122">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9201b-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
