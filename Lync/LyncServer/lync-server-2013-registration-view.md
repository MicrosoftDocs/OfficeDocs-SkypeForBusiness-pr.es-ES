---
title: 'Lync Server 2013: vista de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120f0cb40bb3401a327e495a460db400a9359891
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="8d393-102">Vista de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d393-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d393-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8d393-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8d393-104">La vista de registro almacena información sobre el registro de usuarios.</span><span class="sxs-lookup"><span data-stu-id="8d393-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="8d393-105">Esta vista se presentó en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d393-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d393-106">Columna</span><span class="sxs-lookup"><span data-stu-id="8d393-106">Column</span></span></th>
<th><span data-ttu-id="8d393-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d393-107">Data Type</span></span></th>
<th><span data-ttu-id="8d393-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d393-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d393-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8d393-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d393-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="8d393-111">Time of session request.</span></span> <span data-ttu-id="8d393-112">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="8d393-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="8d393-113">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d393-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-115">int</span><span class="sxs-lookup"><span data-stu-id="8d393-115">int</span></span></p></td>
<td><p><span data-ttu-id="8d393-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="8d393-116">ID number to identify the session.</span></span> <span data-ttu-id="8d393-117">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="8d393-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="8d393-118">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d393-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-120">datetime</span><span class="sxs-lookup"><span data-stu-id="8d393-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d393-121">Hora en la que se realizó el registro.</span><span class="sxs-lookup"><span data-stu-id="8d393-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8d393-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8d393-124">Identificador URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-127">Tipo de URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="8d393-128">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d393-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-131">Inquilino del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-131">Tenant of the user who registered.</span></span> <span data-ttu-id="8d393-132">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d393-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-134">identificador</span><span class="sxs-lookup"><span data-stu-id="8d393-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8d393-135">Identificador único del extremo del usuario registrado con.</span><span class="sxs-lookup"><span data-stu-id="8d393-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-137">identificador</span><span class="sxs-lookup"><span data-stu-id="8d393-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8d393-138">Identificador único que se usa para diferenciar los registros que implican al mismo usuario y al mismo punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8d393-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-140">datetime</span><span class="sxs-lookup"><span data-stu-id="8d393-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d393-141">Hora en la que se produjo la anulación de inscripción.</span><span class="sxs-lookup"><span data-stu-id="8d393-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-144">Motivo de la anulación del registro.</span><span class="sxs-lookup"><span data-stu-id="8d393-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-147">Versión del cliente que usó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-148"><strong>Tipocliente</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-149">int</span><span class="sxs-lookup"><span data-stu-id="8d393-149">int</span></span></p></td>
<td><p><span data-ttu-id="8d393-150">Cliente usado por el usuario que registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-150">Client used by the user who registered.</span></span> <span data-ttu-id="8d393-151">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d393-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8d393-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8d393-154">Categoría del cliente que ha usado el usuario que registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-155"><strong>Dirección IP</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-157">Dirección IP con la que el usuario se registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-157">IP Address the user registered with.</span></span> <span data-ttu-id="8d393-158">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="8d393-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="8d393-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="8d393-161">IDENTIFICACIÓN del cuadro de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="8d393-161">SIP dialog ID.</span></span> <span data-ttu-id="8d393-162">El formato de es:</span><span class="sxs-lookup"><span data-stu-id="8d393-162">The format of the is:</span></span></p>
<p><span data-ttu-id="8d393-163">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="8d393-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-165">int</span><span class="sxs-lookup"><span data-stu-id="8d393-165">int</span></span></p></td>
<td><p><span data-ttu-id="8d393-166">Código de respuesta SIP a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="8d393-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="8d393-167">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="8d393-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="8d393-168">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="8d393-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-170">int</span><span class="sxs-lookup"><span data-stu-id="8d393-170">int</span></span></p></td>
<td><p><span data-ttu-id="8d393-171">IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.</span><span class="sxs-lookup"><span data-stu-id="8d393-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-172"><strong>Registrador</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-174">FQDN del registrador.</span><span class="sxs-lookup"><span data-stu-id="8d393-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-175"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-177">FQDN del grupo de servidores que ha capturado los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="8d393-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-180">FQDN del servidor perimetral usado por el usuario que registró.</span><span class="sxs-lookup"><span data-stu-id="8d393-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-182">bit</span><span class="sxs-lookup"><span data-stu-id="8d393-182">bit</span></span></p></td>
<td><p><span data-ttu-id="8d393-183">Indica si el usuario ha iniciado sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="8d393-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-185">bit</span><span class="sxs-lookup"><span data-stu-id="8d393-185">bit</span></span></p></td>
<td><p><span data-ttu-id="8d393-186">Indica si el UserService estaba disponible en el momento del registro.</span><span class="sxs-lookup"><span data-stu-id="8d393-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-188">bit</span><span class="sxs-lookup"><span data-stu-id="8d393-188">bit</span></span></p></td>
<td><p><span data-ttu-id="8d393-189">Indica si el registro se realizó con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="8d393-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-191">BIGINT</span><span class="sxs-lookup"><span data-stu-id="8d393-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="8d393-192">Dirección MAC del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="8d393-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d393-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-195">Fabricante del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="8d393-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="8d393-196">Para obtener más información, consulte la <a href="lync-server-2013-manufacturers-table.md">tabla de fabricantes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d393-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d393-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="8d393-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="8d393-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d393-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d393-199">Versión de hardware del dispositivo registrada.</span><span class="sxs-lookup"><span data-stu-id="8d393-199">Hardware version of the device registered.</span></span> <span data-ttu-id="8d393-200">Para obtener más información, consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d393-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

