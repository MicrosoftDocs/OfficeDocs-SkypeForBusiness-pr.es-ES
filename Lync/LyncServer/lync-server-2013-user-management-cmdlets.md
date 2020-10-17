---
title: 'Lync Server 2013: cmdlets de administración de usuarios'
description: 'Lync Server 2013: cmdlets de administración de usuarios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94f2b48017fd29fa7a5a814da8a3c80d8f57968
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569786"
---
# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="bacbd-103">Cmdlets de administración de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bacbd-103">User management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bacbd-104">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="bacbd-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="bacbd-105">Los cmdlets de administración de usuarios incluidos en Microsoft Lync Server 2013 permiten habilitar, deshabilitar y modificar las cuentas de usuario de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bacbd-105">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="bacbd-106">Cmdlets de administración de usuarios</span><span class="sxs-lookup"><span data-stu-id="bacbd-106">User Management Cmdlets</span></span>

<span data-ttu-id="bacbd-107">La mayoría de las tareas de administración que se aplican a usuarios y cuentas de usuario se pueden realizar desde el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bacbd-107">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="bacbd-108">Las excepciones más importantes son los cmdlets que se ocupan de los proveedores de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="bacbd-108">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="bacbd-109">Las tareas de administración de usuarios se pueden realizar mediante el uso de cmdlets desde el shell de administración de Lync Server o desde una secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="bacbd-109">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="bacbd-110">El uso de un script permite automatizar determinadas tareas.</span><span class="sxs-lookup"><span data-stu-id="bacbd-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="bacbd-111">A continuación se presenta una lista de cmdlets directamente relacionados con la administración de usuarios y cuentas de usuario:</span><span class="sxs-lookup"><span data-stu-id="bacbd-111">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="bacbd-112">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="bacbd-112">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="bacbd-113">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="bacbd-113">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="bacbd-114">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="bacbd-114">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="bacbd-115">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="bacbd-115">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="bacbd-116">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="bacbd-116">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="bacbd-117">Debug-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="bacbd-117">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="bacbd-118">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="bacbd-118">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="bacbd-119">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="bacbd-119">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="bacbd-120">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="bacbd-120">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="bacbd-121">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="bacbd-121">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="bacbd-122">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="bacbd-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="bacbd-123">Set-CsUser</span><span class="sxs-lookup"><span data-stu-id="bacbd-123">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="bacbd-124">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="bacbd-124">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="bacbd-125">Remove-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="bacbd-125">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="bacbd-126">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="bacbd-126">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="bacbd-127">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="bacbd-127">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="bacbd-128">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="bacbd-128">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="bacbd-129">Get-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="bacbd-129">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="bacbd-130">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="bacbd-130">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="bacbd-131">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="bacbd-131">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="bacbd-132">Remove-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="bacbd-132">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="bacbd-133">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="bacbd-133">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bacbd-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bacbd-134">See Also</span></span>


[<span data-ttu-id="bacbd-135">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="bacbd-135">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

