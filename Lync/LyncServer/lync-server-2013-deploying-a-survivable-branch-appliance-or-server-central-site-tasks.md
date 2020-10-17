---
title: Implementación de una aplicación de sucursal con funciones de supervivencia o tareas de sitio central de servidor
description: Implementación de una aplicación de sucursal con funciones de supervivencia o tareas de sitio central del servidor.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4460ea215d6fc80ee89f1ca9bc42f08ac5d14617
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558606"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="8acdf-103">Implementación de una aplicación o servidor de sucursal con funciones de supervivencia con las tareas de sitio central de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acdf-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8acdf-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8acdf-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8acdf-105">Complete las tareas de esta sección en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="8acdf-105">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="8acdf-106">Si está implementando un servidor de sucursal con funciones de supervivencia, omita la primera tarea.</span><span class="sxs-lookup"><span data-stu-id="8acdf-106">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8acdf-107">Antes de realizar las tareas de esta sección, deberán cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="8acdf-107">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="8acdf-108">Lync Server debe configurarse en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="8acdf-108">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="8acdf-109">Debe agregarse un técnico de instalación de la sucursal al grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="8acdf-109">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="8acdf-110">Además, se recomienda que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8acdf-110">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="8acdf-111">Implementar un servidor DHCP en cada una de las sucursales para permitir que los clientes obtengan direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="8acdf-111">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="8acdf-112">Como alternativa a la implementación de un servidor DHCP en cada sitio de sucursal, habilite el DHCP de Lync Server en la aplicación de sucursal con funciones de supervivencia o con el servidor de sucursal con funciones de supervivencia mediante el cmdlet <STRONG>set-CsRegistrarConfiguration – EnableDHCPServer $true de</STRONG>Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8acdf-112">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="8acdf-113">Para obtener más información, consulte la sección "requisitos de hardware y software" de <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resistencia de sitios de sucursal para Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="8acdf-113">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8acdf-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8acdf-114">In This Section</span></span>

  - [<span data-ttu-id="8acdf-115">Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acdf-115">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="8acdf-116">Agregar sitios de sucursal a la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acdf-116">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="8acdf-117">Definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acdf-117">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

