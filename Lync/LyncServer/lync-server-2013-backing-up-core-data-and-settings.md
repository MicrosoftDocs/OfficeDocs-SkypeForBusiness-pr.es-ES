---
title: 'Lync Server 2013: copia de seguridad de los datos y la configuración principales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a6614a06ea4e5370dd944940d35a690853c171b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="16937-102">Copia de seguridad de los datos y la configuración principales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16937-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16937-103">_**Última modificación del tema:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="16937-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="16937-104">Los siguientes procedimientos usan los cmdlets del shell de administración de Lync Server para crear archivos de copia de seguridad para la configuración y los datos de los servicios principales.</span><span class="sxs-lookup"><span data-stu-id="16937-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="16937-105">Para obtener más información acerca de las herramientas usadas en esta sección, incluidos dónde se encuentran, consulte [requisitos de copia de seguridad y restauración en Lync Server 2013: herramientas y permisos](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="16937-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="16937-106">Para obtener más información sobre cómo realizar copias de seguridad de los datos de archivado y supervisión, vea [realizar copias de seguridad de bases de datos de archivado y supervisión en Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="16937-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16937-107">El paso de esta sección para crear una copia de seguridad del almacén de administración central incluye la configuración y la configuración de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="16937-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="16937-108">Puede ejecutar los cmdlets descritos en esta sección de manera local o remota.</span><span class="sxs-lookup"><span data-stu-id="16937-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="16937-109">Para crear copias de seguridad de datos y configuración principales</span><span class="sxs-lookup"><span data-stu-id="16937-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="16937-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en cualquier equipo de la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="16937-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16937-111">Para almacenar las copias de seguridad creadas en los pasos siguientes, cree una nueva carpeta compartida y actualice la ruta de acceso a la que hace referencia **$Backup** con la nueva carpeta compartida.</span><span class="sxs-lookup"><span data-stu-id="16937-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="16937-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="16937-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="16937-113">Realice una copia de seguridad del archivo de configuración del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="16937-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="16937-114">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="16937-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="16937-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16937-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16937-116">Este paso exporta la topología, las directivas y las opciones de configuración de Lync Server a un archivo.</span><span class="sxs-lookup"><span data-stu-id="16937-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="16937-117">No es necesario realizar ningún otro paso para crear una copia de seguridad de los datos de la topología.</span><span class="sxs-lookup"><span data-stu-id="16937-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="16937-118">Copie el archivo de configuración de la copia de seguridad del almacén de\\Administración Central en $backup.</span><span class="sxs-lookup"><span data-stu-id="16937-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="16937-p104">Cree una copia de seguridad de los datos del servicio de información de ubicaciones. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16937-p104">Back up Location Information service data. At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="16937-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16937-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="16937-122">Copie el archivo de configuración del servicio de información de ubicación con copia\\de seguridad en $backup.</span><span class="sxs-lookup"><span data-stu-id="16937-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="16937-123">Realice una copia de seguridad de los datos de usuario en cada base de datos back-end de un grupo de servidores front-end y cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="16937-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="16937-124">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="16937-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="16937-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16937-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="16937-126">Copie el archivo de usuario de copia de seguridad\\en $backup.</span><span class="sxs-lookup"><span data-stu-id="16937-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="16937-127">En cada grupo que ejecuta la aplicación de grupo de respuesta, realice una copia de seguridad de la configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="16937-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="16937-128">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16937-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="16937-129">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="16937-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="16937-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16937-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="16937-131">Copie el archivo de configuración del grupo de respuesta de la\\copia de seguridad en $backup.</span><span class="sxs-lookup"><span data-stu-id="16937-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

