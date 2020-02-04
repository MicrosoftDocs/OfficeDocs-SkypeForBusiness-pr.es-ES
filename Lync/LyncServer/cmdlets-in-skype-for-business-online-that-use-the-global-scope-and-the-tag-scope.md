---
title: Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de la etiqueta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04eb5f71a0092452eb8b24fa9acf53d46fb3bcd5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728100"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="d5150-102">Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="d5150-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="d5150-103">En Skype empresarial online, las directivas se pueden configurar en el *ámbito global* o en el *ámbito* de la etiqueta (o *por ámbito de usuario*).</span><span class="sxs-lookup"><span data-stu-id="d5150-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="d5150-104">Al usar los cmdlets **Get-CS** , no tiene que especificar un ámbito o una identidad.</span><span class="sxs-lookup"><span data-stu-id="d5150-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="d5150-105">Si llama a uno de estos cmdlets sin parámetros, se devolverán todos los elementos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="d5150-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="d5150-106">Por ejemplo, este comando devuelve información acerca de todas las directivas de acceso externas:</span><span class="sxs-lookup"><span data-stu-id="d5150-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="d5150-107">Si desea limitar los datos devueltos, solo tiene que incluir el parámetro Identity o el parámetro filter.</span><span class="sxs-lookup"><span data-stu-id="d5150-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="d5150-108">Por ejemplo, para devolver solo la directiva global, use este comando:</span><span class="sxs-lookup"><span data-stu-id="d5150-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="d5150-109">Para devolver una directiva por usuario que tenga la identidad "RedmondAccessPolicy", use este comando:</span><span class="sxs-lookup"><span data-stu-id="d5150-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="d5150-110">Cuando se hace referencia a una directiva por usuario, el <STRONG>prefijo</STRONG> de etiqueta es opcional.</span><span class="sxs-lookup"><span data-stu-id="d5150-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="d5150-111">Esta sintaxis, que incluye el prefijo, también es válida:</span><span class="sxs-lookup"><span data-stu-id="d5150-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="d5150-112">Get-CsExternalAccessPolicy – Identity "etiqueta: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="d5150-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="d5150-113">Para devolver todas las directivas excepto las directivas globales (es decir, todas las directivas por usuario), use este comando:</span><span class="sxs-lookup"><span data-stu-id="d5150-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="d5150-114">Los siguientes cmdlets funcionan contra el ámbito global y el ámbito por usuario (etiqueta):</span><span class="sxs-lookup"><span data-stu-id="d5150-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="d5150-115">[Get-ClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d5150-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d5150-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d5150-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d5150-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d5150-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d5150-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="d5150-122">A pesar del nombre, los planes de marcado son, en términos funcionales, directivas.</span><span class="sxs-lookup"><span data-stu-id="d5150-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="d5150-123">El <EM>plan de marcado</EM> de términos se usa en lugar de, por ejemplo, la Directiva de marcado, a fin de preservar la terminología que se usa con versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5150-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="d5150-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5150-124">See Also</span></span>


[<span data-ttu-id="d5150-125">Identidades, ámbitos y espacios empresariales en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="d5150-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="d5150-126">[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d5150-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

