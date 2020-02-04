---
title: 'Lync Server 2013: Definición de los requisitos para llamadas de emergencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4b1e196a95d19a06c502cc9aeb989d6806b06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="6c28c-102">Definición de los requisitos para llamadas de emergencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c28c-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="6c28c-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="6c28c-104">Antes de empezar una implementación de Microsoft Lync Server 2013 E9-1-1, primero debe poder responder a las preguntas detalladas en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="6c28c-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="6c28c-105">La planeación que necesite dependerá del tipo de solución E9-1-1 que haya decidido implementar, ya sea un proveedor de servicios E9-1-1 por medio de un tronco SIP o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="6c28c-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="6c28c-106">En la siguiente tabla figuran las secciones de este manual de planificación que necesitará repasar según cada solución.</span><span class="sxs-lookup"><span data-stu-id="6c28c-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="6c28c-107">Pasos de planeación por tipo de E9-1-1</span><span class="sxs-lookup"><span data-stu-id="6c28c-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c28c-108">Proveedor de servicios troncales SIP</span><span class="sxs-lookup"><span data-stu-id="6c28c-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="6c28c-109">Puerta de enlace ELIN</span><span class="sxs-lookup"><span data-stu-id="6c28c-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c28c-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c28c-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c28c-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitar usuarios para E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitar usuarios para E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c28c-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Administración de ubicaciones para proveedores de servicios de tronco de SIP en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Administrar ubicaciones de puertas de enlace de ELIN en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c28c-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para la adquisición manual de una ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para la adquisición manual de una ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c28c-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Diseño del tronco del SIP para E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-121"><a href="lync-server-2013-including-the-security-desk.md">Incluido el escritorio de seguridad de Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c28c-122"><a href="lync-server-2013-including-the-security-desk.md">Incluido el escritorio de seguridad de Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-123"><a href="lync-server-2013-defining-the-location-policy.md">Definir la Directiva de ubicación de Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c28c-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Elección de un proveedor de servicios de E9-1-1 para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c28c-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Asignación de un ámbito de directivas de ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c28c-126"><a href="lync-server-2013-defining-the-location-policy.md">Definir la Directiva de ubicación de Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c28c-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Asignación de un ámbito de directivas de ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c28c-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="6c28c-128">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6c28c-128">In This Section</span></span>

  - [<span data-ttu-id="6c28c-129">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="6c28c-130">Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="6c28c-131">Habilitar usuarios para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="6c28c-132">Administración de ubicaciones para proveedores de servicios de tronco de SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="6c28c-133">Administrar ubicaciones de puertas de enlace de ELIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="6c28c-134">Definir la experiencia de usuario para la adquisición manual de una ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="6c28c-135">Diseño del tronco del SIP para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="6c28c-136">Incluido el escritorio de seguridad de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="6c28c-137">Elección de un proveedor de servicios de E9-1-1 para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="6c28c-138">Definir la Directiva de ubicación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="6c28c-139">Asignación de un ámbito de directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c28c-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

