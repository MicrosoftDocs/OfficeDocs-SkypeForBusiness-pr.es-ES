---
title: 'Lync Server 2013: realizar copias de seguridad y restaurar hojas de cálculo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca10b848dfa1f6cf53724b364cf53b1fc0fad90
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="2327d-102">Copias de seguridad y restauración de hojas de cálculo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2327d-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2327d-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="2327d-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="2327d-104">El plan de copia de seguridad y restauración de la organización debe contener detalles sobre cómo y cuándo se realiza la copia de seguridad de los datos y la configuración.</span><span class="sxs-lookup"><span data-stu-id="2327d-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="2327d-105">Puede usar las hojas de cálculo que se presentan aquí para ayudarle a documentar esta información para su implementación específica y los requisitos de copia de seguridad y restauración de su organización.</span><span class="sxs-lookup"><span data-stu-id="2327d-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="2327d-106">Use las siguientes hojas de cálculo para registrar la información que necesita para realizar copias de seguridad y restaurar la información de la base de datos, el almacén de archivos y la configuración de un grupo de servidores de Lync o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2327d-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="2327d-107">Mantenga una o más copias de estas hojas de cálculo en un lugar seguro para que sean accesibles si necesita restaurar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2327d-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2327d-108">Las hojas de cálculo de esta sección cubren solo la información necesaria para restaurar los datos y la configuración de las bases de datos y los servidores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2327d-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="2327d-109">Si necesita documentar otra información de restauración, como la información para reinstalar sistemas operativos y otro software, use los planes de implementación de su organización y los planes de copia de seguridad y restauración para cumplir esos requisitos.</span><span class="sxs-lookup"><span data-stu-id="2327d-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="2327d-110">Hoja de cálculo de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="2327d-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="2327d-111">Use la tabla siguiente para registrar la información que necesita para realizar copias de seguridad y restaurar las bases de datos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2327d-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="2327d-112">Información de la base de datos para copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="2327d-112">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2327d-113">Database</span><span class="sxs-lookup"><span data-stu-id="2327d-113">Database</span></span></th>
<th><span data-ttu-id="2327d-114">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2327d-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="2327d-115">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-115">Backup schedule</span></span></th>
<th><span data-ttu-id="2327d-116">Herramienta copia de seguridad de base de datos</span><span class="sxs-lookup"><span data-stu-id="2327d-116">Database backup tool</span></span></th>
<th><span data-ttu-id="2327d-117">Conjunto de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-117">Backup set</span></span></th>
<th><span data-ttu-id="2327d-118">Destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-118">Backup destination</span></span></th>
<th><span data-ttu-id="2327d-119">Notas</span><span class="sxs-lookup"><span data-stu-id="2327d-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2327d-120">Base de datos RTC en el servidor back-end para datos de usuario</span><span class="sxs-lookup"><span data-stu-id="2327d-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="2327d-121">Cmdlet <strong>Export-CsUserData</strong></span><span class="sxs-lookup"><span data-stu-id="2327d-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="2327d-122">Denomina</span><span class="sxs-lookup"><span data-stu-id="2327d-122">Name:</span></span></p>
<p><span data-ttu-id="2327d-123">Currido</span><span class="sxs-lookup"><span data-stu-id="2327d-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2327d-124">LcsLog (nombre predeterminado) base de datos en el servidor de base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="2327d-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2327d-125">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2327d-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="2327d-126">Denomina</span><span class="sxs-lookup"><span data-stu-id="2327d-126">Name:</span></span></p>
<p><span data-ttu-id="2327d-127">Currido</span><span class="sxs-lookup"><span data-stu-id="2327d-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2327d-128">Base de datos de LcsCdr al supervisar el servidor de base de datos para registros de detalles de llamadas (CDRs)</span><span class="sxs-lookup"><span data-stu-id="2327d-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2327d-129">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2327d-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="2327d-130">Denomina</span><span class="sxs-lookup"><span data-stu-id="2327d-130">Name:</span></span></p>
<p><span data-ttu-id="2327d-131">Currido</span><span class="sxs-lookup"><span data-stu-id="2327d-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2327d-132">QoEMetrics base de datos de supervisión del servidor de base de datos para los datos de la calidad de la experiencia (QoE)</span><span class="sxs-lookup"><span data-stu-id="2327d-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2327d-133">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2327d-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="2327d-134">Denomina</span><span class="sxs-lookup"><span data-stu-id="2327d-134">Name:</span></span></p>
<p><span data-ttu-id="2327d-135">Currido</span><span class="sxs-lookup"><span data-stu-id="2327d-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2327d-136">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2327d-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="2327d-137">Herramienta de administración de SQL Server o cmdlet <strong>Export-CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="2327d-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="2327d-138">Denomina</span><span class="sxs-lookup"><span data-stu-id="2327d-138">Name:</span></span></p>
<p><span data-ttu-id="2327d-139">Currido</span><span class="sxs-lookup"><span data-stu-id="2327d-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2327d-140">No es necesario realizar copias de seguridad ni restauración de las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="2327d-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="2327d-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="2327d-141">Rtcdyn.</span></span> <span data-ttu-id="2327d-142">Los datos de usuario transitorios de esta base de datos no son necesarios para la restauración de servicio.</span><span class="sxs-lookup"><span data-stu-id="2327d-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="2327d-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="2327d-143">Rtcab.</span></span> <span data-ttu-id="2327d-144">La base de datos de la libreta de direcciones se vuelve a crear automáticamente desde la lista global de direcciones (GAL) en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2327d-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="2327d-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="2327d-145">Rgsdyn.</span></span> <span data-ttu-id="2327d-146">Los datos transitorios del servicio de grupo de respuesta de esta base de datos no son necesarios para la restauración de servicio.</span><span class="sxs-lookup"><span data-stu-id="2327d-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="2327d-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="2327d-147">Cpsdyn.</span></span> <span data-ttu-id="2327d-148">La información dinámica para la aplicación de estacionamiento de llamadas no es necesaria para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="2327d-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="2327d-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="2327d-149">MgcComp.</span></span> <span data-ttu-id="2327d-150">La base de datos de cumplimiento de la conversación persistente no es necesaria para la restauración de servicio.</span><span class="sxs-lookup"><span data-stu-id="2327d-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="2327d-151">Hoja de cálculo de copia de seguridad y restauración del almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="2327d-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="2327d-152">Use la tabla siguiente para registrar la información que necesita para hacer una copia de seguridad de los almacenes de archivos y restaurarlos.</span><span class="sxs-lookup"><span data-stu-id="2327d-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="2327d-153">Los almacenes de archivos contienen datos como metadatos de contenido de la reunión, registros de cumplimiento de actualizaciones, registros de actualización de dispositivos y archivos de audio para el grupo de respuesta, las llamadas de estacionamiento y las aplicaciones de anuncios.</span><span class="sxs-lookup"><span data-stu-id="2327d-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="2327d-154">Información del almacén de archivos para copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="2327d-154">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2327d-155">Contenido</span><span class="sxs-lookup"><span data-stu-id="2327d-155">Content</span></span></th>
<th><span data-ttu-id="2327d-156">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2327d-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="2327d-157">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-157">Backup schedule</span></span></th>
<th><span data-ttu-id="2327d-158">Herramienta de copia de seguridad del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="2327d-158">File system backup tool</span></span></th>
<th><span data-ttu-id="2327d-159">Compartir archivos para realizar una copia de seguridad \*</span><span class="sxs-lookup"><span data-stu-id="2327d-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="2327d-160">Destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-160">Backup destination</span></span></th>
<th><span data-ttu-id="2327d-161">Notas</span><span class="sxs-lookup"><span data-stu-id="2327d-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2327d-162">Almacén de archivos de Lync Server</span><span class="sxs-lookup"><span data-stu-id="2327d-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="2327d-163">Herramienta de copia de seguridad estándar, como Robocopy</span><span class="sxs-lookup"><span data-stu-id="2327d-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="2327d-164">Servidor de archivos para Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2327d-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="2327d-165">En Standard Edition de forma predeterminada, para la implementación de Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2327d-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="2327d-166">Normalmente, uno por sitio.</span><span class="sxs-lookup"><span data-stu-id="2327d-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2327d-167">No se debe realizar una copia de seguridad de los archivos llamados <strong>Meeting. Active</strong> .</span><span class="sxs-lookup"><span data-stu-id="2327d-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="2327d-168">Estos archivos están en uso y se bloquean durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="2327d-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="2327d-169">Hoja de cálculo de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="2327d-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="2327d-170">Use la tabla siguiente para registrar la información que necesita para realizar copias de seguridad y restaurar la configuración.</span><span class="sxs-lookup"><span data-stu-id="2327d-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="2327d-171">Información de configuración de copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="2327d-171">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2327d-172">Database</span><span class="sxs-lookup"><span data-stu-id="2327d-172">Database</span></span></th>
<th><span data-ttu-id="2327d-173">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2327d-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="2327d-174">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-174">Backup schedule</span></span></th>
<th><span data-ttu-id="2327d-175">Herramienta de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-175">Backup tool</span></span></th>
<th><span data-ttu-id="2327d-176">Nombre del archivo de configuración (. xml)</span><span class="sxs-lookup"><span data-stu-id="2327d-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="2327d-177">Ubicación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="2327d-177">Backup location</span></span></th>
<th><span data-ttu-id="2327d-178">Notas</span><span class="sxs-lookup"><span data-stu-id="2327d-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2327d-179">Base de datos XDS en el almacén de administración central para configuración de topología (global)</span><span class="sxs-lookup"><span data-stu-id="2327d-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="2327d-180">Cmdlet <strong>Export-CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="2327d-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2327d-181">Base de datos de lis en el almacén central de administración para información de la ubicación E9-1-1 (global)</span><span class="sxs-lookup"><span data-stu-id="2327d-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2327d-182">Cmdlet <strong>Export-CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="2327d-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2327d-183">Base de datos RgsConfig en el servidor back-end para la configuración de grupo de respuesta (grupo)</span><span class="sxs-lookup"><span data-stu-id="2327d-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2327d-184">Cmdlet <strong>Export-CsRgsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="2327d-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

