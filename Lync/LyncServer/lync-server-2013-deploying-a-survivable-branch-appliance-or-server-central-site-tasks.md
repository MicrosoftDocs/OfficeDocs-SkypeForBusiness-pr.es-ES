---
title: Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="5842c-102">Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia - Tareas de sitio central con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5842c-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5842c-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5842c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5842c-104">Complete las tareas de esta sección en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="5842c-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="5842c-105">Si va a implementar un servidor de sucursal con la supervivencia, omita la primera tarea.</span><span class="sxs-lookup"><span data-stu-id="5842c-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5842c-106">Antes de realizar las tareas de esta sección, deben cumplirse las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5842c-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="5842c-107">Lync Server debe estar configurado en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="5842c-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="5842c-108">Un técnico de instalación del sitio de la sucursal debe agregarse al grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="5842c-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="5842c-109">Además, le recomendamos que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5842c-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="5842c-110">Implemente un servidor DHCP en cada sitio de sucursal para que los clientes puedan obtener direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="5842c-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="5842c-111">Como alternativa a la implementación de un servidor DHCP en cada sitio de sucursal, habilite el servicio DHCP de Lync Server en el equipo de la sucursal o el servidor de sucursal con la configuración de Lync Server Management, cmdlet <STRONG>-CsRegistrarConfiguration – EnableDHCPServer $true </STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5842c-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="5842c-112">Para obtener más información, consulte la sección "requisitos de hardware y software" de <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resistencia de sitios de sucursales para Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="5842c-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5842c-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5842c-113">In This Section</span></span>

  - [<span data-ttu-id="5842c-114">Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5842c-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="5842c-115">Agregar sitios de sucursal a la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5842c-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="5842c-116">Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5842c-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

