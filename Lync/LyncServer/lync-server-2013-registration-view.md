---
title: 'Lync Server 2013: vista de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="0b62a-102">Vista de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b62a-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b62a-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0b62a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0b62a-104">La vista de registro almacena información sobre el registro de usuarios.</span><span class="sxs-lookup"><span data-stu-id="0b62a-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="0b62a-105">Esta vista se presentó en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b62a-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b62a-106">Columna</span><span class="sxs-lookup"><span data-stu-id="0b62a-106">Column</span></span></th>
<th><span data-ttu-id="0b62a-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="0b62a-107">Data Type</span></span></th>
<th><span data-ttu-id="0b62a-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="0b62a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0b62a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b62a-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-111">Time of session request.</span></span> <span data-ttu-id="0b62a-112">Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="0b62a-113">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b62a-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-115">int</span><span class="sxs-lookup"><span data-stu-id="0b62a-115">int</span></span></p></td>
<td><p><span data-ttu-id="0b62a-116">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-116">ID number to identify the session.</span></span> <span data-ttu-id="0b62a-117">Se usa en conjunción con SessionIdTime para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="0b62a-118">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b62a-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-120">datetime</span><span class="sxs-lookup"><span data-stu-id="0b62a-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b62a-121">Hora en la que se realizó el registro.</span><span class="sxs-lookup"><span data-stu-id="0b62a-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0b62a-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-124">Identificador URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-127">Tipo de URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="0b62a-128">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b62a-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-131">Inquilino del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-131">Tenant of the user who registered.</span></span> <span data-ttu-id="0b62a-132">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b62a-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-134">identificador</span><span class="sxs-lookup"><span data-stu-id="0b62a-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="0b62a-135">Identificador único del extremo del usuario registrado con.</span><span class="sxs-lookup"><span data-stu-id="0b62a-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-137">identificador</span><span class="sxs-lookup"><span data-stu-id="0b62a-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="0b62a-138">Identificador único que se usa para diferenciar los registros que implican al mismo usuario y al mismo punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-140">datetime</span><span class="sxs-lookup"><span data-stu-id="0b62a-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="0b62a-141">Hora en la que se produjo la anulación de inscripción.</span><span class="sxs-lookup"><span data-stu-id="0b62a-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-144">Motivo de la anulación del registro.</span><span class="sxs-lookup"><span data-stu-id="0b62a-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-147">Versión del cliente que usó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-148"><strong>Tipocliente</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-149">int</span><span class="sxs-lookup"><span data-stu-id="0b62a-149">int</span></span></p></td>
<td><p><span data-ttu-id="0b62a-150">Cliente usado por el usuario que registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-150">Client used by the user who registered.</span></span> <span data-ttu-id="0b62a-151">Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b62a-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="0b62a-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-154">Categoría del cliente que ha usado el usuario que registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-155"><strong>Dirección IP</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-157">Dirección IP con la que el usuario se registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-157">IP Address the user registered with.</span></span> <span data-ttu-id="0b62a-158">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="0b62a-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="0b62a-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-161">IDENTIFICACIÓN del cuadro de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="0b62a-161">SIP dialog ID.</span></span> <span data-ttu-id="0b62a-162">El formato de es:</span><span class="sxs-lookup"><span data-stu-id="0b62a-162">The format of the is:</span></span></p>
<p><span data-ttu-id="0b62a-163">cuadro de diálogo; desde: etiqueta; to-Tag</span><span class="sxs-lookup"><span data-stu-id="0b62a-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-165">int</span><span class="sxs-lookup"><span data-stu-id="0b62a-165">int</span></span></p></td>
<td><p><span data-ttu-id="0b62a-166">Código de respuesta SIP a la invitación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="0b62a-167">Por lo general, este campo se rellena con los datos generados desde el mensaje de invitación inicial de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="0b62a-168">Si no hay ningún mensaje de invitación, el campo se rellena con la fecha y la hora del primer mensaje SIP pertinente (BYE, cancelar, mensaje o información).</span><span class="sxs-lookup"><span data-stu-id="0b62a-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-170">int</span><span class="sxs-lookup"><span data-stu-id="0b62a-170">int</span></span></p></td>
<td><p><span data-ttu-id="0b62a-171">IDENTIFICACIÓN de diagnóstico capturada del encabezado de SIP.</span><span class="sxs-lookup"><span data-stu-id="0b62a-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-172"><strong>Registrador</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-174">FQDN del registrador.</span><span class="sxs-lookup"><span data-stu-id="0b62a-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-175"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-177">FQDN del grupo de servidores que ha capturado los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="0b62a-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-180">FQDN del servidor perimetral usado por el usuario que registró.</span><span class="sxs-lookup"><span data-stu-id="0b62a-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-182">bit</span><span class="sxs-lookup"><span data-stu-id="0b62a-182">bit</span></span></p></td>
<td><p><span data-ttu-id="0b62a-183">Indica si el usuario ha iniciado sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="0b62a-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-185">bit</span><span class="sxs-lookup"><span data-stu-id="0b62a-185">bit</span></span></p></td>
<td><p><span data-ttu-id="0b62a-186">Indica si el UserService estaba disponible en el momento del registro.</span><span class="sxs-lookup"><span data-stu-id="0b62a-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-188">bit</span><span class="sxs-lookup"><span data-stu-id="0b62a-188">bit</span></span></p></td>
<td><p><span data-ttu-id="0b62a-189">Indica si el registro se realizó con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="0b62a-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-191">BIGINT</span><span class="sxs-lookup"><span data-stu-id="0b62a-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="0b62a-192">Dirección MAC del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="0b62a-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b62a-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-195">Fabricante del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="0b62a-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="0b62a-196">Para obtener más información, consulte la <a href="lync-server-2013-manufacturers-table.md">tabla de fabricantes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b62a-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b62a-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="0b62a-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="0b62a-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b62a-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0b62a-199">Versión de hardware del dispositivo registrada.</span><span class="sxs-lookup"><span data-stu-id="0b62a-199">Hardware version of the device registered.</span></span> <span data-ttu-id="0b62a-200">Para obtener más información, consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0b62a-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

