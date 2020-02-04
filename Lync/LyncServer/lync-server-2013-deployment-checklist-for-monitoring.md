---
title: 'Lync Server 2013: Lista de comprobación para la supervisión'
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
ms.openlocfilehash: 71b7d69054df266139f3f13ca0ca53e1803f44b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="27c57-102">Lista de comprobación para la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27c57-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27c57-103">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="27c57-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="27c57-104">Aunque la supervisión ya está instalada y activa en cada servidor front-end, hay varios pasos que debe realizar antes de que pueda recopilar datos de supervisión para Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27c57-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="27c57-105">Estos pasos se describen en la siguiente lista de comprobación:</span><span class="sxs-lookup"><span data-stu-id="27c57-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27c57-106">Fase</span><span class="sxs-lookup"><span data-stu-id="27c57-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="27c57-107">Pasos</span><span class="sxs-lookup"><span data-stu-id="27c57-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="27c57-108">Rol y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="27c57-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="27c57-109">Documentación</span><span class="sxs-lookup"><span data-stu-id="27c57-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c57-110"><strong>Instalar los requisitos previos de hardware y software</strong></span><span class="sxs-lookup"><span data-stu-id="27c57-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="27c57-111">Instale una versión compatible de Microsoft SQL Server en el equipo que actuará como almacén de datos back-end para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="27c57-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="27c57-112">Usuario de dominio que también es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="27c57-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="27c57-113"><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la guía de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="27c57-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="27c57-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Compatibilidad con el software de servidor y la infraestructura en Lync Server 2013</a> en la guía de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="27c57-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27c57-115"><strong>Crear la topología interna adecuada para admitir la supervisión</strong></span><span class="sxs-lookup"><span data-stu-id="27c57-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="27c57-116">Use el generador de topología de Lync Server 2013 para agregar bases de datos de supervisión a la topología y, después, publique la topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="27c57-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="27c57-117">Para definir una topología, un usuario que sea miembro del grupo de usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="27c57-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="27c57-118">Para publicar la topología, un usuario que sea miembro del grupo de administradores del dominio y del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="27c57-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="27c57-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Asociar una tienda de supervisión con un grupo de servidores front-end en Lync Server 2013</a> en la guía de implementación</span><span class="sxs-lookup"><span data-stu-id="27c57-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27c57-120"><strong>Habilitar la configuración de supervisión adecuada</strong></span><span class="sxs-lookup"><span data-stu-id="27c57-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="27c57-121">Habilite la supervisión de la grabación de detalles de llamadas (CDR) o la calidad de la experiencia (QoE) en los ámbitos global y/o del sitio.</span><span class="sxs-lookup"><span data-stu-id="27c57-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="27c57-122">Un usuario que sea miembro del grupo RTCUniversalServerAdmins o que tiene asignado un rol RBAC que proporciona acceso a los cmdlets de CsCdrConfiguration y CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="27c57-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="27c57-123">Configuración de la <a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">grabación de detalles de llamadas y la configuración de la calidad de la experiencia en Lync Server 2013</a> en la guía de operaciones</span><span class="sxs-lookup"><span data-stu-id="27c57-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

