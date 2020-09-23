---
title: Página Agregar almacén de supervisión de front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Para Definir el almacén de SQL Server de supervisión, configure las propiedades siguientes:'
ms.openlocfilehash: 85b8518bb533de68423dea93f259fc7b927ed9ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218881"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="cb651-103">Página Agregar almacén de supervisión de front-end</span><span class="sxs-lookup"><span data-stu-id="cb651-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="cb651-104">Para **Definir el almacén de SQL Server de supervisión**, configure las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb651-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="cb651-105">**Supervisión del almacén de SQL Server**: Seleccione un nombre de dominio completo de SQL Server (y, opcionalmente, una instancia) de la lista.</span><span class="sxs-lookup"><span data-stu-id="cb651-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="cb651-106">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="cb651-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="cb651-107">Active la casilla **Habilitar la creación de reflejos del almacén de SQL Server** si desea agregar la creación de reflejo de la base de datos para el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="cb651-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="cb651-108">Seleccione el **Reflejo del almacén SQL Server de supervisión** existente de la lista.</span><span class="sxs-lookup"><span data-stu-id="cb651-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="cb651-109">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de reflejos.</span><span class="sxs-lookup"><span data-stu-id="cb651-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="cb651-110">Si seleccionó **Habilitar la creación de reflejos del almacén de SQL Server**, puede seleccionar usar el testigo de creación de reflejos de **SQL Server para habilitar la conmutación automática por error** para seleccionar un almacén de testigos de reflejo de SQL Server en la lista.</span><span class="sxs-lookup"><span data-stu-id="cb651-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="cb651-111">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén testigo de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="cb651-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="cb651-112">Haga clic en **Atrás** para volver al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="cb651-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="cb651-113">Haga clic en **Siguiente** una vez haya terminado de introducir las opciones de este cuadro de diálogo para proceder con la configuración.</span><span class="sxs-lookup"><span data-stu-id="cb651-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="cb651-114">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="cb651-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="cb651-115">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="cb651-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb651-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb651-116">See also</span></span>

[<span data-ttu-id="cb651-117">Asociar un almacén de supervisión a un grupo de servidores front-end en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="cb651-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
