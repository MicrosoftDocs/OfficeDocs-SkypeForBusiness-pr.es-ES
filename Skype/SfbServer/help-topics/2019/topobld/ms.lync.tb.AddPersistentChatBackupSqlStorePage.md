---
title: Agregar un almacén de SQL Server de copia de seguridad del chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configurar los almacenes de SQL Server de reserva que proporcionarán bases de datos de copia de seguridad para el servidor de Chat persistente o grupo de servidores de Chat persistente.
ms.openlocfilehash: 67dc09cca54f0079fc4b7bac16355bbd8dc64633
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="66aa8-103">Agregar un almacén de SQL Server de copia de seguridad del chat persistente</span><span class="sxs-lookup"><span data-stu-id="66aa8-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="66aa8-104">Configurar los almacenes de SQL Server de reserva que proporcionarán bases de datos de copia de seguridad para el servidor de Chat persistente o grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="66aa8-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="66aa8-105">**Almacén de SQL Server**: seleccione un SQL Server existente y, opcionalmente, una instancia de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="66aa8-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="66aa8-106">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de copia de seguridad de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="66aa8-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="66aa8-107">Seleccione la casilla de verificación de **la creación de reflejo de almacén de habilitar SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de copia de seguridad de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="66aa8-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="66aa8-108">Seleccione en la lista **almacén de SQL Server de reflejo** un SQL Server y una instancia opcional para que actúen como reflejo de SQL Server para el servidor SQL de copia de seguridad de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="66aa8-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="66aa8-109">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el servidor SQL de Chat persistente la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="66aa8-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="66aa8-110">En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="66aa8-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="66aa8-111">El servidor testigo realiza datos no reflejado o de host para los servidores de Chat persistente, pero garantiza que un solo servidor de SQL en una configuración duplicada es el servidor SQL activo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="66aa8-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="66aa8-112">Haga clic en **nuevo** para definir un nuevo testigo de SQL Server y, opcionalmente, una instancia para el Chat persistente copia de seguridad SQL Server testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="66aa8-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="66aa8-113">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="66aa8-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="66aa8-114">Haga clic en **siguiente** cuando haya terminado de introducir las opciones de configuración de almacén de SQL Server copia de seguridad de este grupo de servidores y para continuar con la definición de grupo de servidores de servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="66aa8-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="66aa8-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir el nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="66aa8-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="66aa8-116">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="66aa8-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66aa8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="66aa8-117">See also</span></span>

#### 

[<span data-ttu-id="66aa8-118">Planeación de servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66aa8-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="66aa8-119">Requisitos de servidor de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66aa8-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="66aa8-120">Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66aa8-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="66aa8-121">Configuración de alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66aa8-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

