---
title: Agregar almacén de SQL Server de copia de seguridad del chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure los almacenes de SQL Server de copia de seguridad que proporcionarán bases de datos de copia de seguridad para el servidor de chat persistente o el grupo de servidores de chat persistente.
ms.openlocfilehash: c21cd099372bb49b621447697320df2785a0c9dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818740"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="06719-103">Agregar almacén de la instancia de copia de seguridad de SQL Server del chat persistente</span><span class="sxs-lookup"><span data-stu-id="06719-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="06719-104">Configure los almacenes de SQL Server de copia de seguridad que proporcionarán bases de datos de copia de seguridad para el servidor de chat persistente o el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06719-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="06719-105">**SQL Server almacén:** seleccione una instancia SQL Server existente y, opcionalmente, una instancia para chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06719-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="06719-106">Haga **clic en** Nuevo para definir una nueva SQL Server y, opcionalmente, una nueva instancia para los datos de copia de seguridad de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06719-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="06719-107">Active la **casilla** SQL Server creación de reflejos del almacén para configurar una base de datos SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de copia de seguridad de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06719-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="06719-108">Seleccione en la lista Creación de **reflejos SQL Server** almacenar una instancia SQL Server y opcional para que actúe como el reflejo de SQL Server para la copia de seguridad de chat persistente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06719-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="06719-109">Haga **clic** en Nuevo para definir una nueva SQL Server y, opcionalmente, una nueva instancia para la creación de reflejos SQL Server chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06719-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="06719-110">En la lista **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** seleccione un SQL Server que actuará como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="06719-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="06719-111">El servidor testigo no refleja ni hospeda datos para los servidores de chat persistente, pero garantiza que solo un SQL Server en una configuración reflejada sea el servidor activo SQL Server en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="06719-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="06719-112">Haga **clic en** Nuevo para definir un nuevo testigo SQL Server, opcionalmente, una instancia para el testigo de copia de seguridad de chat SQL Server reflejo.</span><span class="sxs-lookup"><span data-stu-id="06719-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="06719-113">Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.</span><span class="sxs-lookup"><span data-stu-id="06719-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="06719-114">Haga **clic en** Siguiente una vez que haya terminado de especificar las opciones para la configuración del almacén de copia de seguridad SQL Server grupo de servidores y para continuar con la definición del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06719-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="06719-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="06719-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="06719-116">Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="06719-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="06719-117">Ver también</span><span class="sxs-lookup"><span data-stu-id="06719-117">See also</span></span>

[<span data-ttu-id="06719-118">Planear el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="06719-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="06719-119">Requisitos del servidor para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="06719-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="06719-120">Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="06719-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="06719-121">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="06719-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
