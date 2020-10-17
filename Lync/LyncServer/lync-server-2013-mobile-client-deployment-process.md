---
title: 'Lync Server 2013: proceso de implementación de cliente móvil'
description: 'Lync Server 2013: proceso de implementación de clientes móviles.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563486"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="7c275-103">Proceso de implementación de clientes móviles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c275-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c275-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7c275-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7c275-105">Una vez completada la implementación de Microsoft Lync Server 2013, los usuarios pueden instalar la aplicación de Lync 2013 desde el mercado móvil que están acostumbrados a usar para su dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="7c275-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="7c275-106">Proceso de implementación de Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="7c275-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c275-107">Fase</span><span class="sxs-lookup"><span data-stu-id="7c275-107">Phase</span></span></th>
<th><span data-ttu-id="7c275-108">Pasos</span><span class="sxs-lookup"><span data-stu-id="7c275-108">Steps</span></span></th>
<th><span data-ttu-id="7c275-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="7c275-109">Permissions</span></span></th>
<th><span data-ttu-id="7c275-110">Documentación</span><span class="sxs-lookup"><span data-stu-id="7c275-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c275-111">Realizar tareas previas a la configuración.</span><span class="sxs-lookup"><span data-stu-id="7c275-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7c275-112">Compruebe la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c275-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="7c275-113">Compruebe los requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="7c275-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7c275-114">Administrador</span><span class="sxs-lookup"><span data-stu-id="7c275-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="7c275-115"><a href="lync-server-2013-planning-for-mobility.md">Planeación de la movilidad en Lync Server 2013</a> en la documentación de planeación del servidor.</span><span class="sxs-lookup"><span data-stu-id="7c275-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="7c275-116"><a href="lync-server-2013-deploying-mobility.md">Implementación de la movilidad en Lync Server 2013</a> en la documentación de implementación del servidor.</span><span class="sxs-lookup"><span data-stu-id="7c275-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="7c275-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisitos de infraestructura de certificados para Lync Server 2013</a> en la documentación de planeación del servidor.</span><span class="sxs-lookup"><span data-stu-id="7c275-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c275-118">Instale la aplicación Lync en un dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="7c275-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7c275-119">Instale los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="7c275-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="7c275-120">Instale desde el Marketplace específico del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="7c275-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7c275-121">Administrador</span><span class="sxs-lookup"><span data-stu-id="7c275-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="7c275-122">Instrucciones de instalación específicas del dispositivo móvil en <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7c275-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c275-123">Configure el cliente.</span><span class="sxs-lookup"><span data-stu-id="7c275-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7c275-124">Configure la información del servidor y la configuración de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="7c275-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7c275-125">Administrador</span><span class="sxs-lookup"><span data-stu-id="7c275-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="7c275-126"><a href="lync-server-2013-deploying-mobile-clients.md">Implementación de clientes móviles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7c275-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c275-127">Probar los escenarios móviles.</span><span class="sxs-lookup"><span data-stu-id="7c275-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7c275-128">Pruebe la mensajería instantánea (mi) y la presencia.</span><span class="sxs-lookup"><span data-stu-id="7c275-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="7c275-129">Probar la Conferencia de acceso telefónico saliente.</span><span class="sxs-lookup"><span data-stu-id="7c275-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="7c275-130">Busque un contacto en el directorio corporativo.</span><span class="sxs-lookup"><span data-stu-id="7c275-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="7c275-131">Pruebe las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="7c275-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7c275-132">Administrador</span><span class="sxs-lookup"><span data-stu-id="7c275-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="7c275-133">Instrucciones de comprobación específicas del dispositivo móvil en <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7c275-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c275-134">Instale la aplicación Lync en teléfonos móviles.</span><span class="sxs-lookup"><span data-stu-id="7c275-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7c275-135">Instale los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="7c275-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="7c275-136">Instale desde el Marketplace específico del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="7c275-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7c275-137">Usuario</span><span class="sxs-lookup"><span data-stu-id="7c275-137">User</span></span></p></td>
<td><p><span data-ttu-id="7c275-138">Instrucciones de instalación específicas del dispositivo móvil en <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7c275-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

