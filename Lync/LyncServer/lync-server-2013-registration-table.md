---
title: 'Lync Server 2013: tabla de registro'
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
ms.openlocfilehash: 4c40fddd324cd687b54d0c3317edc533fa559c8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536697"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="a5979-102">Tabla de registro en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5979-102">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5979-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a5979-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a5979-104">Cada registro representa un evento de registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="a5979-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5979-105">Columna</span><span class="sxs-lookup"><span data-stu-id="a5979-105">Column</span></span></th>
<th><span data-ttu-id="a5979-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a5979-106">Data Type</span></span></th>
<th><span data-ttu-id="a5979-107">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="a5979-107">Key/Index</span></span></th>
<th><span data-ttu-id="a5979-108">Detalles</span><span class="sxs-lookup"><span data-stu-id="a5979-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5979-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a5979-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a5979-111">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="a5979-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-112">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="a5979-112">Time of session request.</span></span> <span data-ttu-id="a5979-113">Se usa junto con <strong>SessionIdSeq</strong> para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a5979-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a5979-114">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-116">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-116">int</span></span></p></td>
<td><p><span data-ttu-id="a5979-117">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="a5979-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-118">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="a5979-118">ID number to identify the session.</span></span> <span data-ttu-id="a5979-119">Se usa en combinación con <strong>SessionIdTime</strong> para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="a5979-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a5979-120">Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-122">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-122">int</span></span></p></td>
<td><p><span data-ttu-id="a5979-123">Externa</span><span class="sxs-lookup"><span data-stu-id="a5979-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-124">Identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="a5979-124">The user ID.</span></span> <span data-ttu-id="a5979-125">Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-127">identificador</span><span class="sxs-lookup"><span data-stu-id="a5979-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-p104">GUID para identificar un extremo de registro. Por lo general, el evento de registro del mismo equipo y del mismo usuario tendrá el mismo identificador de extremo. Los equipos diferentes tienen un identificador de extremo distinto.</span><span class="sxs-lookup"><span data-stu-id="a5979-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-132">Identificador</span><span class="sxs-lookup"><span data-stu-id="a5979-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-133">Id. usado para diferenciar registros que implican al mismo usuario y al mismo extremo.</span><span class="sxs-lookup"><span data-stu-id="a5979-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="a5979-134">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5979-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-136">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-136">int</span></span></p></td>
<td><p><span data-ttu-id="a5979-137">Externa</span><span class="sxs-lookup"><span data-stu-id="a5979-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-138">Versión de cliente del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a5979-138">Client version of current user.</span></span> <span data-ttu-id="a5979-139">Consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-141">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-141">int</span></span></p></td>
<td><p><span data-ttu-id="a5979-142">Externa</span><span class="sxs-lookup"><span data-stu-id="a5979-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-143">Identificador del servidor registrador utilizado para el registro.</span><span class="sxs-lookup"><span data-stu-id="a5979-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="a5979-144">Consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-146">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-146">int</span></span></p></td>
<td><p><span data-ttu-id="a5979-147">Externa</span><span class="sxs-lookup"><span data-stu-id="a5979-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-148">Identificador del grupo en el que se capturó la sesión.</span><span class="sxs-lookup"><span data-stu-id="a5979-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="a5979-149">Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-151">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-151">int</span></span></p></td>
<td><p><span data-ttu-id="a5979-152">Externa</span><span class="sxs-lookup"><span data-stu-id="a5979-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-153">Servidor perimetral que se utiliza para el registro.</span><span class="sxs-lookup"><span data-stu-id="a5979-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="a5979-154">Consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-156">Bit</span><span class="sxs-lookup"><span data-stu-id="a5979-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-157">Si el usuario inició sesión de forma interna o no.</span><span class="sxs-lookup"><span data-stu-id="a5979-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-159">bit</span><span class="sxs-lookup"><span data-stu-id="a5979-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-160">Si UserService está disponible o no.</span><span class="sxs-lookup"><span data-stu-id="a5979-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-162">bit</span><span class="sxs-lookup"><span data-stu-id="a5979-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-163">Si el registro se realizó con el registrador principal o no.</span><span class="sxs-lookup"><span data-stu-id="a5979-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-165">bit</span><span class="sxs-lookup"><span data-stu-id="a5979-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-166">Indica si el usuario se registra o no con una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a5979-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="a5979-167">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5979-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-169">datetime</span><span class="sxs-lookup"><span data-stu-id="a5979-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-170">Hora de registro.</span><span class="sxs-lookup"><span data-stu-id="a5979-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-172">datetime</span><span class="sxs-lookup"><span data-stu-id="a5979-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-173">Hora de anulación del registro.</span><span class="sxs-lookup"><span data-stu-id="a5979-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-175">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-176">Código de respuesta de la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="a5979-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-178">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-p109">Identificador de diagnóstico de la solicitud de registro. Indica ese tipo de información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a5979-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-182">entero</span><span class="sxs-lookup"><span data-stu-id="a5979-182">int</span></span></p></td>
<td><p><span data-ttu-id="a5979-183">Externa</span><span class="sxs-lookup"><span data-stu-id="a5979-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-184">Dispositivo del cual proviene la solicitud de registro.</span><span class="sxs-lookup"><span data-stu-id="a5979-184">The device that the register request is coming from.</span></span> <span data-ttu-id="a5979-185">Consulte la <a href="lync-server-2013-devices-table.md">tabla dispositivos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5979-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5979-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a5979-188">Externa</span><span class="sxs-lookup"><span data-stu-id="a5979-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5979-189">El motivo de la eliminación de registro, como "Iniciado por el usuario", "registro expirado", "error del cliente" y más.</span><span class="sxs-lookup"><span data-stu-id="a5979-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="a5979-190">Consulte la <a href="lync-server-2013-deregistertype-table.md">tabla DeRegisterType en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a5979-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5979-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a5979-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a5979-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a5979-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5979-193">Dirección IP del extremo con el que está registrado el usuario.</span><span class="sxs-lookup"><span data-stu-id="a5979-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="a5979-194">Esta puede ser una dirección IPv4 o una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="a5979-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="a5979-195">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5979-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

