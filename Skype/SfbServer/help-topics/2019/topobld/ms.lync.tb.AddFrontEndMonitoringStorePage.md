---
title: Página Agregar almacén de supervisión de front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para Definir el almacén de SQL Server de supervisión, configure las propiedades siguientes:'
ms.openlocfilehash: e867ec998e1380e70125d0ad743f83b06737758e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811670"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="01d6d-103">Página Agregar almacén de supervisión de front-end</span><span class="sxs-lookup"><span data-stu-id="01d6d-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="01d6d-104">Para **Definir el almacén de SQL Server de supervisión**, configure las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="01d6d-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="01d6d-105">**Supervisión SQL Server almacén:** seleccione una SQL Server de dominio completo (y, opcionalmente, una instancia) de la lista.</span><span class="sxs-lookup"><span data-stu-id="01d6d-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="01d6d-106">Haga **clic en** Nuevo para crear una nueva definición SQL Server FQDN y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="01d6d-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="01d6d-107">Active la casilla SQL Server creación de **reflejos** del almacén si desea agregar la creación de reflejos de la base de datos para el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="01d6d-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="01d6d-108">Seleccione el **Reflejo del almacén SQL Server de supervisión** existente de la lista.</span><span class="sxs-lookup"><span data-stu-id="01d6d-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="01d6d-109">Haga **clic en** Nuevo para crear una nueva SQL Server FQDN y, opcionalmente, un nombre de instancia para el almacén reflejado.</span><span class="sxs-lookup"><span data-stu-id="01d6d-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="01d6d-110">Si seleccionó Habilitar la creación de reflejos del almacén de SQL Server **SQL Server,** opcionalmente seleccione Usar un testigo de creación de reflejo para habilitar la conmutación por error automática para seleccionar un almacén testigo de creación de reflejo de SQL Server en la lista. </span><span class="sxs-lookup"><span data-stu-id="01d6d-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="01d6d-111">Haga **clic** en Nuevo para crear una nueva SQL Server FQDN y, opcionalmente, un nombre de instancia para el almacén testigo de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="01d6d-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="01d6d-112">Haga clic en **Atrás** para volver al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="01d6d-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="01d6d-113">Haga clic en **Siguiente** una vez haya terminado de introducir las opciones de este cuadro de diálogo para proceder con la configuración.</span><span class="sxs-lookup"><span data-stu-id="01d6d-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="01d6d-114">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="01d6d-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="01d6d-115">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="01d6d-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="01d6d-116">Ver también</span><span class="sxs-lookup"><span data-stu-id="01d6d-116">See also</span></span>

[<span data-ttu-id="01d6d-117">Asociar un almacén de supervisión con un grupo de servidores front-end en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="01d6d-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
