---
title: Página Agregar almacén de supervisión de front-end
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir el almacén de SQL Server de supervisión mediante la configuración de las siguientes propiedades:'
ms.openlocfilehash: 2de5788c52f91a2ef2395aaa3c1f580170f1c765
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896843"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="a39b7-103">Página Agregar almacén de supervisión de front-end</span><span class="sxs-lookup"><span data-stu-id="a39b7-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="a39b7-104">Para **definir el almacén de SQL Server de supervisión** mediante la configuración de las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="a39b7-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="a39b7-105">**Almacén de SQL Server de supervisión**: seleccione un nombre de dominio completo de SQL Server (y, opcionalmente, una instancia) de la lista.</span><span class="sxs-lookup"><span data-stu-id="a39b7-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="a39b7-106">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a39b7-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="a39b7-107">Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea agregar la creación de reflejos de base de datos para el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="a39b7-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="a39b7-108">Seleccione un **reflejo de almacén de SQL Server de supervisión** existente de la lista.</span><span class="sxs-lookup"><span data-stu-id="a39b7-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="a39b7-109">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de reflejo.</span><span class="sxs-lookup"><span data-stu-id="a39b7-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="a39b7-110">Si seleccionó **la creación de reflejo de almacén de habilitar SQL Server**, seleccione opcionalmente **testigo para habilitar la conmutación por error automática de reflejo de utilizar SQL Server** para seleccionar un almacén de testigos de la lista de la creación de reflejos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a39b7-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="a39b7-111">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="a39b7-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="a39b7-112">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a39b7-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="a39b7-113">Haga clic en **siguiente** cuando haya terminado de introducir las opciones de este cuadro de diálogo continuar con la configuración.</span><span class="sxs-lookup"><span data-stu-id="a39b7-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="a39b7-114">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="a39b7-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="a39b7-115">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="a39b7-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a39b7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a39b7-116">See also</span></span>

[<span data-ttu-id="a39b7-117">Asociar un almacén de supervisión a un grupo de servidores Front-End en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a39b7-117">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span>](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
