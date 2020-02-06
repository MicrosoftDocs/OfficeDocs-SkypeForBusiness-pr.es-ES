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
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Para definir el almacén de SQL Server de supervisión, configure las siguientes propiedades:'
ms.openlocfilehash: 789083ad0743ed7baf94630c86e4647e218c336c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820862"
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="05c41-103">Página Agregar almacén de supervisión de front-end</span><span class="sxs-lookup"><span data-stu-id="05c41-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="05c41-104">Para **definir el almacén de SQL Server de supervisión** , configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c41-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="05c41-105">**Supervisar el almacén de SQL Server**: Seleccione un nombre de dominio completo de SQL Server (y, opcionalmente, una instancia) de la lista.</span><span class="sxs-lookup"><span data-stu-id="05c41-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="05c41-106">Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="05c41-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="05c41-107">Active la casilla de verificación Habilitar el reflejo de la **tienda de SQL Server** si quiere agregar reflejo de base de datos para el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="05c41-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="05c41-108">Seleccione en la lista un espejo de la **tienda SQL Server de supervisión** existente.</span><span class="sxs-lookup"><span data-stu-id="05c41-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="05c41-109">Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de reflejo.</span><span class="sxs-lookup"><span data-stu-id="05c41-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="05c41-110">Si seleccionó **Habilitar reflejo de la tienda SQL Server**, seleccione **usar el testigo de reflejo de SQL Server para habilitar la conmutación automática por error** para seleccionar un almacén testigo de reflejo de SQL Server de la lista.</span><span class="sxs-lookup"><span data-stu-id="05c41-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="05c41-111">Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="05c41-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="05c41-112">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="05c41-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="05c41-113">Cuando haya terminado de escribir las opciones de este cuadro de diálogo, haga clic en **siguiente** para continuar con la configuración.</span><span class="sxs-lookup"><span data-stu-id="05c41-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="05c41-114">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="05c41-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="05c41-115">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="05c41-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="05c41-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="05c41-116">See also</span></span>

[<span data-ttu-id="05c41-117">Asociación de un almacén de supervisión a un grupo de servidores front-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="05c41-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
