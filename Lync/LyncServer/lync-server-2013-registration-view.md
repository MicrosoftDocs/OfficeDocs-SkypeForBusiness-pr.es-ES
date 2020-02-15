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
ms.openlocfilehash: a7418c5aa80e35d783517a86626dd2b77a393e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="a23b0-102">Vista de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a23b0-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a23b0-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a23b0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a23b0-104">La vista de registro almacena información sobre el registro de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a23b0-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="a23b0-105">Esta vista se introdujo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a23b0-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a23b0-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a23b0-106">Column</span></span></th>
<th><span data-ttu-id="a23b0-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a23b0-107">Data Type</span></span></th>
<th><span data-ttu-id="a23b0-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="a23b0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a23b0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a23b0-111">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="a23b0-111">Time of session request.</span></span> <span data-ttu-id="a23b0-112">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="a23b0-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a23b0-113">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a23b0-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-115">int</span><span class="sxs-lookup"><span data-stu-id="a23b0-115">int</span></span></p></td>
<td><p><span data-ttu-id="a23b0-116">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="a23b0-116">ID number to identify the session.</span></span> <span data-ttu-id="a23b0-117">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="a23b0-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a23b0-118">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a23b0-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-120">datetime</span><span class="sxs-lookup"><span data-stu-id="a23b0-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="a23b0-121">Hora a la que ocurrió el registro.</span><span class="sxs-lookup"><span data-stu-id="a23b0-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a23b0-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-124">URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="a23b0-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-127">Tipo de URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="a23b0-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="a23b0-128">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a23b0-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-131">Inquilino del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="a23b0-131">Tenant of the user who registered.</span></span> <span data-ttu-id="a23b0-132">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a23b0-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-134">identificador</span><span class="sxs-lookup"><span data-stu-id="a23b0-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a23b0-135">Identificador único del extremo con el que se registró el usuario.</span><span class="sxs-lookup"><span data-stu-id="a23b0-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-137">identificador</span><span class="sxs-lookup"><span data-stu-id="a23b0-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a23b0-138">Identificador único que se utiliza para diferenciar los registros con el mismo usuario y el mismo extremo.</span><span class="sxs-lookup"><span data-stu-id="a23b0-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-140">datetime</span><span class="sxs-lookup"><span data-stu-id="a23b0-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="a23b0-141">Hora a la que ocurrió la anulación de registro.</span><span class="sxs-lookup"><span data-stu-id="a23b0-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-144">Motivo de la anulación de registro.</span><span class="sxs-lookup"><span data-stu-id="a23b0-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-147">Versión del cliente que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="a23b0-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-149">int</span><span class="sxs-lookup"><span data-stu-id="a23b0-149">int</span></span></p></td>
<td><p><span data-ttu-id="a23b0-150">Cliente que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="a23b0-150">Client used by the user who registered.</span></span> <span data-ttu-id="a23b0-151">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a23b0-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a23b0-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-154">Categoría del cliente que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="a23b0-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-155"><strong>DirIP</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-157">Dirección IP con la que se registró el usuario.</span><span class="sxs-lookup"><span data-stu-id="a23b0-157">IP Address the user registered with.</span></span> <span data-ttu-id="a23b0-158">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="a23b0-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-159"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="a23b0-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-p108">Identificador del diálogo SIP. El formato es:</span><span class="sxs-lookup"><span data-stu-id="a23b0-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="a23b0-163">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="a23b0-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-165">int</span><span class="sxs-lookup"><span data-stu-id="a23b0-165">int</span></span></p></td>
<td><p><span data-ttu-id="a23b0-p109">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="a23b0-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-170">int</span><span class="sxs-lookup"><span data-stu-id="a23b0-170">int</span></span></p></td>
<td><p><span data-ttu-id="a23b0-171">Identificador de diagnóstico capturado del encabezado SIP.</span><span class="sxs-lookup"><span data-stu-id="a23b0-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-172"><strong>Dominios</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-174">FQDN del registrador.</span><span class="sxs-lookup"><span data-stu-id="a23b0-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-177">FQDN del grupo de servidores que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a23b0-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-180">FQDN del servidor perimetral que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="a23b0-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-182">bit</span><span class="sxs-lookup"><span data-stu-id="a23b0-182">bit</span></span></p></td>
<td><p><span data-ttu-id="a23b0-183">Indica si el usuario inició sesión desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="a23b0-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-185">bit</span><span class="sxs-lookup"><span data-stu-id="a23b0-185">bit</span></span></p></td>
<td><p><span data-ttu-id="a23b0-186">Indica si el UserService estaba disponible en el momento del registro.</span><span class="sxs-lookup"><span data-stu-id="a23b0-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-188">bit</span><span class="sxs-lookup"><span data-stu-id="a23b0-188">bit</span></span></p></td>
<td><p><span data-ttu-id="a23b0-189">Indica si el registro se realizó con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="a23b0-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-191">BIGINT</span><span class="sxs-lookup"><span data-stu-id="a23b0-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="a23b0-192">Dirección MAC del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="a23b0-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a23b0-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-195">Fabricante del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="a23b0-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="a23b0-196">Consulte la <a href="lync-server-2013-manufacturers-table.md">tabla fabricantes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a23b0-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a23b0-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a23b0-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a23b0-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a23b0-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a23b0-199">Versión del hardware del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="a23b0-199">Hardware version of the device registered.</span></span> <span data-ttu-id="a23b0-200">Consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a23b0-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

