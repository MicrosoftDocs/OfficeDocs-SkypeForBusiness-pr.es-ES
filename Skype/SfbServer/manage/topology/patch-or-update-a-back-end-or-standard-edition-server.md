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
description: 'Resumen: Conozca cómo instalar una actualización o una revisión en un servidor de fondo detrás de Skype para Business Server.'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a><span data-ttu-id="155fe-103">Revisar o actualizar un servidor back-end o un servidor Standard Edition en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="155fe-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="155fe-104">**Resumen:** Obtenga información acerca de cómo instalar una actualización o una revisión en un servidor de fondo detrás de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="155fe-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="155fe-105">Este tema explica cómo instalar una actualización en un servidor de Enterprise Edition atrás final o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="155fe-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="155fe-106">Si un servidor de fondo atrás está inactivo durante al menos 30 minutos mientras se está actualizando, los usuarios pueden vaya al modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="155fe-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="155fe-107">Cuando finalice la actualización y los servidores de fondo detrás otra vez ha conectado con los servidores frontales en el grupo, los usuarios se devuelven a la funcionalidad completa.</span><span class="sxs-lookup"><span data-stu-id="155fe-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="155fe-108">Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="155fe-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="155fe-109">Para actualizar un servidor back-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="155fe-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="155fe-110">Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="155fe-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="155fe-111">Descargue la actualización extráigala en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="155fe-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="155fe-112">Iniciar el Skype para el Shell de administración de servidor empresarial: haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para negocios 2015**y, a continuación, haga clic en **Skype para el Shell de administración de servidor de Business**..</span><span class="sxs-lookup"><span data-stu-id="155fe-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="155fe-113">Dejar de Skype para Business Server services.</span><span class="sxs-lookup"><span data-stu-id="155fe-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="155fe-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="155fe-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="155fe-p103">Detenga el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="155fe-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="155fe-117">Cierre todos los Skype para windows de Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="155fe-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="155fe-118">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="155fe-118">Install the update.</span></span>
    
8. <span data-ttu-id="155fe-119">Iniciar el Skype para el Shell de administración de servidor empresarial: haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para negocios 2015**y, a continuación, haga clic en **Skype para el Shell de administración de servidor de Business**..</span><span class="sxs-lookup"><span data-stu-id="155fe-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
9. <span data-ttu-id="155fe-120">Dejar de Skype para servicios Business Server nuevo para detectar -d ensamblados de la caché de ensamblados Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="155fe-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="155fe-121">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="155fe-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="155fe-p105">Reinicie el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="155fe-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="155fe-124">Aplique los cambios realizados a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="155fe-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="155fe-125">Si se trata de un servidor de Enterprise Edition atrás final y no existen bases de datos colocadas en este servidor, como el archivado o bases de datos de supervisión, a continuación, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="155fe-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="155fe-126">Si se trata de un servidor de Enterprise Edition atrás final y hay colocadas las bases de datos en este servidor, a continuación, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="155fe-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="155fe-127">Si se trata de un servidor Standard Edition, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="155fe-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


