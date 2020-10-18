---
title: 'Lync Server 2013: tabla de registro'
description: 'Lync Server 2013: tabla de registro.'
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
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578536"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="74479-103">Tabla de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74479-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74479-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="74479-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="74479-105">Cada registro representa un evento de registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="74479-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74479-106">Columna</span><span class="sxs-lookup"><span data-stu-id="74479-106">Column</span></span></th>
<th><span data-ttu-id="74479-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="74479-107">Data Type</span></span></th>
<th><span data-ttu-id="74479-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="74479-108">Key/Index</span></span></th>
<th><span data-ttu-id="74479-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="74479-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74479-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="74479-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-111">datetime</span><span class="sxs-lookup"><span data-stu-id="74479-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="74479-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="74479-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-113">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="74479-113">Time of session request.</span></span> <span data-ttu-id="74479-114">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="74479-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="74479-115">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="74479-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-117">entero</span><span class="sxs-lookup"><span data-stu-id="74479-117">int</span></span></p></td>
<td><p><span data-ttu-id="74479-118">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="74479-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-119">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="74479-119">ID number to identify the session.</span></span> <span data-ttu-id="74479-120">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="74479-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="74479-121">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-123">entero</span><span class="sxs-lookup"><span data-stu-id="74479-123">int</span></span></p></td>
<td><p><span data-ttu-id="74479-124">Externa</span><span class="sxs-lookup"><span data-stu-id="74479-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-125">Identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="74479-125">The user ID.</span></span> <span data-ttu-id="74479-126">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-128">identificador</span><span class="sxs-lookup"><span data-stu-id="74479-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-p104">GUID para identificar un extremo de registro. Por lo general, el evento de registro del mismo equipo y del mismo usuario tendrá el mismo identificador de extremo. Los equipos diferentes tienen un identificador de extremo distinto.</span><span class="sxs-lookup"><span data-stu-id="74479-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-132"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="74479-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-133">Identificador</span><span class="sxs-lookup"><span data-stu-id="74479-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-134">Id. usado para diferenciar registros que implican al mismo usuario y al mismo extremo.</span><span class="sxs-lookup"><span data-stu-id="74479-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="74479-135">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74479-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-137">entero</span><span class="sxs-lookup"><span data-stu-id="74479-137">int</span></span></p></td>
<td><p><span data-ttu-id="74479-138">Externa</span><span class="sxs-lookup"><span data-stu-id="74479-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-139">Versión de cliente del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="74479-139">Client version of current user.</span></span> <span data-ttu-id="74479-140">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-141"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-142">entero</span><span class="sxs-lookup"><span data-stu-id="74479-142">int</span></span></p></td>
<td><p><span data-ttu-id="74479-143">Externa</span><span class="sxs-lookup"><span data-stu-id="74479-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-144">Identificador del servidor registrador utilizado para el registro.</span><span class="sxs-lookup"><span data-stu-id="74479-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="74479-145">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-146"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-147">entero</span><span class="sxs-lookup"><span data-stu-id="74479-147">int</span></span></p></td>
<td><p><span data-ttu-id="74479-148">Externa</span><span class="sxs-lookup"><span data-stu-id="74479-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-149">Identificador del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="74479-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="74479-150">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-152">entero</span><span class="sxs-lookup"><span data-stu-id="74479-152">int</span></span></p></td>
<td><p><span data-ttu-id="74479-153">Externa</span><span class="sxs-lookup"><span data-stu-id="74479-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-154">Servidor perimetral que se utiliza para el registro.</span><span class="sxs-lookup"><span data-stu-id="74479-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="74479-155">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="74479-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-157">Bit</span><span class="sxs-lookup"><span data-stu-id="74479-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-158">Si el usuario inició sesión de forma interna o no.</span><span class="sxs-lookup"><span data-stu-id="74479-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="74479-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-160">bit</span><span class="sxs-lookup"><span data-stu-id="74479-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-161">Si UserService está disponible o no.</span><span class="sxs-lookup"><span data-stu-id="74479-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="74479-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-163">bit</span><span class="sxs-lookup"><span data-stu-id="74479-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-164">Si el registro se realizó con el registrador principal o no.</span><span class="sxs-lookup"><span data-stu-id="74479-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="74479-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-166">bit</span><span class="sxs-lookup"><span data-stu-id="74479-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-167">Indica si el usuario se registra o no con una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="74479-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="74479-168">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74479-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-169"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="74479-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-170">datetime</span><span class="sxs-lookup"><span data-stu-id="74479-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-171">Hora de registro.</span><span class="sxs-lookup"><span data-stu-id="74479-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-172"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="74479-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-173">datetime</span><span class="sxs-lookup"><span data-stu-id="74479-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-174">Hora de anulación del registro.</span><span class="sxs-lookup"><span data-stu-id="74479-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="74479-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-176">entero</span><span class="sxs-lookup"><span data-stu-id="74479-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-177">Código de respuesta de la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="74479-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-178"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-179">entero</span><span class="sxs-lookup"><span data-stu-id="74479-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-p109">Identificador de diagnóstico de la solicitud de registro. Indica ese tipo de información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="74479-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-183">entero</span><span class="sxs-lookup"><span data-stu-id="74479-183">int</span></span></p></td>
<td><p><span data-ttu-id="74479-184">Externa</span><span class="sxs-lookup"><span data-stu-id="74479-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-185">Dispositivo del cual proviene la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="74479-185">The device that the register request is coming from.</span></span> <span data-ttu-id="74479-186">Consulte la <a href="lync-server-2013-devices-table.md">tabla dispositivos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74479-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="74479-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="74479-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="74479-189">Externa</span><span class="sxs-lookup"><span data-stu-id="74479-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74479-190">El motivo de la eliminación de registro, como "Iniciado por el usuario", "registro expirado", "error del cliente" y más.</span><span class="sxs-lookup"><span data-stu-id="74479-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="74479-191">Consulte la <a href="lync-server-2013-deregistertype-table.md">tabla DeRegisterType en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="74479-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74479-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="74479-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="74479-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74479-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74479-194">Dirección IP del extremo con el que está registrado el usuario.</span><span class="sxs-lookup"><span data-stu-id="74479-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="74479-195">Esta puede ser una dirección IPv4 o una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="74479-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="74479-196">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74479-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

