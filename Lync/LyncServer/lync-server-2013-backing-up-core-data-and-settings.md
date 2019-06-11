---
title: 'Lync Server 2013: realizar una copia de seguridad de los datos y la configuración básicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1737dac3369361b0937e6b870839e11e5706e41a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="6e9cd-102">Realizar copias de seguridad de los datos y la configuración básicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e9cd-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e9cd-103">_**Última modificación del tema:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="6e9cd-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="6e9cd-104">Los procedimientos siguientes usan los cmdlets del shell de administración de Lync Server para crear archivos de copia de seguridad para la configuración y los datos de los servicios básicos.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="6e9cd-105">Para obtener más información sobre las herramientas usadas en esta sección, incluyendo dónde se encuentran, consulte [requisitos de copia de seguridad y restauración en Lync Server 2013: herramientas y permisos](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6e9cd-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="6e9cd-106">Para más información sobre cómo realizar copias de seguridad del archivado y la supervisión de datos, vea [realizar copias de seguridad del archivado y la supervisión de bases de datos en Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="6e9cd-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e9cd-107">El paso de esta sección para realizar una copia de seguridad del almacén de administración central incluye la configuración y la configuración para archivar y supervisar.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="6e9cd-108">Puede ejecutar los cmdlets descritos en esta sección de forma local o remota.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="6e9cd-109">Para hacer una copia de seguridad de los datos y la configuración básicos</span><span class="sxs-lookup"><span data-stu-id="6e9cd-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="6e9cd-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6e9cd-111">Para almacenar las copias de seguridad que cree en los pasos siguientes, cree una nueva carpeta compartida y actualice la ruta de acceso a la que hace referencia **$backup** a la nueva carpeta compartida.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="6e9cd-112">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="6e9cd-113">Haga una copia de seguridad del archivo de configuración del almacén central de administración.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="6e9cd-114">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="6e9cd-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e9cd-116">Este paso exporta la topología, las directivas y los parámetros de configuración de Lync Server a un archivo.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="6e9cd-117">No es necesario ningún otro paso para hacer una copia de seguridad de los datos de la topología.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="6e9cd-118">Copie el archivo de configuración del almacén de administración central de la copia\\de seguridad en $backup.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="6e9cd-119">Haga una copia de seguridad de los datos del servicio de información.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-119">Back up Location Information service data.</span></span> <span data-ttu-id="6e9cd-120">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="6e9cd-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="6e9cd-122">Copie el archivo de configuración del servicio de información de ubicación con copia\\de seguridad en $backup.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="6e9cd-123">Haga una copia de seguridad de los datos de usuario en todas las bases de datos back-end de un grupo de servidores front-end y de cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="6e9cd-124">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="6e9cd-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="6e9cd-126">Copie el archivo de usuario de copia de seguridad\\en $backup.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="6e9cd-127">En todos los grupos que ejecutan la aplicación de grupo de respuesta, realice una copia de seguridad de la configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="6e9cd-128">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="6e9cd-129">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="6e9cd-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6e9cd-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="6e9cd-131">Copie el archivo de configuración del grupo de respuesta de copia\\de seguridad en $backup.</span><span class="sxs-lookup"><span data-stu-id="6e9cd-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

