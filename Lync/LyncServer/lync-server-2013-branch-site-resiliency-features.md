---
title: 'Lync Server 2013: características de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5787f0fd07afcf0ca70a9c3b0f7c21e3525cfae7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="1d839-102">Características de resistencia de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d839-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d839-103">_**Última modificación del tema:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="1d839-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="1d839-104">Al proporcionar resistencia a las sucursales, si se produce un error en la conexión WAN de una sucursal a un sitio central o si no se puede alcanzar el sitio central, las siguientes características de voz deberían seguir disponibles:</span><span class="sxs-lookup"><span data-stu-id="1d839-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="1d839-105">Llamadas de red telefónica conmutada (RTC) entrantes y realizadas.</span><span class="sxs-lookup"><span data-stu-id="1d839-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="1d839-106">Llamadas de empresa entre usuarios del mismo sitio y entre dos sitios diferentes</span><span class="sxs-lookup"><span data-stu-id="1d839-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="1d839-107">Administración básica de llamadas, incluida la retención, recuperación y transferencia de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1d839-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="1d839-108">Mensajería instantánea entre dos participantes</span><span class="sxs-lookup"><span data-stu-id="1d839-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="1d839-109">Desvío de llamadas, llamadas simultáneas a extremos, delegación de llamadas y servicios de llamada de equipo, pero solo si el delegador y el delegado (por ejemplo, un encargado y su administrador) o todos los miembros del equipo están configurados en el mismo sitio</span><span class="sxs-lookup"><span data-stu-id="1d839-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="1d839-110">Registros de detalles de las llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="1d839-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="1d839-111">Conferencias de acceso telefónico local RTC con operador automático de conferencia</span><span class="sxs-lookup"><span data-stu-id="1d839-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="1d839-112">Capacidades de correo de voz, si configura la configuración de reenrutamiento del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="1d839-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="1d839-113">(Para obtener más información, consulte [requisitos de resistencia de sitios de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="1d839-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="1d839-114">Autorización y autenticación de usuarios</span><span class="sxs-lookup"><span data-stu-id="1d839-114">User authentication and authorization</span></span>

<span data-ttu-id="1d839-115">Las siguientes características solo estarán disponibles si la solución de resistencia es una implementación de Lync Server a escala completa en el sitio de sucursal:</span><span class="sxs-lookup"><span data-stu-id="1d839-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="1d839-116">Conferencia A/V, web y MI</span><span class="sxs-lookup"><span data-stu-id="1d839-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="1d839-117">Enrutamiento basado en presencia y No molestar (DND) (con el que se evita que las llamadas suenen en extensiones con DND activado)</span><span class="sxs-lookup"><span data-stu-id="1d839-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="1d839-118">Actualización de la configuración del desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="1d839-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="1d839-119">Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="1d839-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="1d839-120">Aprovisionamiento de nuevos teléfonos y clientes, pero solo si los servicios de dominio de Active Directory están presentes en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="1d839-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="1d839-121">9-1-1 mejorado (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="1d839-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="1d839-122">Si se ha implementado E9-1-1 y el tronco SIP en el sitio central no está disponible porque el vínculo WAN está inactivo, la aplicación de sucursal con funciones de supervivencia enrutará las llamadas de E9-1-1 a la puerta de enlace de sucursal local.</span><span class="sxs-lookup"><span data-stu-id="1d839-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="1d839-123">Para habilitar esta característica, las directivas de voz de los usuarios de las sucursales deben enrutar las llamadas a la puerta de enlace local en caso de error de WAN.</span><span class="sxs-lookup"><span data-stu-id="1d839-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d839-124">SBA (sucursal con funciones de supervivencia) no es compatible con XMPP.</span><span class="sxs-lookup"><span data-stu-id="1d839-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="1d839-125">Los usuarios hospedados en una configuración de SBA no podrán enviar mensajes instantáneos ni ver presencia con contactos XMPP.</span><span class="sxs-lookup"><span data-stu-id="1d839-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

