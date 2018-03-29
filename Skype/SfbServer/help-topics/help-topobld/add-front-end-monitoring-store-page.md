---
title: Agregar Front-End de supervisión de página de tienda
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Puede definir el almacén de la supervisión de SQL Server mediante la configuración de las propiedades siguientes:'
ms.openlocfilehash: fe95cab603729736b0483774baa7111837a31c8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-monitoring-store-page"></a><span data-ttu-id="2b5f5-103">Agregar Front-End de supervisión de página de tienda</span><span class="sxs-lookup"><span data-stu-id="2b5f5-103">Add Front End Monitoring Store Page</span></span>
 
<span data-ttu-id="2b5f5-104">Puede **definir el almacén de la supervisión de SQL Server** mediante la configuración de las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b5f5-104">You **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="2b5f5-105">**Supervisión de SQL Server almacenar**: seleccione un nombre de dominio completo de SQL Server (y, opcionalmente, una instancia) de la lista.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (and, optionally an instance) from the list.</span></span>
    
    <span data-ttu-id="2b5f5-106">Haga clic en **nuevo** para crear una nueva definición del nombre de dominio completo de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-106">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="2b5f5-107">Active la casilla de verificación **Habilitar SQL Server almacén reflejo** si desea agregar el reflejo de base de datos para el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="2b5f5-108">Seleccione una **supervisión de SQL Server almacenar espejo** existente de la lista.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="2b5f5-109">Haga clic en **nuevo** para crear una nueva definición del nombre de dominio completo de SQL Server y, opcionalmente, un nombre de instancia para el almacén de espejo.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-109">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="2b5f5-110">Si ha seleccionado **Habilitar SQL Server almacén espejado**, seleccione opcionalmente **uso SQL Server reflejo testigo para habilitar la conmutación por error automática** para seleccionar un SQL Server reflejo auxiliar de almacén de la lista.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="2b5f5-111">Haga clic en **nuevo** para crear una nueva definición del nombre de dominio completo de SQL Server y, opcionalmente, un nombre de instancia para el almacén de testigo espejado.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-111">Click **New** to create a new SQL Server FQDN definition, and optionally an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="2b5f5-112">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="2b5f5-113">Una vez que haya terminado de especificar las opciones de este cuadro de diálogo continuar con la configuración, haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="2b5f5-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="2b5f5-114">Haga clic en **Cancelar** para descartar todos los cambios y finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="2b5f5-115">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="2b5f5-115">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b5f5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b5f5-116">See also</span></span>

#### 

[<span data-ttu-id="2b5f5-117">Asociar un almacén de supervisión con una agrupación de Front-End en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2b5f5-117">Associate a monitoring store with a Front End pool in Skype for Business Server 2015</span></span>](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)

