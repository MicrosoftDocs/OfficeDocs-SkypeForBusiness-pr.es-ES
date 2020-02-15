---
title: 'Lync Server 2013: definición de los requisitos para las llamadas de emergencia'
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
ms.openlocfilehash: 61d388659a747cb8fed339a40a15abd8e33c693e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="b6e72-102">Definición de los requisitos para las llamadas de emergencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6e72-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="b6e72-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="b6e72-104">Antes de comenzar una implementación de Microsoft Lync Server 2013 E9-1-1, primero debe poder responder a las preguntas que se detallan en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="b6e72-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="b6e72-105">La planeación que necesite dependerá del tipo de solución E9-1-1 que haya decidido implementar, ya sea un proveedor de servicios E9-1-1 mediante troncales SIP o una puerta de enlace de número de identificación de ubicación de emergencia (ELIN).</span><span class="sxs-lookup"><span data-stu-id="b6e72-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="b6e72-106">En la siguiente tabla figuran las secciones de este manual de planeación que deberá repasar según cada solución.</span><span class="sxs-lookup"><span data-stu-id="b6e72-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="b6e72-107">Pasos de planeación por tipo de E9-1-1</span><span class="sxs-lookup"><span data-stu-id="b6e72-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6e72-108">Proveedor de servicios troncales SIP</span><span class="sxs-lookup"><span data-stu-id="b6e72-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="b6e72-109">Puerta de enlace ELIN</span><span class="sxs-lookup"><span data-stu-id="b6e72-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6e72-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6e72-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6e72-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitación de usuarios para E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitación de usuarios para E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6e72-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Administración de ubicaciones para proveedores de servicio de tronco de SIP en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Administración de ubicaciones para puertas de enlace de ELIN en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6e72-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6e72-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Diseño del tronco SIP para E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-121"><a href="lync-server-2013-including-the-security-desk.md">Incluir el Departamento de seguridad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6e72-122"><a href="lync-server-2013-including-the-security-desk.md">Incluir el Departamento de seguridad en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-123"><a href="lync-server-2013-defining-the-location-policy.md">Definición de la Directiva de ubicación para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6e72-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Selección de un proveedor de servicios E9-1-1 para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b6e72-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Asignar el ámbito de la Directiva de ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6e72-126"><a href="lync-server-2013-defining-the-location-policy.md">Definición de la Directiva de ubicación para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6e72-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Asignar el ámbito de la Directiva de ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b6e72-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="b6e72-128">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b6e72-128">In This Section</span></span>

  - [<span data-ttu-id="b6e72-129">Definir el ámbito de la implementación de E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="b6e72-130">Definición de los elementos de red que se usan para determinar la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="b6e72-131">Habilitación de usuarios para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="b6e72-132">Administración de ubicaciones para proveedores de servicio de tronco de SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="b6e72-133">Administración de ubicaciones para puertas de enlace de ELIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="b6e72-134">Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="b6e72-135">Diseño del tronco SIP para E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="b6e72-136">Incluir el Departamento de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="b6e72-137">Selección de un proveedor de servicios E9-1-1 para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="b6e72-138">Definición de la Directiva de ubicación para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="b6e72-139">Asignar el ámbito de la Directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e72-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

