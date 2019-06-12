---
title: Actualizar o actualizar un servidor de servicios de fondo o un servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="38c06-102">Actualizar o actualizar un servidor de servicios de fondo o un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38c06-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38c06-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="38c06-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="38c06-104">En este tema se explica cómo instalar una actualización en un servidor de servicios de fondo Enterprise Edition o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="38c06-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="38c06-105">Si un servidor back-end está desactivado durante al menos 30 minutos mientras lo está actualizando, los usuarios pueden entrar en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="38c06-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="38c06-106">Cuando la actualización se ha completado y los servidores back-end se han conectado de nuevo con los servidores front-end en el grupo, los usuarios se devuelven a la funcionalidad completa.</span><span class="sxs-lookup"><span data-stu-id="38c06-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="38c06-107">Si la actualización dura menos de 30 minutos, los usuarios no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="38c06-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="38c06-108">Para actualizar un servidor back-end o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="38c06-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="38c06-109">Inicie sesión en el servidor que desea actualizar como miembro del rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="38c06-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="38c06-110">Descargue la actualización extráigala en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="38c06-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="38c06-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38c06-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="38c06-112">Detenga los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38c06-112">Stop Lync Server services.</span></span> <span data-ttu-id="38c06-113">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="38c06-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="38c06-114">Detenga el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="38c06-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="38c06-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="38c06-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="38c06-116">Cierre todas las ventanas del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38c06-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="38c06-117">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="38c06-117">Install the update.</span></span>

8.  <span data-ttu-id="38c06-118">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38c06-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="38c06-119">Detenga de nuevo los servicios de Lync Server para capturar los ensamblados de caché global de ensamblados (GAC): d.</span><span class="sxs-lookup"><span data-stu-id="38c06-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="38c06-120">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="38c06-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="38c06-121">Reinicie el servicio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="38c06-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="38c06-122">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="38c06-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="38c06-123">Aplique los cambios realizados por LyncServerUpdateInstaller. exe a las bases de datos de SQL Server de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="38c06-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="38c06-124">Si se trata de un servidor de servicios de fondo Enterprise Edition y no hay bases de datos colocadas en este servidor, como archivar o supervisar bases de datos, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="38c06-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="38c06-125">Si se trata de un servidor de servicios de fondo Enterprise Edition y hay bases de datos colocadas en este servidor, escriba lo siguiente en una línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="38c06-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="38c06-126">Si se trata de un servidor Standard Edition, escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="38c06-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

