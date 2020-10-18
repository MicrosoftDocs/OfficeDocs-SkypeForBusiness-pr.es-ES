---
title: 'Lync Server 2013: vista de registro'
description: 'Lync Server 2013: vista de registro.'
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
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578535"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="9723d-103">Vista de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9723d-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9723d-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9723d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9723d-105">La vista de registro almacena información sobre el registro de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9723d-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="9723d-106">Esta vista se introdujo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9723d-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9723d-107">Columna</span><span class="sxs-lookup"><span data-stu-id="9723d-107">Column</span></span></th>
<th><span data-ttu-id="9723d-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9723d-108">Data Type</span></span></th>
<th><span data-ttu-id="9723d-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="9723d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9723d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9723d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9723d-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="9723d-112">Time of session request.</span></span> <span data-ttu-id="9723d-113">Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="9723d-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9723d-114">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9723d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-116">entero</span><span class="sxs-lookup"><span data-stu-id="9723d-116">int</span></span></p></td>
<td><p><span data-ttu-id="9723d-117">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="9723d-117">ID number to identify the session.</span></span> <span data-ttu-id="9723d-118">Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="9723d-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9723d-119">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9723d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-120"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-121">datetime</span><span class="sxs-lookup"><span data-stu-id="9723d-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="9723d-122">Hora a la que ocurrió el registro.</span><span class="sxs-lookup"><span data-stu-id="9723d-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9723d-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9723d-125">URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="9723d-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-126"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-128">Tipo de URI del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="9723d-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="9723d-129">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9723d-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-130"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-132">Inquilino del usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="9723d-132">Tenant of the user who registered.</span></span> <span data-ttu-id="9723d-133">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9723d-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-135">identificador</span><span class="sxs-lookup"><span data-stu-id="9723d-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9723d-136">Identificador único del extremo con el que se registró el usuario.</span><span class="sxs-lookup"><span data-stu-id="9723d-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-137"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-138">identificador</span><span class="sxs-lookup"><span data-stu-id="9723d-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9723d-139">Identificador único que se utiliza para diferenciar los registros con el mismo usuario y el mismo extremo.</span><span class="sxs-lookup"><span data-stu-id="9723d-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-141">datetime</span><span class="sxs-lookup"><span data-stu-id="9723d-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="9723d-142">Hora a la que ocurrió la anulación de registro.</span><span class="sxs-lookup"><span data-stu-id="9723d-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-145">Motivo de la anulación de registro.</span><span class="sxs-lookup"><span data-stu-id="9723d-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-148">Versión del cliente que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="9723d-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-150">entero</span><span class="sxs-lookup"><span data-stu-id="9723d-150">int</span></span></p></td>
<td><p><span data-ttu-id="9723d-151">Cliente que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="9723d-151">Client used by the user who registered.</span></span> <span data-ttu-id="9723d-152">Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9723d-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9723d-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9723d-155">Categoría del cliente que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="9723d-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-156"><strong>DirIP</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-158">Dirección IP con la que se registró el usuario.</span><span class="sxs-lookup"><span data-stu-id="9723d-158">IP Address the user registered with.</span></span> <span data-ttu-id="9723d-159">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9723d-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-160"><strong>Identificador</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-161">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="9723d-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="9723d-p108">Identificador del diálogo SIP. El formato es:</span><span class="sxs-lookup"><span data-stu-id="9723d-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="9723d-164">Dialog; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="9723d-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-166">entero</span><span class="sxs-lookup"><span data-stu-id="9723d-166">int</span></span></p></td>
<td><p><span data-ttu-id="9723d-p109">Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</span><span class="sxs-lookup"><span data-stu-id="9723d-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-170"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-171">entero</span><span class="sxs-lookup"><span data-stu-id="9723d-171">int</span></span></p></td>
<td><p><span data-ttu-id="9723d-172">Identificador de diagnóstico capturado del encabezado SIP.</span><span class="sxs-lookup"><span data-stu-id="9723d-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-173"><strong>Dominios</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-175">FQDN del registrador.</span><span class="sxs-lookup"><span data-stu-id="9723d-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-176"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-178">FQDN del grupo de servidores que capturó los datos de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9723d-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-181">FQDN del servidor perimetral que utilizó el usuario que se registró.</span><span class="sxs-lookup"><span data-stu-id="9723d-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-183">bit</span><span class="sxs-lookup"><span data-stu-id="9723d-183">bit</span></span></p></td>
<td><p><span data-ttu-id="9723d-184">Indica si el usuario inició sesión desde la red interna.</span><span class="sxs-lookup"><span data-stu-id="9723d-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-186">bit</span><span class="sxs-lookup"><span data-stu-id="9723d-186">bit</span></span></p></td>
<td><p><span data-ttu-id="9723d-187">Indica si el UserService estaba disponible en el momento del registro.</span><span class="sxs-lookup"><span data-stu-id="9723d-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-189">bit</span><span class="sxs-lookup"><span data-stu-id="9723d-189">bit</span></span></p></td>
<td><p><span data-ttu-id="9723d-190">Indica si el registro se realizó con el registrador principal.</span><span class="sxs-lookup"><span data-stu-id="9723d-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-192">BIGINT</span><span class="sxs-lookup"><span data-stu-id="9723d-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="9723d-193">Dirección MAC del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="9723d-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9723d-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-196">Fabricante del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="9723d-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="9723d-197">Consulte la <a href="lync-server-2013-manufacturers-table.md">tabla fabricantes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9723d-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9723d-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9723d-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9723d-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9723d-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9723d-200">Versión del hardware del dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="9723d-200">Hardware version of the device registered.</span></span> <span data-ttu-id="9723d-201">Consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9723d-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

