---
title: 'Lync Server 2013: lista de comprobación de implementación para supervisión'
description: 'Lync Server 2013: lista de comprobación para la supervisión de la implementación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d3293accf6e25c20ae8391f9107ae75fef338
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568335"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="413e2-103">Lista de comprobación de implementación para la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="413e2-103">Deployment checklist for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="413e2-104">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="413e2-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="413e2-105">Aunque la supervisión ya está instalada y activa en cada servidor front-end, existen varios pasos que debe realizar antes de poder recopilar datos de supervisión para Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="413e2-105">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="413e2-106">Estos pasos se describen en la siguiente lista de comprobación:</span><span class="sxs-lookup"><span data-stu-id="413e2-106">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="413e2-107">Fase</span><span class="sxs-lookup"><span data-stu-id="413e2-107">Phase</span></span></p></td>
<td><p><span data-ttu-id="413e2-108">Pasos</span><span class="sxs-lookup"><span data-stu-id="413e2-108">Steps</span></span></p></td>
<td><p><span data-ttu-id="413e2-109">Roles y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="413e2-109">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="413e2-110">Documentación</span><span class="sxs-lookup"><span data-stu-id="413e2-110">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="413e2-111"><strong>Instalar el hardware y el software necesario como requisito previo</strong></span><span class="sxs-lookup"><span data-stu-id="413e2-111"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="413e2-112">Instalar una versión compatible de Microsoft SQL Server en el PC que actuará como almacén de datos back-end para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="413e2-112">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="413e2-113">Usuario de dominio que también es miembro del grupo de administradores locales</span><span class="sxs-lookup"><span data-stu-id="413e2-113">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="413e2-114"><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la guía de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="413e2-114"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="413e2-115"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la guía de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="413e2-115"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="413e2-116"><strong>Crear la topología interna adecuada para admitir la supervisión</strong></span><span class="sxs-lookup"><span data-stu-id="413e2-116"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="413e2-117">Use el generador de topologías de Lync Server 2013 para agregar bases de datos de supervisión a la topología y, a continuación, publique la topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="413e2-117">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="413e2-118">Para definir una topología, un usuario que sea miembro del grupo de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="413e2-118">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="413e2-119">Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="413e2-119">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="413e2-120"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Asociar un almacén de supervisión a un grupo de servidores front-end en Lync Server 2013</a> en la guía de implementación</span><span class="sxs-lookup"><span data-stu-id="413e2-120"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="413e2-121"><strong>Habilitar la configuración de supervisión adecuada</strong></span><span class="sxs-lookup"><span data-stu-id="413e2-121"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="413e2-122">Habilitar el registro detallado de llamadas (CDR) y/o la supervisión de la calidad de la experiencia (QoE) en los ámbitos del sitio y/o global.</span><span class="sxs-lookup"><span data-stu-id="413e2-122">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="413e2-123">Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="413e2-123">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="413e2-124"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configurar el registro de detalles de llamadas y la configuración de la calidad de la experiencia en Lync Server 2013</a> en la guía de operaciones</span><span class="sxs-lookup"><span data-stu-id="413e2-124"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

