---
title: Agregar supervisión de director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
ROBOTS: NOINDEX, NOFOLLOW
description: 'Puede definir el almacén de SQL Server de supervisión mediante la configuración de las siguientes propiedades:'
ms.openlocfilehash: 2a76c537912ae28513b1c9895b9e787de0e11eff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703205"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="6591f-103">Agregar supervisión de director</span><span class="sxs-lookup"><span data-stu-id="6591f-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="6591f-104">Puede **definir el almacén de SQL Server de supervisión** mediante la configuración de las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="6591f-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="6591f-105">**Supervisar el almacén de SQL Server**: seleccione de la lista un nombre de dominio completo (FQDN) de SQL Server (y, opcionalmente, una instancia de SQL Server con nombre).</span><span class="sxs-lookup"><span data-stu-id="6591f-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="6591f-106">Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="6591f-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="6591f-107">Active la casilla de verificación Habilitar el reflejo de la **tienda de SQL Server** si quiere agregar reflejo de base de datos para el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="6591f-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="6591f-108">Seleccione en la lista un espejo de la **tienda SQL Server de supervisión** existente.</span><span class="sxs-lookup"><span data-stu-id="6591f-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="6591f-109">Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de reflejo.</span><span class="sxs-lookup"><span data-stu-id="6591f-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="6591f-110">Si seleccionó **Habilitar reflejo de la tienda SQL Server**, seleccione **usar el testigo de reflejo de SQL Server para habilitar la conmutación automática por error** para seleccionar un almacén testigo de reflejo de SQL Server de la lista.</span><span class="sxs-lookup"><span data-stu-id="6591f-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="6591f-111">Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén testigo de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="6591f-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="6591f-112">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6591f-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="6591f-113">Cuando haya terminado de escribir las opciones de este cuadro de diálogo, haga clic en **siguiente** para continuar con la configuración.</span><span class="sxs-lookup"><span data-stu-id="6591f-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="6591f-114">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="6591f-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="6591f-115">Haga clic en **ayuda** para acceder a ayuda sensible al contexto, como esta página.</span><span class="sxs-lookup"><span data-stu-id="6591f-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

