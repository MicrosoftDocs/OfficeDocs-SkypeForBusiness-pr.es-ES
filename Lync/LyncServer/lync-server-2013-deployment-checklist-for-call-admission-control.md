---
title: 'Lync Server 2013: lista de comprobación para la implementación del control de admisión de llamadas'
description: 'Lync Server 2013: lista de comprobación para la implementación del control de admisión de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557696"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="f6296-103">Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6296-103">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6296-104">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="f6296-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="f6296-105">Para planear de forma eficaz el servicio de control de admisión de llamadas (CAC), debe tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6296-105">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="f6296-106">Requisitos previos para implementar el CAC.</span><span class="sxs-lookup"><span data-stu-id="f6296-106">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="f6296-107">Información necesaria para el CAC y las decisiones de configuración que debe tomar antes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f6296-107">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="f6296-108">Requisitos previos del control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="f6296-108">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="f6296-109">Antes de implementar el control de admisión de llamadas, debe haber implementado ya los servidores internos de Lync Server 2013, incluido un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f6296-109">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="f6296-110">Requisitos de información para el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="f6296-110">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="f6296-111">La siguiente tabla resume la información requerida para implementar el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f6296-111">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="f6296-112">Requisitos de información para implementar el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="f6296-112">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6296-113">Información</span><span class="sxs-lookup"><span data-stu-id="f6296-113">Information</span></span></th>
<th><span data-ttu-id="f6296-114">Resumen de la información necesaria</span><span class="sxs-lookup"><span data-stu-id="f6296-114">Summary of Information Required</span></span></th>
<th><span data-ttu-id="f6296-115">Documentación</span><span class="sxs-lookup"><span data-stu-id="f6296-115">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6296-116">Capacidades de Lync Server que necesita su organización</span><span class="sxs-lookup"><span data-stu-id="f6296-116">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6296-117">Funcionalidades que admitirá su organización</span><span class="sxs-lookup"><span data-stu-id="f6296-117">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="f6296-118">Funcionalidades que se habilitarán para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="f6296-118">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6296-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos para el control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6296-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6296-120">Topologías y componentes que se implementarán</span><span class="sxs-lookup"><span data-stu-id="f6296-120">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6296-121">Los componentes relacionados con CAC se instalan automáticamente como parte de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6296-121">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6296-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos para el control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6296-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6296-123">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="f6296-123">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6296-124">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="f6296-124">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="f6296-125">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="f6296-125">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="f6296-126">Requisitos de combinación</span><span class="sxs-lookup"><span data-stu-id="f6296-126">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6296-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determinación de los requisitos del sistema para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6296-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6296-128">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="f6296-128">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6296-129">No se necesitan requisitos específicos de infraestructura para el CAC</span><span class="sxs-lookup"><span data-stu-id="f6296-129">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6296-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisitos de infraestructura para el control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6296-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6296-131">Requisitos de la interfaz de red</span><span class="sxs-lookup"><span data-stu-id="f6296-131">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6296-132">Información de la interfaz interna y externa</span><span class="sxs-lookup"><span data-stu-id="f6296-132">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="f6296-133">Información de enrutamiento (incluida información sobre el blog de NextHop, en el <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> canal de respuesta del cliente del equipo de Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="f6296-133">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6296-134"><a href="lync-server-2013-deploying-external-user-access.md">Implementar el acceso de usuarios externos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6296-134"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6296-135">Estrategia de implementación</span><span class="sxs-lookup"><span data-stu-id="f6296-135">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6296-136">Secuencia de implementación</span><span class="sxs-lookup"><span data-stu-id="f6296-136">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="f6296-137">Grupo de trabajo o dominio</span><span class="sxs-lookup"><span data-stu-id="f6296-137">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="f6296-138">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f6296-138">Security</span></span></p></li>
<li><p><span data-ttu-id="f6296-139">Supervisión y auditoría</span><span class="sxs-lookup"><span data-stu-id="f6296-139">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="f6296-140">Consideraciones de hardware</span><span class="sxs-lookup"><span data-stu-id="f6296-140">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6296-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedimientos recomendados para el control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6296-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6296-142">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="f6296-142">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6296-143">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f6296-143">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="f6296-144">Requisitos de información</span><span class="sxs-lookup"><span data-stu-id="f6296-144">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="f6296-145">Proceso y procedimientos</span><span class="sxs-lookup"><span data-stu-id="f6296-145">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6296-146"><a href="lync-server-2013-configure-call-admission-control.md">Configurar el control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6296-146"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

