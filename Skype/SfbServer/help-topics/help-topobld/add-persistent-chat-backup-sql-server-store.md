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
description: Configurar los almacenes de copia de seguridad de SQL Server que proporcionan las bases de datos de copia de seguridad para el servidor de charla persistente o el grupo de servidores de charla persistente.
ms.openlocfilehash: 67dc09cca54f0079fc4b7bac16355bbd8dc64633
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="ab988-103">Agregar un almacén de SQL Server de copia de seguridad del chat persistente</span><span class="sxs-lookup"><span data-stu-id="ab988-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="ab988-104">Configurar los almacenes de copia de seguridad de SQL Server que proporcionan las bases de datos de copia de seguridad para el servidor de charla persistente o el grupo de servidores de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="ab988-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="ab988-105">**SQL Server almacenar**: seleccione una existente de SQL Server y, opcionalmente, una instancia de Chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="ab988-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="ab988-106">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia de la charla persistentes para datos de backup.</span><span class="sxs-lookup"><span data-stu-id="ab988-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="ab988-107">Seleccione la casilla de verificación **Habilitar SQL Server almacén espejado** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de backup Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ab988-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="ab988-108">Seleccione en la lista **almacén de creación de reflejos de SQL Server** un SQL Server y una instancia opcional para actuar como la duplicación de SQL Server para la copia de seguridad de SQL Server persistente Chat.</span><span class="sxs-lookup"><span data-stu-id="ab988-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="ab988-109">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el espejado de SQL Server persistente de Chat.</span><span class="sxs-lookup"><span data-stu-id="ab988-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="ab988-110">En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="ab988-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="ab988-111">El servidor testigo no no datos espejo o host para los servidores de charla persistente, pero asegura que sólo uno de SQL Server en una configuración duplicada es el activo de SQL Server en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="ab988-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="ab988-112">Haga clic en **nuevo** para definir a un nuevo testigo de SQL Server, opcionalmente, una instancia de la de la SQL Server backup Chat persistente que se reflejo a testigo.</span><span class="sxs-lookup"><span data-stu-id="ab988-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="ab988-113">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ab988-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ab988-114">Haga clic en **siguiente** cuando haya terminado de especificar las opciones de configuración del almacén de copia de seguridad de SQL Server de este grupo y continuar con la definición de grupo del servidor de Chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="ab988-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ab988-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir el nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="ab988-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ab988-116">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="ab988-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab988-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab988-117">See also</span></span>

#### 

[<span data-ttu-id="ab988-118">Plan para el servidor de charla persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ab988-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ab988-119">Requisitos del servidor para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ab988-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="ab988-120">Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ab988-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="ab988-121">Configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ab988-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

