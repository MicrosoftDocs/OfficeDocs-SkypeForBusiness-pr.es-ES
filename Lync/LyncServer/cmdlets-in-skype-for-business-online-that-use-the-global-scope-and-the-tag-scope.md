---
title: Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta
description: Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de la etiqueta.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545626"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="04bd0-103">Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta</span><span class="sxs-lookup"><span data-stu-id="04bd0-103">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="04bd0-104">En Skype empresarial online, las directivas se pueden configurar en el *ámbito global* o en el *ámbito* de la etiqueta (o *por ámbito de usuario*).</span><span class="sxs-lookup"><span data-stu-id="04bd0-104">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="04bd0-105">Cuando se usan los cmdlets **Get-CS** , no es necesario especificar un ámbito o una identidad.</span><span class="sxs-lookup"><span data-stu-id="04bd0-105">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="04bd0-106">Si se llama a uno de estos cmdlets sin ningún parámetro, se devolverán todos los elementos relevantes.</span><span class="sxs-lookup"><span data-stu-id="04bd0-106">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="04bd0-107">Por ejemplo, este comando devuelve información sobre todas las directivas de acceso externo:</span><span class="sxs-lookup"><span data-stu-id="04bd0-107">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="04bd0-108">Si desea limitar los datos devueltos, solo tiene que incluir el parámetro Identity o el parámetro filter.</span><span class="sxs-lookup"><span data-stu-id="04bd0-108">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="04bd0-109">Por ejemplo, para devolver sólo la directiva global, use este comando:</span><span class="sxs-lookup"><span data-stu-id="04bd0-109">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="04bd0-110">Para devolver una directiva por usuario que tenga la identidad "RedmondAccessPolicy", use este comando:</span><span class="sxs-lookup"><span data-stu-id="04bd0-110">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="04bd0-111">Cuando se hace referencia a una directiva por usuario, el <STRONG>prefijo</STRONG> de etiqueta es opcional.</span><span class="sxs-lookup"><span data-stu-id="04bd0-111">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="04bd0-112">Esta sintaxis, que incluye el prefijo, también es válida:</span><span class="sxs-lookup"><span data-stu-id="04bd0-112">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="04bd0-113">Get-CsExternalAccessPolicy – Identity "etiqueta: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="04bd0-113">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="04bd0-114">Para devolver todas las directivas excepto las directivas globales (es decir, todas las directivas por usuario), use este comando:</span><span class="sxs-lookup"><span data-stu-id="04bd0-114">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="04bd0-115">Los siguientes cmdlets operan en el ámbito global y en el ámbito por usuario (etiqueta):</span><span class="sxs-lookup"><span data-stu-id="04bd0-115">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="04bd0-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="04bd0-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="04bd0-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="04bd0-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="04bd0-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="04bd0-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="04bd0-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="04bd0-123">A pesar del nombre, los planes de marcado son, en términos funcionales, directivas.</span><span class="sxs-lookup"><span data-stu-id="04bd0-123">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="04bd0-124">El plan de términos de <EM>marcado</EM> se usa en lugar de, por ejemplo, la Directiva de marcado, a fin de preservar la terminología que se usa con versiones anteriores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="04bd0-124">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="04bd0-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04bd0-125">See Also</span></span>


[<span data-ttu-id="04bd0-126">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="04bd0-126">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="04bd0-127">[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="04bd0-127">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

