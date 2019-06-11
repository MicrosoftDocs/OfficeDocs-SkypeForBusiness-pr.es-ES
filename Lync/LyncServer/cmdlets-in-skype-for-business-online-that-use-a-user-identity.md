---
title: Cmdlets de Skype empresarial online que usan una identidad de usuario
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e0086f4b04dd199a285820db811a57899cdc0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842095"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="9d952-102">Cmdlets de Skype empresarial online que usan una identidad de usuario</span><span class="sxs-lookup"><span data-stu-id="9d952-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="9d952-103">En Skype empresarial online, hay varias maneras de hacer referencia a una identidad de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="9d952-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="9d952-104">Use el nombre para mostrar de los servicios de dominio de Active Directory del usuario.</span><span class="sxs-lookup"><span data-stu-id="9d952-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="9d952-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d952-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="9d952-106">Use la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="9d952-106">Use the user’s SIP address.</span></span> <span data-ttu-id="9d952-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d952-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9d952-108">Use el UPN del usuario.</span><span class="sxs-lookup"><span data-stu-id="9d952-108">Use the user’s UPN.</span></span> <span data-ttu-id="9d952-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d952-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="9d952-110">Use el nombre completo de los servicios de dominio de Active Directory del usuario.</span><span class="sxs-lookup"><span data-stu-id="9d952-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="9d952-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d952-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="9d952-112">Los siguientes cmdlets aceptan una identidad de usuario:</span><span class="sxs-lookup"><span data-stu-id="9d952-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="9d952-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9d952-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="9d952-125">Tenga en cuenta que no es necesario especificar una identidad de usuario al llamar a uno de los cmdlets **Get-CS** .</span><span class="sxs-lookup"><span data-stu-id="9d952-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="9d952-126">En este caso, los cmdlets devuelven todas las instancias del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="9d952-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="9d952-127">Por ejemplo, este comando devuelve información acerca de todos los usuarios que se han habilitado para Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="9d952-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="9d952-128">El parámetro Identity solo es necesario si desea devolver información para un usuario específico:</span><span class="sxs-lookup"><span data-stu-id="9d952-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="9d952-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d952-129">See Also</span></span>


[<span data-ttu-id="9d952-130">Identidades, ámbitos y espacios empresariales en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="9d952-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="9d952-131">[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9d952-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

