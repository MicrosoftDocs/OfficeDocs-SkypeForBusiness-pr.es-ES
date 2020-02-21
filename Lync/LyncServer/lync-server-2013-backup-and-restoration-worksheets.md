---
title: 'Lync Server 2013: hojas de cálculo de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fcf163893a84e4b9244e43b12c702cf0076b1ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="ff0dd-102">Hojas de cálculo de copia de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff0dd-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff0dd-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ff0dd-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ff0dd-104">El plan de copia de seguridad y restauración de la organización debe contener detalles sobre cómo y cuándo se realiza la copia de seguridad de los datos y la configuración.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="ff0dd-105">Puede usar las hojas de cálculo que se presentan aquí para ayudarle a documentar esta información para su implementación específica y para los requisitos de restauración y copia de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="ff0dd-106">Use las siguientes hojas de trabajo para registrar la información necesaria para realizar copias de seguridad y restaurar la información de configuración de la base de datos, el almacén de archivos y la configuración de un grupo de servidores de Lync Server o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="ff0dd-107">Conserve una o más copias de estas hojas de cálculo en una ubicación segura para que sean accesibles fácilmente si necesita restaurar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff0dd-108">Las hojas de cálculo de esta sección cubren solo la información necesaria para restaurar los datos y la configuración de las bases de datos y los servidores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="ff0dd-109">Si necesita documentar otra información de restauración, como la información para volver a instalar sistemas operativos y otro software, use los planes de implementación de su organización y los planes de copia de seguridad y restauración para cumplir dichos requisitos.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="ff0dd-110">Hoja de copia de seguridad y restauración de base de datos</span><span class="sxs-lookup"><span data-stu-id="ff0dd-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="ff0dd-111">Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de las bases de datos de Lync Server y restaurarlas.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="ff0dd-112">Información de base de datos para copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="ff0dd-113">Base de datos</span><span class="sxs-lookup"><span data-stu-id="ff0dd-113">Database</span></span></th>
<th><span data-ttu-id="ff0dd-114">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="ff0dd-115">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-115">Backup schedule</span></span></th>
<th><span data-ttu-id="ff0dd-116">Herramienta copia de seguridad de base de datos</span><span class="sxs-lookup"><span data-stu-id="ff0dd-116">Database backup tool</span></span></th>
<th><span data-ttu-id="ff0dd-117">Conjunto de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-117">Backup set</span></span></th>
<th><span data-ttu-id="ff0dd-118">Destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-118">Backup destination</span></span></th>
<th><span data-ttu-id="ff0dd-119">Notas</span><span class="sxs-lookup"><span data-stu-id="ff0dd-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff0dd-120">Base de datos RTC en el servidor back-end para datos de usuario</span><span class="sxs-lookup"><span data-stu-id="ff0dd-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="ff0dd-121"><strong>Export-CsUserData</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff0dd-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="ff0dd-122">Denomina</span><span class="sxs-lookup"><span data-stu-id="ff0dd-122">Name:</span></span></p>
<p><span data-ttu-id="ff0dd-123">Expiración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff0dd-124">Base de datos de LcsLog (nombre predeterminado) en el servidor de base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="ff0dd-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff0dd-125">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff0dd-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="ff0dd-126">Denomina</span><span class="sxs-lookup"><span data-stu-id="ff0dd-126">Name:</span></span></p>
<p><span data-ttu-id="ff0dd-127">Expiración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff0dd-128">Base de datos de LcsCdr en servidor de base de datos de supervisión para registros de detalles de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff0dd-129">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff0dd-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="ff0dd-130">Denomina</span><span class="sxs-lookup"><span data-stu-id="ff0dd-130">Name:</span></span></p>
<p><span data-ttu-id="ff0dd-131">Expiración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff0dd-132">Base de datos de QoEMetrics en el servidor de base de datos de supervisión para datos de calidad de la experiencia (QoE)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff0dd-133">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff0dd-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="ff0dd-134">Denomina</span><span class="sxs-lookup"><span data-stu-id="ff0dd-134">Name:</span></span></p>
<p><span data-ttu-id="ff0dd-135">Expiración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff0dd-136">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ff0dd-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="ff0dd-137">Herramienta de administración de SQL Server o cmdlet <strong>Export-CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="ff0dd-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="ff0dd-138">Denomina</span><span class="sxs-lookup"><span data-stu-id="ff0dd-138">Name:</span></span></p>
<p><span data-ttu-id="ff0dd-139">Expiración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff0dd-140">No es necesaria ninguna copia de seguridad ni restauración de las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="ff0dd-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="ff0dd-141">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-141">Rtcdyn.</span></span> <span data-ttu-id="ff0dd-142">Los datos de usuario transitorios de esta base de datos no son necesarios para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="ff0dd-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-143">Rtcab.</span></span> <span data-ttu-id="ff0dd-144">La base de datos de la libreta de direcciones se vuelve a crear automáticamente a partir de la lista global de direcciones (GAL) de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="ff0dd-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-145">Rgsdyn.</span></span> <span data-ttu-id="ff0dd-146">Los datos transitorios del servicio de grupo de respuesta de esta base de datos no son necesarios para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="ff0dd-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-147">Cpsdyn.</span></span> <span data-ttu-id="ff0dd-148">La información dinámica para la aplicación estacionamiento de llamadas no es necesaria para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="ff0dd-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-149">MgcComp.</span></span> <span data-ttu-id="ff0dd-150">La base de datos de cumplimiento de chat persistente no es necesaria para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="ff0dd-151">Hoja de cálculo de copia de seguridad y restauración del almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="ff0dd-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="ff0dd-152">Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de los almacenes de archivos y restaurarlos.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="ff0dd-153">Los almacenes de archivos contienen datos como los metadatos de contenido de reuniones, los registros de cumplimiento de actualizaciones, los registros de actualización de dispositivos y los archivos de audio para el grupo de respuesta, estacionamiento de llamadas y aplicaciones de anuncio.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="ff0dd-154">Información del almacén de archivos para la copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="ff0dd-155">Contenido</span><span class="sxs-lookup"><span data-stu-id="ff0dd-155">Content</span></span></th>
<th><span data-ttu-id="ff0dd-156">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="ff0dd-157">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-157">Backup schedule</span></span></th>
<th><span data-ttu-id="ff0dd-158">Herramienta de copia de seguridad del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="ff0dd-158">File system backup tool</span></span></th>
<th><span data-ttu-id="ff0dd-159">Copia de seguridad del recurso compartido de archivos \*</span><span class="sxs-lookup"><span data-stu-id="ff0dd-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="ff0dd-160">Destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-160">Backup destination</span></span></th>
<th><span data-ttu-id="ff0dd-161">Notas</span><span class="sxs-lookup"><span data-stu-id="ff0dd-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff0dd-162">Almacén de archivos de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff0dd-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="ff0dd-163">Herramienta de copia de seguridad estándar, como Robocopy</span><span class="sxs-lookup"><span data-stu-id="ff0dd-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="ff0dd-164">Servidor de archivos para Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="ff0dd-165">De forma predeterminada en Standard Edition, para la implementación de Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="ff0dd-166">Normalmente, una por sitio.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff0dd-167">No se deben hacer copias de seguridad de los archivos con el nombre <strong>Meeting.Active</strong>.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="ff0dd-168">Estos archivos están en uso y se bloquean mientras se realiza una reunión.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="ff0dd-169">Hoja de cálculo de copia de seguridad y restauración de configuración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="ff0dd-170">Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de la configuración y restaurarla.</span><span class="sxs-lookup"><span data-stu-id="ff0dd-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="ff0dd-171">Información de configuración para copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="ff0dd-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="ff0dd-172">Base de datos</span><span class="sxs-lookup"><span data-stu-id="ff0dd-172">Database</span></span></th>
<th><span data-ttu-id="ff0dd-173">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="ff0dd-174">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-174">Backup schedule</span></span></th>
<th><span data-ttu-id="ff0dd-175">Herramienta de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-175">Backup tool</span></span></th>
<th><span data-ttu-id="ff0dd-176">Nombre del archivo de configuración (. xml)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="ff0dd-177">Ubicación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0dd-177">Backup location</span></span></th>
<th><span data-ttu-id="ff0dd-178">Notas</span><span class="sxs-lookup"><span data-stu-id="ff0dd-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff0dd-179">Base de datos XDS en el almacén de administración central para la configuración de la topología (global)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="ff0dd-180"><strong>Export-CsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff0dd-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff0dd-181">Base de datos de lis en el almacén de administración central para información de ubicación E9-1-1 (global)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff0dd-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff0dd-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff0dd-183">Base de datos de RgsConfig en el servidor back-end para la configuración del grupo de respuesta (grupo)</span><span class="sxs-lookup"><span data-stu-id="ff0dd-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ff0dd-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="ff0dd-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

