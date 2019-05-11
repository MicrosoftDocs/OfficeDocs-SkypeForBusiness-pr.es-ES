---
title: Una revisión o actualización de un servidor Back-End o servidor Standard Edition en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumen: Obtenga información sobre cómo instalar una actualización o revisión en un servidor Back-End en Skype para Business Server.'
ms.openlocfilehash: d00f740ef328abe7a58a61d831c4fcd0eae93fc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911997"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="b110e-103">Una revisión o actualización de un servidor Back-End o servidor Standard Edition en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b110e-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="b110e-104">**Resumen:** Obtenga información sobre cómo instalar una actualización o revisión en un servidor Back-End en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b110e-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="b110e-105">En este tema se explica cómo instalar una actualización en un servidor de Enterprise Edition Back End o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b110e-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="b110e-106">Si un servidor Back-End está inactivo durante al menos 30 minutos mientras se está actualizando, los usuarios, a continuación, es posible que vaya a modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="b110e-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="b110e-107">Cuando finalice la actualización y los servidores Back-End nuevo se ha conectado con el servidor front-end del grupo de servidores, los usuarios se devuelven a la funcionalidad completa.</span><span class="sxs-lookup"><span data-stu-id="b110e-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="b110e-108">Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="b110e-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="b110e-109">Para actualizar un servidor back-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b110e-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="b110e-110">Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b110e-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="b110e-111">Descargue la actualización extráigala en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="b110e-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="b110e-112">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de Business Server**..</span><span class="sxs-lookup"><span data-stu-id="b110e-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="b110e-113">Detener Skype para servicios de Business Server.</span><span class="sxs-lookup"><span data-stu-id="b110e-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="b110e-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b110e-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="b110e-115">Detenga el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="b110e-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="b110e-116">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b110e-116">At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="b110e-117">Cierre todos los Skype para windows Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b110e-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="b110e-118">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="b110e-118">Install the update.</span></span>
    
8. <span data-ttu-id="b110e-119">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="b110e-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="b110e-120">Detener Skype para servicios de Business Server nuevo para detectar los ensamblados -d de la memoria caché de ensamblados Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="b110e-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="b110e-121">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b110e-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="b110e-p105">Reinicie el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b110e-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="b110e-124">Aplique los cambios realizados a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="b110e-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="b110e-125">Si se trata de un servidor de Enterprise Edition Back End y no existen bases de datos combinadas en este servidor, como el archivado o bases de datos de supervisión, a continuación, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b110e-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="b110e-126">Si se trata de un servidor de Enterprise Edition Back End y hay bases de datos combinadas en este servidor, a continuación, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b110e-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="b110e-127">Si se trata de un servidor Standard Edition, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b110e-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
