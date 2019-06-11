---
title: 'Lync Server 2013: Lista de comprobación para la implementación del control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="af9d9-102">Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af9d9-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af9d9-103">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="af9d9-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="af9d9-104">Para planear de forma eficaz el control de admisión de llamadas (CAC), debe tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af9d9-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="af9d9-105">Requisitos previos para implementar CAC.</span><span class="sxs-lookup"><span data-stu-id="af9d9-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="af9d9-106">Información necesaria para el CAC y las decisiones de configuración que debe realizar antes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="af9d9-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="af9d9-107">Requisitos previos de implementación para el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="af9d9-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="af9d9-108">Antes de implementar el control de admisión de llamadas, debe haber implementado los servidores internos de Lync Server 2013, incluido un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="af9d9-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="af9d9-109">Requisitos de información para el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="af9d9-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="af9d9-110">En la tabla siguiente se resume la información necesaria para implementar el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="af9d9-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="af9d9-111">Requisitos de información para la implementación de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="af9d9-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af9d9-112">Información</span><span class="sxs-lookup"><span data-stu-id="af9d9-112">Information</span></span></th>
<th><span data-ttu-id="af9d9-113">Resumen de la información necesaria</span><span class="sxs-lookup"><span data-stu-id="af9d9-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="af9d9-114">Documentación</span><span class="sxs-lookup"><span data-stu-id="af9d9-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af9d9-115">Capacidades de Lync Server requeridas por su organización</span><span class="sxs-lookup"><span data-stu-id="af9d9-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af9d9-116">Capacidades que la organización debe admitir</span><span class="sxs-lookup"><span data-stu-id="af9d9-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="af9d9-117">Capacidades que se deben habilitar para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="af9d9-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="af9d9-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="af9d9-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af9d9-119">Topologías y componentes que se van a implementar</span><span class="sxs-lookup"><span data-stu-id="af9d9-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af9d9-120">Los componentes relacionados con CAC se instalan automáticamente como parte de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af9d9-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="af9d9-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="af9d9-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af9d9-122">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="af9d9-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af9d9-123">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="af9d9-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="af9d9-124">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="af9d9-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="af9d9-125">Requisitos de collocation</span><span class="sxs-lookup"><span data-stu-id="af9d9-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="af9d9-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="af9d9-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af9d9-127">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="af9d9-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af9d9-128">No se necesitan requisitos de infraestructura específicos para CAC</span><span class="sxs-lookup"><span data-stu-id="af9d9-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="af9d9-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisitos de infraestructura para el control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="af9d9-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af9d9-130">Requisitos de interfaz de red</span><span class="sxs-lookup"><span data-stu-id="af9d9-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af9d9-131">Información de la interfaz interna y externa</span><span class="sxs-lookup"><span data-stu-id="af9d9-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="af9d9-132">Información de enrutamiento (incluida información sobre el blog de <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>NextHop en, canal de respuesta para clientes del equipo de Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="af9d9-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="af9d9-133"><a href="lync-server-2013-deploying-external-user-access.md">Implementar el acceso de usuarios externos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="af9d9-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af9d9-134">Estrategia de implementación</span><span class="sxs-lookup"><span data-stu-id="af9d9-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af9d9-135">Secuencia de implementación</span><span class="sxs-lookup"><span data-stu-id="af9d9-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="af9d9-136">Grupo de trabajo o dominio</span><span class="sxs-lookup"><span data-stu-id="af9d9-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="af9d9-137">Seguridad</span><span class="sxs-lookup"><span data-stu-id="af9d9-137">Security</span></span></p></li>
<li><p><span data-ttu-id="af9d9-138">Supervisión y auditoría</span><span class="sxs-lookup"><span data-stu-id="af9d9-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="af9d9-139">Consideraciones de hardware</span><span class="sxs-lookup"><span data-stu-id="af9d9-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="af9d9-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Procedimientos recomendados para el servicio de control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="af9d9-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af9d9-141">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="af9d9-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af9d9-142">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="af9d9-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="af9d9-143">Requisitos de información</span><span class="sxs-lookup"><span data-stu-id="af9d9-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="af9d9-144">Procesos y procedimientos</span><span class="sxs-lookup"><span data-stu-id="af9d9-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="af9d9-145"><a href="lync-server-2013-configure-call-admission-control.md">Configurar el control de admisión de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="af9d9-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

