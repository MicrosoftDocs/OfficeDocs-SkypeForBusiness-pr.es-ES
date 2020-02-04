---
title: 'Lync Server 2013: Administrar directivas de correo de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434cc1eb721635f4a56be33f48802da3bc6db0e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="f410d-102">Administrar directivas de correo de voz hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f410d-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f410d-103">_**Última modificación del tema:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="f410d-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="f410d-104">Una *Directiva de correo de voz hospedada* proporciona información a la aplicación de enrutamiento de 2013 ExUM de Lync Server acerca de dónde enrutar las llamadas de los usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="f410d-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f410d-105">Por lo general, solo se necesita una directiva de correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="f410d-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="f410d-106">En muchos casos, puede modificar la directiva global para satisfacer todas sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="f410d-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="f410d-107">Si crea una directiva con el ámbito del sitio, se asignará automáticamente a todos los usuarios alojados en el sitio especificado.</span><span class="sxs-lookup"><span data-stu-id="f410d-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="f410d-108">Si crea una directiva con ámbito por usuario, debe asignarla explícitamente a los usuarios, grupos y objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="f410d-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="f410d-109">Es posible implementar varias directivas de correo de voz hospedado, pero, en ese caso, las directivas deben asignarse para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="f410d-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="f410d-110">Para obtener más información sobre cómo planear directivas de correo de voz hospedado, consulte [directivas de correo de voz hospedado en Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="f410d-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f410d-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f410d-111">In This Section</span></span>

  - [<span data-ttu-id="f410d-112">Modificar la Directiva de correo de voz hospedado global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f410d-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="f410d-113">Crear una directiva de correo de voz hospedado en el nivel de sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f410d-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="f410d-114">Crear una directiva de correo de voz hospedada por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f410d-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="f410d-115">Asignar una directiva de correo de voz hospedado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f410d-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

