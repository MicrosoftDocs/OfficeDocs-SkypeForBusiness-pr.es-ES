---
title: Revisión o actualización de un servidor back-end o un servidor Standard Edition en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: obtenga información sobre cómo instalar una actualización o revisión en un servidor back-end en Skype Empresarial Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826310"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="c8e32-103">Revisión o actualización de un servidor back-end o un servidor Standard Edition en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c8e32-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="c8e32-104">**Resumen:** Obtenga información sobre cómo instalar una actualización o revisión en un servidor back-end en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c8e32-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="c8e32-105">En este tema se explica cómo instalar una actualización en un servidor back-end Enterprise Edition o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c8e32-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="c8e32-p101">Si un servidor back-end está inactivo al menos 30 minutos mientras se actualiza, los usuarios podrían entrar en modo de resistencia. Cuando termine la actualización y los servidores back-end se conecten de nuevo a los servidores front-end del grupo, los usuarios volverán al modo de funcionalidad total. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="c8e32-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="c8e32-109">Para actualizar un servidor back-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c8e32-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="c8e32-110">Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c8e32-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="c8e32-111">Descargue la actualización extráigala en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="c8e32-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="c8e32-112">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="c8e32-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="c8e32-113">Detenga los servicios de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c8e32-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="c8e32-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8e32-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="c8e32-115">Detenga el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="c8e32-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="c8e32-116">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8e32-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="c8e32-117">Cierre todas las ventanas del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c8e32-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="c8e32-118">Instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="c8e32-118">Install the update.</span></span>
    
8. <span data-ttu-id="c8e32-119">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="c8e32-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="c8e32-120">Vuelva a detener los servicios de Skype Empresarial Server para capturar ensamblados -d de caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="c8e32-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="c8e32-121">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8e32-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="c8e32-122">Reinicie el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="c8e32-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="c8e32-123">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="c8e32-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="c8e32-124">Aplique los cambios realizados a las bases SQL Server de datos mediante una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c8e32-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="c8e32-125">Si se trata de un servidor back-end Enterprise Edition y no hay bases de datos en este servidor, como bases de datos de archivado o supervisión, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="c8e32-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="c8e32-126">Si se trata de un servidor back-end Enterprise Edition y hay bases de datos colocadas en este servidor, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="c8e32-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="c8e32-127">Si se trata de un servidor Standard Edition, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="c8e32-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
