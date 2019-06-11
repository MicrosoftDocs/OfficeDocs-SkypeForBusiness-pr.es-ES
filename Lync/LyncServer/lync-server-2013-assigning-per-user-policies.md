---
title: 'Lync Server 2013: asignación de directivas por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9088326d5d7a11bd186a594327eb083df590849
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="cfb87-102">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfb87-103">_**Última modificación del tema:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="cfb87-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="cfb87-104">Puede asignar determinadas directivas a un usuario o a un grupo de usuarios para especificar valores particulares que se desvíen de la configuración definida en las directivas asignadas a otros usuarios, como directivas globales.</span><span class="sxs-lookup"><span data-stu-id="cfb87-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="cfb87-105">Estas directivas se denominan directivas por usuario.</span><span class="sxs-lookup"><span data-stu-id="cfb87-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cfb87-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cfb87-106">In This Section</span></span>

  - [<span data-ttu-id="cfb87-107">Asignar una directiva de conferencia por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="cfb87-108">Asignar una directiva de versión de cliente por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="cfb87-109">Asignar una directiva de PIN por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="cfb87-110">Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="cfb87-111">Asignar una directiva de archivado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="cfb87-112">Asignar una directiva de ubicación por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="cfb87-113">Asignar una directiva de movilidad por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="cfb87-114">Asignar una directiva de chat persistente por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="cfb87-115">Asignar una directiva de plan de marcado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="cfb87-116">Asignar una directiva de voz por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cfb87-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfb87-117">See Also</span></span>


[<span data-ttu-id="cfb87-118">Administración de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfb87-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

