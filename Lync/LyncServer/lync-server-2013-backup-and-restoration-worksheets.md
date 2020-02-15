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
ms.openlocfilehash: 7f767a2c94e797ab43e3b5ace6b553b05bafd81f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="9ce61-102">Hojas de cálculo de copia de seguridad y restauración para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ce61-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ce61-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="9ce61-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="9ce61-104">El plan de copia de seguridad y restauración de la organización debe contener detalles sobre cómo y cuándo se realiza la copia de seguridad de los datos y la configuración.</span><span class="sxs-lookup"><span data-stu-id="9ce61-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="9ce61-105">Puede usar las hojas de cálculo que se presentan aquí para ayudarle a documentar esta información para su implementación específica y para los requisitos de restauración y copia de seguridad de su organización.</span><span class="sxs-lookup"><span data-stu-id="9ce61-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="9ce61-106">Use las siguientes hojas de trabajo para registrar la información necesaria para realizar copias de seguridad y restaurar la información de configuración de la base de datos, el almacén de archivos y la configuración de un grupo de servidores de Lync Server o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9ce61-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="9ce61-107">Conserve una o más copias de estas hojas de cálculo en una ubicación segura para que sean accesibles fácilmente si necesita restaurar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ce61-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ce61-108">Las hojas de cálculo de esta sección cubren solo la información necesaria para restaurar los datos y la configuración de las bases de datos y los servidores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ce61-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="9ce61-109">Si necesita documentar otra información de restauración, como la información para volver a instalar sistemas operativos y otro software, use los planes de implementación de su organización y los planes de copia de seguridad y restauración para cumplir dichos requisitos.</span><span class="sxs-lookup"><span data-stu-id="9ce61-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="9ce61-110">Hoja de copia de seguridad y restauración de base de datos</span><span class="sxs-lookup"><span data-stu-id="9ce61-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="9ce61-111">Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de las bases de datos de Lync Server y restaurarlas.</span><span class="sxs-lookup"><span data-stu-id="9ce61-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="9ce61-112">Información de base de datos para copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="9ce61-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="9ce61-113">Base de datos</span><span class="sxs-lookup"><span data-stu-id="9ce61-113">Database</span></span></th>
<th><span data-ttu-id="9ce61-114">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9ce61-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="9ce61-115">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-115">Backup schedule</span></span></th>
<th><span data-ttu-id="9ce61-116">Herramienta copia de seguridad de base de datos</span><span class="sxs-lookup"><span data-stu-id="9ce61-116">Database backup tool</span></span></th>
<th><span data-ttu-id="9ce61-117">Conjunto de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-117">Backup set</span></span></th>
<th><span data-ttu-id="9ce61-118">Destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-118">Backup destination</span></span></th>
<th><span data-ttu-id="9ce61-119">Notas</span><span class="sxs-lookup"><span data-stu-id="9ce61-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce61-120">Base de datos RTC en el servidor back-end para datos de usuario</span><span class="sxs-lookup"><span data-stu-id="9ce61-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="9ce61-121"><strong>Export-CsUserData</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="9ce61-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="9ce61-122">Denomina</span><span class="sxs-lookup"><span data-stu-id="9ce61-122">Name:</span></span></p>
<p><span data-ttu-id="9ce61-123">Expiración</span><span class="sxs-lookup"><span data-stu-id="9ce61-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce61-124">Base de datos de LcsLog (nombre predeterminado) en el servidor de base de datos de archivado</span><span class="sxs-lookup"><span data-stu-id="9ce61-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ce61-125">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ce61-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="9ce61-126">Denomina</span><span class="sxs-lookup"><span data-stu-id="9ce61-126">Name:</span></span></p>
<p><span data-ttu-id="9ce61-127">Expiración</span><span class="sxs-lookup"><span data-stu-id="9ce61-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce61-128">Base de datos de LcsCdr en servidor de base de datos de supervisión para registros de detalles de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="9ce61-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ce61-129">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ce61-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="9ce61-130">Denomina</span><span class="sxs-lookup"><span data-stu-id="9ce61-130">Name:</span></span></p>
<p><span data-ttu-id="9ce61-131">Expiración</span><span class="sxs-lookup"><span data-stu-id="9ce61-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce61-132">Base de datos de QoEMetrics en el servidor de base de datos de supervisión para datos de calidad de la experiencia (QoE)</span><span class="sxs-lookup"><span data-stu-id="9ce61-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ce61-133">Herramienta de administración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ce61-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="9ce61-134">Denomina</span><span class="sxs-lookup"><span data-stu-id="9ce61-134">Name:</span></span></p>
<p><span data-ttu-id="9ce61-135">Expiración</span><span class="sxs-lookup"><span data-stu-id="9ce61-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce61-136">Base de datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9ce61-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="9ce61-137">Herramienta de administración de SQL Server o cmdlet <strong>Export-CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="9ce61-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="9ce61-138">Denomina</span><span class="sxs-lookup"><span data-stu-id="9ce61-138">Name:</span></span></p>
<p><span data-ttu-id="9ce61-139">Expiración</span><span class="sxs-lookup"><span data-stu-id="9ce61-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ce61-140">No es necesaria ninguna copia de seguridad ni restauración de las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="9ce61-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="9ce61-141">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="9ce61-141">Rtcdyn.</span></span> <span data-ttu-id="9ce61-142">Los datos de usuario transitorios de esta base de datos no son necesarios para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="9ce61-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="9ce61-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="9ce61-143">Rtcab.</span></span> <span data-ttu-id="9ce61-144">La base de datos de la libreta de direcciones se vuelve a crear automáticamente a partir de la lista global de direcciones (GAL) de los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ce61-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="9ce61-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="9ce61-145">Rgsdyn.</span></span> <span data-ttu-id="9ce61-146">Los datos transitorios del servicio de grupo de respuesta de esta base de datos no son necesarios para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="9ce61-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="9ce61-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="9ce61-147">Cpsdyn.</span></span> <span data-ttu-id="9ce61-148">La información dinámica para la aplicación estacionamiento de llamadas no es necesaria para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="9ce61-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="9ce61-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="9ce61-149">MgcComp.</span></span> <span data-ttu-id="9ce61-150">La base de datos de cumplimiento de chat persistente no es necesaria para la restauración del servicio.</span><span class="sxs-lookup"><span data-stu-id="9ce61-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="9ce61-151">Hoja de cálculo de copia de seguridad y restauración del almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="9ce61-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="9ce61-152">Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de los almacenes de archivos y restaurarlos.</span><span class="sxs-lookup"><span data-stu-id="9ce61-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="9ce61-153">Los almacenes de archivos contienen datos como los metadatos de contenido de reuniones, los registros de cumplimiento de actualizaciones, los registros de actualización de dispositivos y los archivos de audio para el grupo de respuesta, estacionamiento de llamadas y aplicaciones de anuncio.</span><span class="sxs-lookup"><span data-stu-id="9ce61-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="9ce61-154">Información del almacén de archivos para la copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="9ce61-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="9ce61-155">Contenido</span><span class="sxs-lookup"><span data-stu-id="9ce61-155">Content</span></span></th>
<th><span data-ttu-id="9ce61-156">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9ce61-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="9ce61-157">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-157">Backup schedule</span></span></th>
<th><span data-ttu-id="9ce61-158">Herramienta de copia de seguridad del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="9ce61-158">File system backup tool</span></span></th>
<th><span data-ttu-id="9ce61-159">Copia de seguridad del recurso compartido de archivos \*</span><span class="sxs-lookup"><span data-stu-id="9ce61-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="9ce61-160">Destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-160">Backup destination</span></span></th>
<th><span data-ttu-id="9ce61-161">Notas</span><span class="sxs-lookup"><span data-stu-id="9ce61-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce61-162">Almacén de archivos de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9ce61-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="9ce61-163">Herramienta de copia de seguridad estándar, como Robocopy</span><span class="sxs-lookup"><span data-stu-id="9ce61-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="9ce61-164">Servidor de archivos para Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="9ce61-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="9ce61-165">De forma predeterminada en Standard Edition, para la implementación de Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9ce61-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="9ce61-166">Normalmente, una por sitio.</span><span class="sxs-lookup"><span data-stu-id="9ce61-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9ce61-167">No se deben hacer copias de seguridad de los archivos con el nombre <strong>Meeting.Active</strong>.</span><span class="sxs-lookup"><span data-stu-id="9ce61-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="9ce61-168">Estos archivos están en uso y se bloquean mientras se realiza una reunión.</span><span class="sxs-lookup"><span data-stu-id="9ce61-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="9ce61-169">Hoja de cálculo de copia de seguridad y restauración de configuración</span><span class="sxs-lookup"><span data-stu-id="9ce61-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="9ce61-170">Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de la configuración y restaurarla.</span><span class="sxs-lookup"><span data-stu-id="9ce61-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="9ce61-171">Información de configuración para copia de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="9ce61-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="9ce61-172">Base de datos</span><span class="sxs-lookup"><span data-stu-id="9ce61-172">Database</span></span></th>
<th><span data-ttu-id="9ce61-173">Nombre del servidor (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9ce61-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="9ce61-174">Programación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-174">Backup schedule</span></span></th>
<th><span data-ttu-id="9ce61-175">Herramienta de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-175">Backup tool</span></span></th>
<th><span data-ttu-id="9ce61-176">Nombre del archivo de configuración (. xml)</span><span class="sxs-lookup"><span data-stu-id="9ce61-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="9ce61-177">Ubicación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce61-177">Backup location</span></span></th>
<th><span data-ttu-id="9ce61-178">Notas</span><span class="sxs-lookup"><span data-stu-id="9ce61-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce61-179">Base de datos XDS en el almacén de administración central para la configuración de la topología (global)</span><span class="sxs-lookup"><span data-stu-id="9ce61-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="9ce61-180"><strong>Export-CsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="9ce61-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce61-181">Base de datos de lis en el almacén de administración central para información de ubicación E9-1-1 (global)</span><span class="sxs-lookup"><span data-stu-id="9ce61-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ce61-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="9ce61-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce61-183">Base de datos de RgsConfig en el servidor back-end para la configuración del grupo de respuesta (grupo)</span><span class="sxs-lookup"><span data-stu-id="9ce61-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9ce61-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="9ce61-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

