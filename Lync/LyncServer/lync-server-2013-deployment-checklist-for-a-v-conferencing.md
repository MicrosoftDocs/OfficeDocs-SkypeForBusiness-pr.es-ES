---
title: Lista de comprobación de implementación de Lync Server 2013 para conferencias A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="38288-102">Lista de comprobación de implementación para conferencias A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38288-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38288-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="38288-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="38288-104">Al igual que con la implementación de otros componentes de Lync Server 2013, la implementación de conferencias A/V requiere que use el generador de topología para crear y publicar una topología que incorpore conferencias.</span><span class="sxs-lookup"><span data-stu-id="38288-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="38288-105">Secuencia de implementación</span><span class="sxs-lookup"><span data-stu-id="38288-105">Deployment Sequence</span></span>

<span data-ttu-id="38288-106">Puede implementar conferencias al mismo tiempo que implementa su Topología inicial o después de haber implementado al menos un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="38288-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="38288-107">Proceso de implementación de conferencia</span><span class="sxs-lookup"><span data-stu-id="38288-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="38288-108">En la tabla siguiente se proporciona una descripción general de los pasos necesarios para implementar las conferencias en una topología existente.</span><span class="sxs-lookup"><span data-stu-id="38288-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38288-109">Fase</span><span class="sxs-lookup"><span data-stu-id="38288-109">Phase</span></span></th>
<th><span data-ttu-id="38288-110">Pasos</span><span class="sxs-lookup"><span data-stu-id="38288-110">Steps</span></span></th>
<th><span data-ttu-id="38288-111">Roles y pertenencias a grupos</span><span class="sxs-lookup"><span data-stu-id="38288-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="38288-112">Documentación</span><span class="sxs-lookup"><span data-stu-id="38288-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38288-113"><strong>Instalar los requisitos previos de hardware y software</strong></span><span class="sxs-lookup"><span data-stu-id="38288-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="38288-114">La Conferencia se ejecuta en servidores front-end de un grupo de servidores front-end y servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="38288-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="38288-115">No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.</span><span class="sxs-lookup"><span data-stu-id="38288-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="38288-116">Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y el procesamiento de presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="38288-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="38288-117">Para obtener más información sobre cómo instalar y configurar el servidor de Office Web Apps, vea <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurar la integración con Office Web Apps Server y Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38288-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="38288-118">Usuario de dominio miembro del grupo Administradores locales</span><span class="sxs-lookup"><span data-stu-id="38288-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="38288-119"><a href="lync-server-2013-supported-hardware.md">Hardware compatible con Lync Server 2013</a> en la documentación de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="38288-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="38288-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Compatibilidad con el software de servidor y la infraestructura en Lync Server 2013</a> en la documentación de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="38288-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="38288-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a> en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="38288-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="38288-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para archivar en Lync Server 2013</a> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="38288-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38288-123"><strong>Crear la topología interna adecuada para admitir la conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="38288-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="38288-124">Ejecute el generador de topología para agregar conferencias a la topología y, a continuación, publique la topología.</span><span class="sxs-lookup"><span data-stu-id="38288-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="38288-125">Para definir una topología, una cuenta que sea miembro del grupo Usuarios locales</span><span class="sxs-lookup"><span data-stu-id="38288-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="38288-126">Para publicar la topología, una cuenta que sea miembro del grupo administradores del dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos para el almacén de archivos de Lync Server 2013 (para que topología pueda configurar las DACL obligatorias)</span><span class="sxs-lookup"><span data-stu-id="38288-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="38288-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Defina y configure una topología en el generador de topologías para Lync Server 2013</a> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="38288-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38288-128"><strong>Configurar directivas de conferencia y soporte técnico</strong></span><span class="sxs-lookup"><span data-stu-id="38288-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="38288-129">Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar las opciones de conferencia.</span><span class="sxs-lookup"><span data-stu-id="38288-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="38288-130">Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asignar usuarios al rol [] o CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="38288-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="38288-131"><a href="lync-server-2013-conferencing-policies.md">Directivas de conferencia en Lync Server 2013</a> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="38288-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38288-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="38288-132">See Also</span></span>


[<span data-ttu-id="38288-133">Información general sobre conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38288-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="38288-134">Definición de requisitos para conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38288-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

