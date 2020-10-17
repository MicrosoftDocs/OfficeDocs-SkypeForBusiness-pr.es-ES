---
title: 'Lync Server 2013: implementación de una aplicación o un servidor de sucursal con funciones de supervivencia'
description: 'Lync Server 2013: implementación de una aplicación o un servidor de sucursal con funciones de supervivencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558596"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="07494-103">Implementación de una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07494-104">_**Última modificación del tema:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="07494-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="07494-105">Resistente Enterprise Voice hace referencia a la resistencia de los sitios de sucursal, es decir, a la capacidad de proporcionar un servicio de telefonía IP empresarial continuo a los usuarios de sitios de sucursal en el caso de que el vínculo al sitio central deje de estar disponible.</span><span class="sxs-lookup"><span data-stu-id="07494-105">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="07494-106">Para sitios de sucursal pequeños y medianos (sitios de sucursal con 25 a 1.000 usuarios), se recomienda implementar una aplicación de sucursal con funciones de supervivencia, que finalizará las llamadas de red telefónica conmutada (RTC) mediante la puerta de enlace RTC integrada o un tronco SIP a un proveedor de servicios telefónicos.</span><span class="sxs-lookup"><span data-stu-id="07494-106">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="07494-107">Una aplicación de sucursal con funciones de supervivencia es un dispositivo de terceros que incluye un servidor blade que ejecuta el sistema operativo Windows Server 2008 R2, el registrador de Lync Server 2013, el software de servidor de mediación y una puerta de enlace RTC, todo en un solo chasis de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07494-107">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="07494-108">Para los sitios de sucursal con 1.000 a 5.000 y ninguna WAN resistente, se recomienda conectar un servidor de sucursal con funciones de supervivencia a una puerta de enlace RTC o a un tronco SIP a un proveedor de servicios telefónicos.</span><span class="sxs-lookup"><span data-stu-id="07494-108">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="07494-109">Un servidor de sucursal con funciones de supervivencia es un equipo basado en Windows Server que tiene el registrador y el software de servidor de mediación instalado.</span><span class="sxs-lookup"><span data-stu-id="07494-109">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07494-110">Para los sitios de sucursal con más de 5.000 usuarios y administradores de Lync Server dedicados, se recomienda una implementación completa de Lync Server 2013, independiente de la del sitio central.</span><span class="sxs-lookup"><span data-stu-id="07494-110">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="07494-111">Para obtener más información sobre cómo elegir la mejor solución de resistencia para los sitios de sucursal de la organización, incluidos los requisitos previos y las consideraciones de planeación, consulte <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site Resiliency Requirements for Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="07494-111">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="07494-112">Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.</span><span class="sxs-lookup"><span data-stu-id="07494-112">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="07494-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="07494-113">In This Section</span></span>

  - [<span data-ttu-id="07494-114">Implementación de una aplicación o servidor de sucursal con funciones de supervivencia con las tareas de sitio central de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-114">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="07494-115">Implementar una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013: tarea de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="07494-115">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="07494-116">Configuración de usuarios para la resistencia de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-116">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="07494-117">Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-117">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="07494-118">Apéndices: servidores y aplicaciones de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-118">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07494-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07494-119">See Also</span></span>


[<span data-ttu-id="07494-120">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07494-120">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

