---
title: Introducción
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f217ec7d39134dcb8d6000de33b3d0c17aeb033d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527157"
---
# <a name="introduction"></a><span data-ttu-id="ad265-102">Introducción</span><span class="sxs-lookup"><span data-stu-id="ad265-102">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad265-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="ad265-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="ad265-104">La herramienta stress and performance de Lync Server 2013 (denominada LyncPerfTool) puede simular la carga de usuarios de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="ad265-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad265-105">Mensajería instantánea (MI) y presencia</span><span class="sxs-lookup"><span data-stu-id="ad265-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="ad265-106">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="ad265-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad265-107">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ad265-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="ad265-108">Voz sobre IP (VoIP), incluida la simulación de red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="ad265-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad265-109">Conferencia de cliente de Web Access</span><span class="sxs-lookup"><span data-stu-id="ad265-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="ad265-110">Operador 2013 de Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="ad265-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad265-111">Grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ad265-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="ad265-112">Expansión de la lista de distribución</span><span class="sxs-lookup"><span data-stu-id="ad265-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad265-113">Consulta de la libreta de direcciones y de descarga de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="ad265-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="ad265-114">Llamadas mejoradas 9-1-1 (E9-1-1) y Perfil de ubicación (plan de marcado)</span><span class="sxs-lookup"><span data-stu-id="ad265-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad265-115">Vídeo</span><span class="sxs-lookup"><span data-stu-id="ad265-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="ad265-116">Ver varias secuencias desde una conferencia</span><span class="sxs-lookup"><span data-stu-id="ad265-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ad265-117">La herramienta de esfuerzo y rendimiento de Lync Server 2013 admite la generación de carga entre grupos de servidores y la Federación solo a través de la configuración avanzada.</span><span class="sxs-lookup"><span data-stu-id="ad265-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="ad265-118">La herramienta tampoco simula la carga de usuarios para los siguientes clientes:</span><span class="sxs-lookup"><span data-stu-id="ad265-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="ad265-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="ad265-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="ad265-120">Chat persistente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ad265-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="ad265-121">Como resultado, la herramienta stress and performance de Lync Server 2013 no permitirá probar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="ad265-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="ad265-122">Chat persistente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ad265-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="ad265-123">Escenarios de integración de Exchange</span><span class="sxs-lookup"><span data-stu-id="ad265-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="ad265-124">Aplicaciones y archivos incluidos con la herramienta de esfuerzo y rendimiento de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad265-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="ad265-125">Las siguientes aplicaciones se incluyen en la herramienta de esfuerzo y rendimiento de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ad265-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad265-126">Herramienta</span><span class="sxs-lookup"><span data-stu-id="ad265-126">Tool</span></span></th>
<th><span data-ttu-id="ad265-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad265-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad265-128">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="ad265-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="ad265-129">La herramienta de aprovisionamiento de usuarios de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad265-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="ad265-130">Esta herramienta se usa para crear usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="ad265-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad265-131">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="ad265-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="ad265-132">Herramienta de configuración de carga de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad265-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="ad265-133">Esta herramienta se usa para configurar las características de la carga de usuarios que se van a simular.</span><span class="sxs-lookup"><span data-stu-id="ad265-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad265-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="ad265-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="ad265-135">La herramienta de esfuerzo y rendimiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad265-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="ad265-136">LyncPerfTool es la herramienta que simula la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ad265-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad265-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="ad265-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="ad265-138">El valor predeterminado. TMX es necesario para usar la herramienta de registro de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad265-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad265-139">Scripts de aprovisionamiento de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad265-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="ad265-140">Estos ejemplos se usan para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="ad265-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

