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
ms.openlocfilehash: e6beaeac91dae0ff5fbf755c4ccb33cae288df75
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="c2744-102">Proceso de implementación de cliente móvil en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2744-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2744-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="c2744-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="c2744-104">Una vez completada una implementación de Microsoft Lync Server 2013, los usuarios pueden instalar la aplicación Lync 2013 desde el Marketplace móvil, que están acostumbrados a usar para su dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="c2744-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="c2744-105">Proceso de implementación de Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="c2744-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2744-106">Fase</span><span class="sxs-lookup"><span data-stu-id="c2744-106">Phase</span></span></th>
<th><span data-ttu-id="c2744-107">Pasos</span><span class="sxs-lookup"><span data-stu-id="c2744-107">Steps</span></span></th>
<th><span data-ttu-id="c2744-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="c2744-108">Permissions</span></span></th>
<th><span data-ttu-id="c2744-109">Documentación</span><span class="sxs-lookup"><span data-stu-id="c2744-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2744-110">Realizar tareas previas a la configuración.</span><span class="sxs-lookup"><span data-stu-id="c2744-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c2744-111">Compruebe la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2744-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="c2744-112">Comprobar los requisitos de los certificados.</span><span class="sxs-lookup"><span data-stu-id="c2744-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c2744-113">Administrador</span><span class="sxs-lookup"><span data-stu-id="c2744-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="c2744-114"><a href="lync-server-2013-planning-for-mobility.md">Planear la movilidad en Lync Server 2013</a> en la documentación de planeación del servidor.</span><span class="sxs-lookup"><span data-stu-id="c2744-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="c2744-115"><a href="lync-server-2013-deploying-mobility.md">Implementación de movilidad en Lync Server 2013</a> en la documentación de implementación del servidor.</span><span class="sxs-lookup"><span data-stu-id="c2744-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="c2744-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisitos de infraestructura de certificados para Lync Server 2013</a> en la documentación de planeación del servidor.</span><span class="sxs-lookup"><span data-stu-id="c2744-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2744-117">Instale la aplicación de Lync en un dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c2744-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c2744-118">Instale los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="c2744-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="c2744-119">Instale desde el Marketplace específico para el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="c2744-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c2744-120">Administrador</span><span class="sxs-lookup"><span data-stu-id="c2744-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="c2744-121">Instrucciones de instalación específicas del dispositivo móvil en la <a href="lync-server-2013-deploying-mobile-clients.md">implementación de clientes móviles en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c2744-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2744-122">Configure el cliente.</span><span class="sxs-lookup"><span data-stu-id="c2744-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2744-123">Configure las opciones de inicio de sesión y la información del servidor.</span><span class="sxs-lookup"><span data-stu-id="c2744-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2744-124">Administrador</span><span class="sxs-lookup"><span data-stu-id="c2744-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="c2744-125"><a href="lync-server-2013-deploying-mobile-clients.md">Implementación de clientes móviles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2744-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2744-126">Probar escenarios de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="c2744-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c2744-127">Pruebe la mensajería instantánea (mi) y la presencia.</span><span class="sxs-lookup"><span data-stu-id="c2744-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="c2744-128">Probar las conferencias de acceso telefónico saliente.</span><span class="sxs-lookup"><span data-stu-id="c2744-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="c2744-129">Buscar un contacto en el directorio corporativo.</span><span class="sxs-lookup"><span data-stu-id="c2744-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="c2744-130">Probar las notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="c2744-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c2744-131">Administrador</span><span class="sxs-lookup"><span data-stu-id="c2744-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="c2744-132">Instrucciones de comprobación específicas del dispositivo móvil en la <a href="lync-server-2013-deploying-mobile-clients.md">implementación de clientes móviles en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c2744-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2744-133">Instale la aplicación de Lync en teléfonos móviles.</span><span class="sxs-lookup"><span data-stu-id="c2744-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c2744-134">Instale los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="c2744-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="c2744-135">Instale desde el Marketplace específico para el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="c2744-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c2744-136">Usuario</span><span class="sxs-lookup"><span data-stu-id="c2744-136">User</span></span></p></td>
<td><p><span data-ttu-id="c2744-137">Instrucciones de instalación específicas del dispositivo móvil en la <a href="lync-server-2013-deploying-mobile-clients.md">implementación de clientes móviles en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c2744-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

