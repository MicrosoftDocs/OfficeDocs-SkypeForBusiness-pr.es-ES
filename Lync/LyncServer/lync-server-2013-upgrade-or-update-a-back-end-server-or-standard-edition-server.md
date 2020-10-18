---
title: Actualizar o actualizar un servidor back-end o un servidor Standard Edition
description: Actualizar o actualizar un servidor back-end o un servidor Standard Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c529546bdcf88ada6fd82399d3b65b46b4312db0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580436"
---
# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f0800-103">Actualizar o actualizar un servidor back-end o un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0800-103">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0800-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f0800-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f0800-105">En este tema se explica cómo instalar una actualización en un servidor back-end de Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f0800-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="f0800-p101">Si un servidor back-end está inactivo al menos 30 minutos mientras se actualiza, los usuarios podrían entrar en modo de resistencia. Cuando termine la actualización y los servidores back-end se conecten de nuevo a los servidores front-end del grupo, los usuarios volverán al modo de funcionalidad total. Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="f0800-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="f0800-109">Para actualizar un servidor back-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f0800-109">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="f0800-110">Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f0800-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f0800-111">Descargue la actualización extráigala en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="f0800-111">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="f0800-112">Inicie el Shell de administración de Lync Server: Haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, a continuación, en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0800-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="f0800-p102">Detenga los servicios de Lync Server. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f0800-p102">Stop Lync Server services. At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="f0800-p103">Detenga el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f0800-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="f0800-117">Cierre todas las ventanas de el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0800-117">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="f0800-118">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="f0800-118">Install the update.</span></span>

8.  <span data-ttu-id="f0800-119">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0800-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="f0800-p104">Vuelva a detener los servicios de Lync Server para capturar ensamblados -d de la caché global de ensamblados (GAC). En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f0800-p104">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies. At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="f0800-p105">Reinicie el servicio World Wide Web. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f0800-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="f0800-124">Aplique los cambios realizados por LyncServerUpdateInstaller.exe a las bases de datos de SQL Server mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="f0800-124">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="f0800-125">Si este es un servidor back-end de Enterprise Edition y no hay bases de datos combinadas en este servidor, como las bases de datos de archivado o supervisión, escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="f0800-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="f0800-126">Si este es un servidor back-end Enterprise Edition y hay bases de datos combinadas en este servidor, escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="f0800-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="f0800-127">Si se trata de un servidor Standard Edition, escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="f0800-127">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

