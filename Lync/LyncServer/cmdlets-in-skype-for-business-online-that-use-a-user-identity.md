---
title: Cmdlets de Skype empresarial online que usan una identidad de usuario
description: Cmdlets de Skype empresarial online que usan una identidad de usuario.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545656"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="ccac1-103">Cmdlets de Skype empresarial online que usan una identidad de usuario</span><span class="sxs-lookup"><span data-stu-id="ccac1-103">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="ccac1-104">En Skype empresarial online, hay varias formas de hacer referencia a una identidad de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="ccac1-104">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="ccac1-105">Use el nombre para mostrar de los servicios de dominio de Active Directory del usuario.</span><span class="sxs-lookup"><span data-stu-id="ccac1-105">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="ccac1-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ccac1-106">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="ccac1-107">Use la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="ccac1-107">Use the user’s SIP address.</span></span> <span data-ttu-id="ccac1-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ccac1-108">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ccac1-109">Usar el UPN del usuario.</span><span class="sxs-lookup"><span data-stu-id="ccac1-109">Use the user’s UPN.</span></span> <span data-ttu-id="ccac1-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ccac1-110">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="ccac1-111">Use el nombre distintivo de los servicios de dominio de Active Directory del usuario.</span><span class="sxs-lookup"><span data-stu-id="ccac1-111">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="ccac1-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ccac1-112">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="ccac1-113">Los siguientes cmdlets aceptan una identidad de usuario:</span><span class="sxs-lookup"><span data-stu-id="ccac1-113">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="ccac1-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-121">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-121">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ccac1-125">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-125">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="ccac1-126">Tenga en cuenta que no es necesario especificar una identidad de usuario al llamar a uno de los cmdlets **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="ccac1-126">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="ccac1-127">En este caso, los cmdlets devuelven todas las instancias del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="ccac1-127">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="ccac1-128">Por ejemplo, este comando devuelve información sobre todos los usuarios que se han habilitado para Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="ccac1-128">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="ccac1-129">El parámetro Identity solo es necesario si desea devolver información de un usuario específico:</span><span class="sxs-lookup"><span data-stu-id="ccac1-129">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="ccac1-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ccac1-130">See Also</span></span>


[<span data-ttu-id="ccac1-131">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="ccac1-131">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="ccac1-132">[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ccac1-132">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

