---
title: Aplicar revisiones o actualizar un servidor de servicios de fondo o un servidor Standard Edition en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: Aprenda a instalar una actualización o una revisión en un servidor back-end de Skype empresarial Server.'
ms.openlocfilehash: 62c7a0c2e0c958e9f3e6c566d9e73a35d1dd945a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817101"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="5abfe-103">Aplicar revisiones o actualizar un servidor de servicios de fondo o un servidor Standard Edition en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5abfe-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="5abfe-104">**Resumen:** Obtenga información sobre cómo instalar una actualización o una revisión en un servidor back-end en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5abfe-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="5abfe-105">En este tema se explica cómo instalar una actualización en un servidor de servicios de fondo Enterprise Edition o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5abfe-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="5abfe-106">Si un servidor back-end está desactivado durante al menos 30 minutos mientras lo está actualizando, los usuarios pueden entrar en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="5abfe-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="5abfe-107">Cuando la actualización se ha completado y los servidores back-end se han conectado de nuevo con los servidores front-end en el grupo, los usuarios se devuelven a la funcionalidad completa.</span><span class="sxs-lookup"><span data-stu-id="5abfe-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="5abfe-108">Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="5abfe-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="5abfe-109">Para actualizar un servidor back-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5abfe-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="5abfe-110">Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5abfe-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="5abfe-111">Descargue la actualización extráigala en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="5abfe-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="5abfe-112">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="5abfe-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="5abfe-113">Detenga los servicios de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5abfe-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="5abfe-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="5abfe-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="5abfe-115">Detenga el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="5abfe-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="5abfe-116">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="5abfe-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="5abfe-117">Cierre todas las ventanas de Shell de administración de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="5abfe-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="5abfe-118">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="5abfe-118">Install the update.</span></span>
    
8. <span data-ttu-id="5abfe-119">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="5abfe-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="5abfe-120">Detenga de nuevo los servicios de Skype empresarial Server para capturar los ensamblados de la caché de ensamblados global (GAC)-d.</span><span class="sxs-lookup"><span data-stu-id="5abfe-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="5abfe-121">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="5abfe-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="5abfe-p105">Reinicie el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="5abfe-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="5abfe-124">Aplique los cambios realizados a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="5abfe-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="5abfe-125">Si se trata de un servidor de servicios de fondo Enterprise Edition y no hay bases de datos colocadas en este servidor, como archivar o supervisar bases de datos, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="5abfe-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="5abfe-126">Si se trata de un servidor de servicios de fondo Enterprise Edition y hay bases de datos colocadas en este servidor, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="5abfe-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="5abfe-127">Si se trata de un servidor Standard Edition, escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="5abfe-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
