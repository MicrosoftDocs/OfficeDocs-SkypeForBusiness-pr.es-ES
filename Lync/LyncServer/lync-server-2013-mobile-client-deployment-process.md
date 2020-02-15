---
title: 'Lync Server 2013: proceso de implementación de cliente móvil'
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
ms.openlocfilehash: 841b0349818fd94d828e3aaa93b3f7c9a99f9f00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="80046-102">Proceso de implementación de clientes móviles en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80046-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80046-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="80046-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="80046-104">Una vez completada la implementación de Microsoft Lync Server 2013, los usuarios pueden instalar la aplicación de Lync 2013 desde el mercado móvil que están acostumbrados a usar para su dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="80046-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="80046-105">Proceso de implementación de Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="80046-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80046-106">Fase</span><span class="sxs-lookup"><span data-stu-id="80046-106">Phase</span></span></th>
<th><span data-ttu-id="80046-107">Pasos</span><span class="sxs-lookup"><span data-stu-id="80046-107">Steps</span></span></th>
<th><span data-ttu-id="80046-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="80046-108">Permissions</span></span></th>
<th><span data-ttu-id="80046-109">Documentación</span><span class="sxs-lookup"><span data-stu-id="80046-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80046-110">Realizar tareas previas a la configuración.</span><span class="sxs-lookup"><span data-stu-id="80046-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="80046-111">Compruebe la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80046-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="80046-112">Compruebe los requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="80046-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="80046-113">Administrador</span><span class="sxs-lookup"><span data-stu-id="80046-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="80046-114"><a href="lync-server-2013-planning-for-mobility.md">Planeación de la movilidad en Lync Server 2013</a> en la documentación de planeación del servidor.</span><span class="sxs-lookup"><span data-stu-id="80046-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="80046-115"><a href="lync-server-2013-deploying-mobility.md">Implementación de la movilidad en Lync Server 2013</a> en la documentación de implementación del servidor.</span><span class="sxs-lookup"><span data-stu-id="80046-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="80046-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisitos de infraestructura de certificados para Lync Server 2013</a> en la documentación de planeación del servidor.</span><span class="sxs-lookup"><span data-stu-id="80046-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80046-117">Instale la aplicación Lync en un dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="80046-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="80046-118">Instale los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="80046-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="80046-119">Instale desde el Marketplace específico del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="80046-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="80046-120">Administrador</span><span class="sxs-lookup"><span data-stu-id="80046-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="80046-121">Instrucciones de instalación específicas del dispositivo móvil en <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="80046-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80046-122">Configure el cliente.</span><span class="sxs-lookup"><span data-stu-id="80046-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="80046-123">Configure la información del servidor y la configuración de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="80046-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80046-124">Administrador</span><span class="sxs-lookup"><span data-stu-id="80046-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="80046-125"><a href="lync-server-2013-deploying-mobile-clients.md">Implementación de clientes móviles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80046-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80046-126">Probar los escenarios móviles.</span><span class="sxs-lookup"><span data-stu-id="80046-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="80046-127">Pruebe la mensajería instantánea (mi) y la presencia.</span><span class="sxs-lookup"><span data-stu-id="80046-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="80046-128">Probar la Conferencia de acceso telefónico saliente.</span><span class="sxs-lookup"><span data-stu-id="80046-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="80046-129">Busque un contacto en el directorio corporativo.</span><span class="sxs-lookup"><span data-stu-id="80046-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="80046-130">Pruebe las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="80046-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="80046-131">Administrador</span><span class="sxs-lookup"><span data-stu-id="80046-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="80046-132">Instrucciones de comprobación específicas del dispositivo móvil en <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="80046-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80046-133">Instale la aplicación Lync en teléfonos móviles.</span><span class="sxs-lookup"><span data-stu-id="80046-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="80046-134">Instale los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="80046-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="80046-135">Instale desde el Marketplace específico del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="80046-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="80046-136">Usuario</span><span class="sxs-lookup"><span data-stu-id="80046-136">User</span></span></p></td>
<td><p><span data-ttu-id="80046-137">Instrucciones de instalación específicas del dispositivo móvil en <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="80046-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

