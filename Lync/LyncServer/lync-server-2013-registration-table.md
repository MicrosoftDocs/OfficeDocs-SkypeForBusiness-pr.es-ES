---
title: 'Lync Server 2013: Tabla Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="355b9-102">Tabla Registration en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="355b9-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="355b9-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="355b9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="355b9-104">Cada registro representa un evento de registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="355b9-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="355b9-105">Columna</span><span class="sxs-lookup"><span data-stu-id="355b9-105">Column</span></span></th>
<th><span data-ttu-id="355b9-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="355b9-106">Data Type</span></span></th>
<th><span data-ttu-id="355b9-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="355b9-107">Key/Index</span></span></th>
<th><span data-ttu-id="355b9-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="355b9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="355b9-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="355b9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="355b9-111">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="355b9-112">Time of session request.</span></span> <span data-ttu-id="355b9-113">Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="355b9-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="355b9-114">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-116">int</span><span class="sxs-lookup"><span data-stu-id="355b9-116">int</span></span></p></td>
<td><p><span data-ttu-id="355b9-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-118">Número de identificación para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="355b9-118">ID number to identify the session.</span></span> <span data-ttu-id="355b9-119">Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="355b9-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="355b9-120">Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-121"><strong>Iddeusuario</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-122">int</span><span class="sxs-lookup"><span data-stu-id="355b9-122">int</span></span></p></td>
<td><p><span data-ttu-id="355b9-123">Extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-124">El identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="355b9-124">The user ID.</span></span> <span data-ttu-id="355b9-125">Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-127">identificador</span><span class="sxs-lookup"><span data-stu-id="355b9-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-128">Un GUID para identificar un extremo de registro.</span><span class="sxs-lookup"><span data-stu-id="355b9-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="355b9-129">Normalmente, el evento Register del mismo equipo del mismo usuario tendrá el mismo identificador de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="355b9-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="355b9-130">Diferentes equipos tienen un identificador de extremo diferente.</span><span class="sxs-lookup"><span data-stu-id="355b9-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-132">Identificador</span><span class="sxs-lookup"><span data-stu-id="355b9-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-133">IDENTIFICADOR usado para diferenciar los registros que implican el mismo usuario y el mismo punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="355b9-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="355b9-134">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="355b9-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-136">int</span><span class="sxs-lookup"><span data-stu-id="355b9-136">int</span></span></p></td>
<td><p><span data-ttu-id="355b9-137">Extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-138">Versión de cliente del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="355b9-138">Client version of current user.</span></span> <span data-ttu-id="355b9-139">Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-141">int</span><span class="sxs-lookup"><span data-stu-id="355b9-141">int</span></span></p></td>
<td><p><span data-ttu-id="355b9-142">Extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-143">IDENTIFICADOR del servidor del registrador usado para el registro.</span><span class="sxs-lookup"><span data-stu-id="355b9-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="355b9-144">Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-146">int</span><span class="sxs-lookup"><span data-stu-id="355b9-146">int</span></span></p></td>
<td><p><span data-ttu-id="355b9-147">Extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-148">IDENTIFICADOR del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="355b9-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="355b9-149">Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-151">int</span><span class="sxs-lookup"><span data-stu-id="355b9-151">int</span></span></p></td>
<td><p><span data-ttu-id="355b9-152">Extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-153">Servidor perimetral en el que se está realizando la inscripción.</span><span class="sxs-lookup"><span data-stu-id="355b9-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="355b9-154">Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-156">Algo</span><span class="sxs-lookup"><span data-stu-id="355b9-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-157">Si el usuario ha iniciado sesión desde dentro o no.</span><span class="sxs-lookup"><span data-stu-id="355b9-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-159">bit</span><span class="sxs-lookup"><span data-stu-id="355b9-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-160">Si el UserService está disponible o no.</span><span class="sxs-lookup"><span data-stu-id="355b9-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-162">bit</span><span class="sxs-lookup"><span data-stu-id="355b9-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-163">Si se registra en el registrador principal o no.</span><span class="sxs-lookup"><span data-stu-id="355b9-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-165">bit</span><span class="sxs-lookup"><span data-stu-id="355b9-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-166">Indica si el usuario está registrado o no en un equipo de sucursal con la supervivencia.</span><span class="sxs-lookup"><span data-stu-id="355b9-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="355b9-167">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="355b9-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-169">datetime</span><span class="sxs-lookup"><span data-stu-id="355b9-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-170">Hora de registro.</span><span class="sxs-lookup"><span data-stu-id="355b9-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-172">datetime</span><span class="sxs-lookup"><span data-stu-id="355b9-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-173">Hora de Desregistro.</span><span class="sxs-lookup"><span data-stu-id="355b9-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-175">int</span><span class="sxs-lookup"><span data-stu-id="355b9-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-176">Código de respuesta de la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="355b9-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-178">int</span><span class="sxs-lookup"><span data-stu-id="355b9-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-179">IDENTIFICADOR de diagnóstico de la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="355b9-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="355b9-180">Indica que el tipo de información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="355b9-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-181"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-182">int</span><span class="sxs-lookup"><span data-stu-id="355b9-182">int</span></span></p></td>
<td><p><span data-ttu-id="355b9-183">Extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-184">El dispositivo del que procede la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="355b9-184">The device that the register request is coming from.</span></span> <span data-ttu-id="355b9-185">Para obtener más información, consulte la <a href="lync-server-2013-devices-table.md">tabla dispositivos en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="355b9-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="355b9-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="355b9-188">Extranjero</span><span class="sxs-lookup"><span data-stu-id="355b9-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="355b9-189">El motivo de la anulación del registro, como "Iniciado por el usuario", "registro expirado", "error del cliente" y más.</span><span class="sxs-lookup"><span data-stu-id="355b9-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="355b9-190">Para obtener más información, consulte la <a href="lync-server-2013-deregistertype-table.md">tabla DeRegisterType en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="355b9-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="355b9-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="355b9-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="355b9-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="355b9-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="355b9-193">Dirección IP del extremo con el que el usuario registró el registro.</span><span class="sxs-lookup"><span data-stu-id="355b9-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="355b9-194">Puede ser una dirección IPv4 o una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="355b9-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="355b9-195">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="355b9-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

