---
title: Agregar almacén SQL Server de cumplimiento del chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Configure los almacenes de SQL Server de cumplimiento que proporcionarán bases de datos para el servidor de chat persistente o la característica de cumplimiento del servidor de chat persistente.
ms.openlocfilehash: 748fe7a0798bc8e10d3d10832763d5c3e1f55648
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218691"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a><span data-ttu-id="0e0ac-103">Agregar almacén SQL Server de cumplimiento del chat persistente</span><span class="sxs-lookup"><span data-stu-id="0e0ac-103">Add Persistent Chat Compliance SQL Server Store</span></span>
 
<span data-ttu-id="0e0ac-104">Configure los almacenes de SQL Server de cumplimiento que proporcionarán bases de datos para el servidor de chat persistente o la característica de cumplimiento del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-104">You configure the compliance SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server compliance feature.</span></span>
  
 <span data-ttu-id="0e0ac-105">**Almacén de SQL Server**: Seleccione un SQL Server existente y, opcionalmente, una instancia para chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="0e0ac-106">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="0e0ac-107">Active la casilla **Habilitar la creación de reflejos del almacén de SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcione una base de datos reflejada para los datos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat compliance data.</span></span>
  
<span data-ttu-id="0e0ac-108">Seleccione en la lista **reflejo de SQL** Server el almacén de SQL Server y una instancia opcional que actúe como el reflejo de SQL Server para el servidor SQL Server de cumplimiento del chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat compliance SQL Server.</span></span>
  
<span data-ttu-id="0e0ac-109">Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para la creación de reflejo de SQL Server de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="0e0ac-110">En la lista **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** seleccione un SQL Server que actuará como servidor testigo en casos de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="0e0ac-111">El servidor testigo no refleja ni hospeda datos para los servidores de chat persistente, pero garantiza que sólo un SQL Server en una configuración reflejada es el servidor SQL Server activo en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="0e0ac-112">Haga clic en **nuevo** para definir un nuevo testigo de SQL Server opcionalmente una instancia para el testigo de creación de reflejo de SQL Server de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="0e0ac-113">Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="0e0ac-114">Haga clic en **siguiente** cuando haya terminado de introducir las opciones de configuración del almacén de SQL Server de copia de seguridad de este grupo de servidores y continúe con la definición del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="0e0ac-115">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="0e0ac-116">Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="0e0ac-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e0ac-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e0ac-117">See also</span></span>

[<span data-ttu-id="0e0ac-118">Planeación del servidor de chat persistente en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e0ac-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="0e0ac-119">Requisitos de servidor para Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e0ac-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="0e0ac-120">Requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e0ac-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="0e0ac-121">Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e0ac-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
