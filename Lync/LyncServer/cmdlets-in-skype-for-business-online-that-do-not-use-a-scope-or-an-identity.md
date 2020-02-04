---
title: Cmdlets de Skype empresarial online que no usan un ámbito o una identidad
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3dfc2ee8cd812b597f363934475d1996f2e42a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727600"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="a54d4-102">Cmdlets de Skype empresarial online que no usan un ámbito o una identidad</span><span class="sxs-lookup"><span data-stu-id="a54d4-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="a54d4-103">Los cmdlets que se usan al modificar las listas permitidas y las listas bloqueadas (listas que determinan de qué organizaciones externas a las que los usuarios pueden comunicarse) no usan un ámbito ni una identidad.</span><span class="sxs-lookup"><span data-stu-id="a54d4-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="a54d4-104">De hecho, el cmdlet **New-CsEdgeAllowAllKnownDomains** no tiene ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="a54d4-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="a54d4-105">Los cmdlets que no usan un ámbito o una identidad son:</span><span class="sxs-lookup"><span data-stu-id="a54d4-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="a54d4-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a54d4-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a54d4-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a54d4-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a54d4-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a54d4-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="a54d4-109">Tenga en cuenta que, con el cmdlet **New-CsEdgeAllowList** y el cmdlet **New-CsEdgeDomainPattern** , debe incluir el parámetro domain.</span><span class="sxs-lookup"><span data-stu-id="a54d4-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="a54d4-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a54d4-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="a54d4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a54d4-111">See Also</span></span>


[<span data-ttu-id="a54d4-112">Identidades, ámbitos y espacios empresariales en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="a54d4-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="a54d4-113">[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a54d4-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

