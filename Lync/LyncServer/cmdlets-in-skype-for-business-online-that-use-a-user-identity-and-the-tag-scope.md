---
title: Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de etiqueta
description: Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de la etiqueta.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2ddbcc9c90096cea5fad4cb680f4ea1797ce48
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545616"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="98e59-103">Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de etiqueta</span><span class="sxs-lookup"><span data-stu-id="98e59-103">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="98e59-104">Los cmdlets **Grant-CS** (que se usan para asignar directivas a usuarios) requieren dos identificadores: una identidad de usuario (el parámetro Identity) y la identidad de una directiva por usuario (el parámetro PolicyName).</span><span class="sxs-lookup"><span data-stu-id="98e59-104">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="98e59-105">Por ejemplo, para asignar la Directiva de voz, RedmondVoicePolicy, al usuario Ken Myer, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="98e59-105">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="98e59-106">Hay dos cosas que debe tener en cuenta al asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="98e59-106">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="98e59-107">En primer lugar, solo se pueden asignar directivas por usuario.</span><span class="sxs-lookup"><span data-stu-id="98e59-107">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="98e59-108">No se puede asignar la directiva global a un usuario.</span><span class="sxs-lookup"><span data-stu-id="98e59-108">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="98e59-109">Por ejemplo, se producirá un error en este comando:</span><span class="sxs-lookup"><span data-stu-id="98e59-109">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="98e59-110">Este comando produce un error porque no es necesario asignar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="98e59-110">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="98e59-111">Si desea administrar a un usuario mediante la directiva global, asegúrese de que no asigna a ese usuario una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="98e59-111">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="98e59-112">Si no se ha asignado ninguna directiva por usuario a un usuario, el usuario se administrará automáticamente mediante la directiva global.</span><span class="sxs-lookup"><span data-stu-id="98e59-112">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="98e59-113">¿Qué ocurre si el usuario ya tiene asignada una directiva por usuario y desea quitar la asignación de esa Directiva y, en su lugar, administrar al usuario la directiva global?</span><span class="sxs-lookup"><span data-stu-id="98e59-113">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="98e59-114">En ese caso, primero usará la siguiente sintaxis, que anula la asignación de una directiva por usuario al conceder a esa usuario una directiva nula:</span><span class="sxs-lookup"><span data-stu-id="98e59-114">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="98e59-115">Grant-CsVoicePolicy – Identity "Ken Myer": PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="98e59-115">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="98e59-116">En segundo lugar, tenga en cuenta que las directivas por usuario se crean en el ámbito de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="98e59-116">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="98e59-117">Sin embargo, puede omitir el **prefijo** de etiqueta al especificar un nombre de directiva.</span><span class="sxs-lookup"><span data-stu-id="98e59-117">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="98e59-118">Estos dos comandos son idénticos:</span><span class="sxs-lookup"><span data-stu-id="98e59-118">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="98e59-119">Si desea devolver las identidades de todas las directivas por usuario (o, al menos, todas las directivas por usuario del tipo especificado, como las directivas de voz), use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="98e59-119">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="98e59-120">Los siguientes cmdlets usan la identidad del usuario y el ámbito de la etiqueta:</span><span class="sxs-lookup"><span data-stu-id="98e59-120">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="98e59-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98e59-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="98e59-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98e59-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="98e59-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98e59-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="98e59-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98e59-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="98e59-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98e59-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="98e59-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98e59-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="98e59-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98e59-127">See Also</span></span>


[<span data-ttu-id="98e59-128">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="98e59-128">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="98e59-129">[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="98e59-129">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

