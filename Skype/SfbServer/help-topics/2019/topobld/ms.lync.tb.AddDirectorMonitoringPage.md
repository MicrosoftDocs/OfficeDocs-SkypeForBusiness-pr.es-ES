---
title: Agregar supervisión de director
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
ROBOTS: NOINDEX, NOFOLLOW
description: 'Puede definir el almacén de SQL Server de supervisión mediante la configuración de las siguientes propiedades:'
ms.openlocfilehash: 4ba52c49cc9d851df9d6fa53220cf81d70967e75
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202313"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="45db8-103">Agregar supervisión de director</span><span class="sxs-lookup"><span data-stu-id="45db8-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="45db8-104">Se puede **definir el almacén de SQL Server de supervisión** mediante la configuración de las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="45db8-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="45db8-105">**Almacén de SQL Server de supervisión**: seleccione un nombre de dominio completo (FQDN) de SQL Server (y, opcionalmente, una instancia de SQL Server con nombre) de la lista.</span><span class="sxs-lookup"><span data-stu-id="45db8-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="45db8-106">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="45db8-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="45db8-107">Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea agregar la creación de reflejos de base de datos para el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="45db8-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="45db8-108">Seleccione un **reflejo de almacén de SQL Server de supervisión** existente de la lista.</span><span class="sxs-lookup"><span data-stu-id="45db8-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="45db8-109">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de reflejo.</span><span class="sxs-lookup"><span data-stu-id="45db8-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="45db8-110">Si seleccionó **la creación de reflejo de almacén de habilitar SQL Server**, seleccione opcionalmente **testigo para habilitar la conmutación por error automática de reflejo de utilizar SQL Server** para seleccionar un almacén de testigos de la lista de la creación de reflejos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45db8-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="45db8-111">Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén testigo de reflejo.</span><span class="sxs-lookup"><span data-stu-id="45db8-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="45db8-112">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="45db8-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="45db8-113">Haga clic en **siguiente** cuando haya terminado de introducir las opciones de este cuadro de diálogo continuar con la configuración.</span><span class="sxs-lookup"><span data-stu-id="45db8-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="45db8-114">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="45db8-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="45db8-115">Haga clic en **Ayuda** para obtener acceso a la Ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="45db8-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

