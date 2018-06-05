---
title: Revisar o actualizar un servidor back-end o un servidor Standard Edition en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: Obtenga información sobre cómo instalar una actualización o revisión en un servidor Back-End en Skype para Business Server.'
ms.openlocfilehash: 40437deb77fc5b212a6c579030ed77939c421050
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569382"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ac66a-103">Revisar o actualizar un servidor back-end o un servidor Standard Edition en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ac66a-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ac66a-104">**Resumen:** Obtenga información sobre cómo instalar una actualización o revisión en un servidor Back-End en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="ac66a-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="ac66a-105">En este tema se explica cómo instalar una actualización en un servidor de Enterprise Edition Back End o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ac66a-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="ac66a-106">Si un servidor Back-End está inactivo durante al menos 30 minutos mientras se está actualizando, los usuarios, a continuación, es posible que vaya a modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="ac66a-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="ac66a-107">Cuando finalice la actualización y los servidores Back-End nuevo se ha conectado con el servidor front-end del grupo de servidores, los usuarios se devuelven a la funcionalidad completa.</span><span class="sxs-lookup"><span data-stu-id="ac66a-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="ac66a-108">Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="ac66a-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="ac66a-109">Para actualizar un servidor back-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ac66a-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="ac66a-110">Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ac66a-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="ac66a-111">Descargue la actualización extráigala en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="ac66a-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="ac66a-112">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para profesionales de 2015**y, a continuación, haga clic en **Skype para Shell de administración de Business Server**..</span><span class="sxs-lookup"><span data-stu-id="ac66a-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="ac66a-113">Detener Skype para servicios de Business Server.</span><span class="sxs-lookup"><span data-stu-id="ac66a-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="ac66a-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="ac66a-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="ac66a-p103">Detenga el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="ac66a-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="ac66a-117">Cierre todos los Skype para windows Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ac66a-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="ac66a-118">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="ac66a-118">Install the update.</span></span>
    
8. <span data-ttu-id="ac66a-119">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para profesionales de 2015**y, a continuación, haga clic en **Skype para Shell de administración de Business Server**..</span><span class="sxs-lookup"><span data-stu-id="ac66a-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
9. <span data-ttu-id="ac66a-120">Detener Skype para servicios de Business Server nuevo para detectar los ensamblados -d de la memoria caché de ensamblados Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="ac66a-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="ac66a-121">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="ac66a-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="ac66a-p105">Reinicie el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="ac66a-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="ac66a-124">Aplique los cambios realizados a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="ac66a-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="ac66a-125">Si se trata de un servidor de Enterprise Edition Back End y no existen bases de datos combinadas en este servidor, como el archivado o bases de datos de supervisión, a continuación, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="ac66a-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="ac66a-126">Si se trata de un servidor de Enterprise Edition Back End y hay bases de datos combinadas en este servidor, a continuación, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="ac66a-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="ac66a-127">Si se trata de un servidor Standard Edition, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="ac66a-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```