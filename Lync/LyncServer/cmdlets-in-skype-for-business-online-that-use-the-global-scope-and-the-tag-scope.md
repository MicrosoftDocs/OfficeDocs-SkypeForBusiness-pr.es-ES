---
title: Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta
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
ms.openlocfilehash: 998201bf7772003c83ae27d56b3a238f9f0ca055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001155"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="5a4cd-102">Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta</span><span class="sxs-lookup"><span data-stu-id="5a4cd-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="5a4cd-103">En Skype empresarial online, las directivas se pueden configurar en el *ámbito global* o en el *ámbito* de la etiqueta (o *por ámbito de usuario*).</span><span class="sxs-lookup"><span data-stu-id="5a4cd-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="5a4cd-104">Cuando se usan los cmdlets **Get-CS** , no es necesario especificar un ámbito o una identidad.</span><span class="sxs-lookup"><span data-stu-id="5a4cd-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="5a4cd-105">Si se llama a uno de estos cmdlets sin ningún parámetro, se devolverán todos los elementos relevantes.</span><span class="sxs-lookup"><span data-stu-id="5a4cd-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="5a4cd-106">Por ejemplo, este comando devuelve información sobre todas las directivas de acceso externo:</span><span class="sxs-lookup"><span data-stu-id="5a4cd-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="5a4cd-107">Si desea limitar los datos devueltos, solo tiene que incluir el parámetro Identity o el parámetro filter.</span><span class="sxs-lookup"><span data-stu-id="5a4cd-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="5a4cd-108">Por ejemplo, para devolver sólo la directiva global, use este comando:</span><span class="sxs-lookup"><span data-stu-id="5a4cd-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="5a4cd-109">Para devolver una directiva por usuario que tenga la identidad "RedmondAccessPolicy", use este comando:</span><span class="sxs-lookup"><span data-stu-id="5a4cd-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="5a4cd-110">Cuando se hace referencia a una directiva por usuario, el <STRONG>prefijo</STRONG> de etiqueta es opcional.</span><span class="sxs-lookup"><span data-stu-id="5a4cd-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="5a4cd-111">Esta sintaxis, que incluye el prefijo, también es válida:</span><span class="sxs-lookup"><span data-stu-id="5a4cd-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="5a4cd-112">Get-CsExternalAccessPolicy – Identity "etiqueta: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="5a4cd-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="5a4cd-113">Para devolver todas las directivas excepto las directivas globales (es decir, todas las directivas por usuario), use este comando:</span><span class="sxs-lookup"><span data-stu-id="5a4cd-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="5a4cd-114">Los siguientes cmdlets operan en el ámbito global y en el ámbito por usuario (etiqueta):</span><span class="sxs-lookup"><span data-stu-id="5a4cd-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="5a4cd-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a4cd-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a4cd-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a4cd-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a4cd-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a4cd-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5a4cd-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="5a4cd-122">A pesar del nombre, los planes de marcado son, en términos funcionales, directivas.</span><span class="sxs-lookup"><span data-stu-id="5a4cd-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="5a4cd-123">El plan de términos de <EM>marcado</EM> se usa en lugar de, por ejemplo, la Directiva de marcado, a fin de preservar la terminología que se usa con versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a4cd-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="5a4cd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a4cd-124">See Also</span></span>


[<span data-ttu-id="5a4cd-125">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="5a4cd-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="5a4cd-126">[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a4cd-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

