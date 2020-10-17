---
title: 'Lync Server 2013: requisitos de copia de seguridad y restauración: herramientas y permisos'
description: 'Lync Server 2013: requisitos de copia de seguridad y restauración: herramientas y permisos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553476"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="5623f-103">Requisitos de copia de seguridad y restauración en Lync Server 2013: herramientas y permisos</span><span class="sxs-lookup"><span data-stu-id="5623f-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5623f-104">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="5623f-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="5623f-105">En este tema se identifican las herramientas que se pueden usar para realizar copias de seguridad y restaurar Lync Server 2013, los permisos que necesita y si puede ejecutar comandos de forma remota o local.</span><span class="sxs-lookup"><span data-stu-id="5623f-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="5623f-106">En concreto, este tema se centra en las herramientas que se proporcionan con Lync Server para la copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="5623f-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="5623f-107">Copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="5623f-107">Backups</span></span>

<span data-ttu-id="5623f-108">Para hacer una copia de seguridad de Lync Server, use las herramientas que se identifican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5623f-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="5623f-109">Todos los comandos necesarios para hacer una copia de seguridad de Lync Server se pueden ejecutar en scripts y se pueden ejecutar de forma remota.</span><span class="sxs-lookup"><span data-stu-id="5623f-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="5623f-110">Herramientas para realizar copias de seguridad de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5623f-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5623f-111">Para realizar una copia de seguridad de este elemento:</span><span class="sxs-lookup"><span data-stu-id="5623f-111">To back up this:</span></span></th>
<th><span data-ttu-id="5623f-112">Use esta herramienta o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5623f-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5623f-113">Datos de configuración de la topología (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5623f-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-115">Datos del servicio de información de ubicaciones (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="5623f-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-117">Datos de configuración del grupo de respuesta (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5623f-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-119">Datos de usuario persistentes (base de datos Rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="5623f-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="5623f-120">ID de conferencia</span><span class="sxs-lookup"><span data-stu-id="5623f-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="5623f-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="5623f-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="5623f-122">Base de datos de archivado (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="5623f-123">Base de datos de registros de detalles de las llamadas de supervisión (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="5623f-124">Base de datos de QoE de supervisión (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5623f-125">Herramienta de base de datos de SQL Server, como SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5623f-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-126">Base de datos de chat persistente (MGC. MDF)</span><span class="sxs-lookup"><span data-stu-id="5623f-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-127">Procedimientos de copia de seguridad de SQL Server o Export-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="5623f-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="5623f-128">Export-CsPersistentChatData exporta datos de chat persistente como un archivo.</span><span class="sxs-lookup"><span data-stu-id="5623f-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-129">Todos los almacenes de archivos: almacén de archivos de Lync Server, almacén de archivos de archivado</span><span class="sxs-lookup"><span data-stu-id="5623f-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5623f-130">No se deben hacer copias de seguridad de los archivos con el nombre <STRONG>Meeting.Active</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5623f-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="5623f-131">Estos archivos se usan y bloquean cuando se desarrolla una reunión.</span><span class="sxs-lookup"><span data-stu-id="5623f-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="5623f-132">Herramienta de administración estándar del sistema de archivos, como Robocopy.</span><span class="sxs-lookup"><span data-stu-id="5623f-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="5623f-133">Ello</span><span class="sxs-lookup"><span data-stu-id="5623f-133">Restoration</span></span>

<span data-ttu-id="5623f-134">Para restaurar Lync Server, use las herramientas de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5623f-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="5623f-135">Se pueden incluir todos los comandos necesarios para restaurar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5623f-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="5623f-136">Algunas se pueden ejecutar de forma remota, pero otras deben ejecutarse de forma local, tal como se especifica en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="5623f-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="5623f-137">Herramientas para restaurar Lync Server</span><span class="sxs-lookup"><span data-stu-id="5623f-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5623f-138">Para ello:</span><span class="sxs-lookup"><span data-stu-id="5623f-138">To do this:</span></span></th>
<th><span data-ttu-id="5623f-139">Use esta herramienta o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5623f-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5623f-140">Cree un equipo nuevo o limpio</span><span class="sxs-lookup"><span data-stu-id="5623f-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5623f-141">Software de instalación del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="5623f-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="5623f-142">Software de instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5623f-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="5623f-143">Complemento Certificates Microsoft Management Console (MMC), si se restauran certificados con una clave privada exportable</span><span class="sxs-lookup"><span data-stu-id="5623f-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-144">Restaurar datos del almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="5623f-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="5623f-145">Herramienta de administración de sistemas de archivos estándar, como Robocopy</span><span class="sxs-lookup"><span data-stu-id="5623f-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-146">Vuelva a crear bases de datos vacías y establecer permisos para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5623f-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5623f-147">Almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="5623f-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="5623f-148">Servidor back-end</span><span class="sxs-lookup"><span data-stu-id="5623f-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="5623f-149">Base de datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="5623f-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="5623f-150">Base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="5623f-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5623f-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="5623f-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-152">Restaurar el puntero de servicios de dominio de Active Directory al almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="5623f-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5623f-153">Si pierde el punto de conexión de servicio en cualquier momento, puede volver a ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5623f-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="5623f-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="5623f-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-155">Importar la topología, las directivas y las opciones de configuración al almacén de administración central (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="5623f-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5623f-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-157">Publicación y habilitación de la topología</span><span class="sxs-lookup"><span data-stu-id="5623f-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="5623f-158">Topology Builder</span><span class="sxs-lookup"><span data-stu-id="5623f-158">Topology Builder</span></span></p>
<p><span data-ttu-id="5623f-159">– O bien –</span><span class="sxs-lookup"><span data-stu-id="5623f-159">-or-</span></span></p>
<p><span data-ttu-id="5623f-160">Publish-CsTopology y Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="5623f-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-161">Habilitar la última topología publicada</span><span class="sxs-lookup"><span data-stu-id="5623f-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="5623f-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="5623f-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-163">Volver a instalar los componentes de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5623f-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="5623f-164">Instalación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5623f-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5623f-165">Se encuentra en la carpeta o el medio de instalación de Lync Server en \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="5623f-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-166">Restaurar datos de información de ubicaciones (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="5623f-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-168">Restauración de datos de usuario persistentes (Rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="5623f-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="5623f-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-170">Restaurar datos de configuración del grupo de respuesta (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5623f-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5623f-172">Si la configuración se está restaurando en un grupo recién implementado que no tiene datos de grupo de respuesta en la base de datos, debe usar la opción – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="5623f-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="5623f-173">Use esta opción incluso si los datos que se están restaurando están en un grupo de servidores con el mismo nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5623f-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="5623f-174">De lo contrario, la importación no se realizará correctamente, debido a los objetos de contacto de los grupos de respuesta que ya existen en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5623f-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5623f-175">Restaure las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="5623f-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="5623f-176">Base de datos de archivado (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="5623f-177">Bases de datos de supervisión: base de datos de registros de detalles de las llamadas (LcsCDR.mdf) y base de datos QoE (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="5623f-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5623f-178">Herramientas de administración de bases de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5623f-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5623f-179">Base de datos de chat persistente (MGS. MDF)</span><span class="sxs-lookup"><span data-stu-id="5623f-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="5623f-180">Procedimientos de restauración de SQL Server o Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="5623f-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="5623f-181">Puede usar Import-CsPersistentChatData con un archivo creado por Export-CsPersistentChatData y los datos se importarán a la base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5623f-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="5623f-182">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="5623f-182">Required Permissions</span></span>

<span data-ttu-id="5623f-183">Los usuarios deben ser miembros del grupo **RTCUniversalServerAdmins** para poder ejecutar todos los comandos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="5623f-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="5623f-184">La mayoría de los comandos de copia de seguridad y restauración no admiten el control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="5623f-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="5623f-185">Dos excepciones son los cmdlets de chat persistente Export-CsPersistentChatData y Import-CsPersistentChatData, que debe ejecutar un usuario que sea miembro del grupo CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5623f-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="5623f-186">Para ejecutar el Asistente para la implementación de Lync Server, un usuario también debe ser miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="5623f-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

