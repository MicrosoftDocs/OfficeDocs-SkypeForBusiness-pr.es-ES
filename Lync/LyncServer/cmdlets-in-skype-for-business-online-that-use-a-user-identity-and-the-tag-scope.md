---
title: Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de la etiqueta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31f6b76b6c63b39bf22f456260f084736d481513
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233130"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="181f8-102">Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="181f8-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="181f8-103">Los cmdlets **Grant-CS** (que se usan para asignar directivas a los usuarios) requieren dos identificadores: una identidad de usuario (el parámetro Identity) y la identidad de una directiva por usuario (el parámetro PolicyName).</span><span class="sxs-lookup"><span data-stu-id="181f8-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="181f8-104">Por ejemplo, para asignar la Directiva de voz, RedmondVoicePolicy, al usuario Ken Myer, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="181f8-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="181f8-105">Hay dos cosas que se deben tener en cuenta al asignar directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="181f8-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="181f8-106">En primer lugar, solo se pueden asignar directivas por usuario.</span><span class="sxs-lookup"><span data-stu-id="181f8-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="181f8-107">No se puede asignar la directiva global a un usuario.</span><span class="sxs-lookup"><span data-stu-id="181f8-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="181f8-108">Por ejemplo, este comando fallará:</span><span class="sxs-lookup"><span data-stu-id="181f8-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="181f8-109">Este comando falla porque no es necesario asignar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="181f8-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="181f8-110">Si desea administrar un usuario mediante la directiva global, asegúrese de no asignarle a ese usuario una directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="181f8-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="181f8-111">Si no se ha asignado ninguna directiva por usuario a un usuario, el usuario se administrará automáticamente mediante la directiva global.</span><span class="sxs-lookup"><span data-stu-id="181f8-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="181f8-112">¿Qué sucede si el usuario tiene asignada una directiva por usuario y desea cancelar la asignación de esa Directiva y, en su lugar, la directiva global la administrará?</span><span class="sxs-lookup"><span data-stu-id="181f8-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="181f8-113">En ese caso, primero usará la sintaxis siguiente, que anula la asignación de una directiva por usuario al otorgar a ese usuario una directiva nula:</span><span class="sxs-lookup"><span data-stu-id="181f8-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="181f8-114">Grant-CsVoicePolicy – identidad "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="181f8-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="181f8-115">En segundo lugar, tenga en cuenta que las directivas por usuario se crean en el ámbito de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="181f8-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="181f8-116">Sin embargo, puede omitir el **prefijo** de etiqueta al especificar un nombre de directiva.</span><span class="sxs-lookup"><span data-stu-id="181f8-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="181f8-117">Estos dos comandos son idénticos:</span><span class="sxs-lookup"><span data-stu-id="181f8-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="181f8-118">Si desea devolver las identidades de todas las directivas de cada usuario (o, al menos, todas las directivas de cada usuario de tipo especificado, como las directivas de voz), use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="181f8-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="181f8-119">Los siguientes cmdlets usan la identidad del usuario y el ámbito de la etiqueta:</span><span class="sxs-lookup"><span data-stu-id="181f8-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="181f8-120">[Grant-ClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="181f8-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="181f8-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="181f8-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="181f8-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="181f8-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="181f8-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="181f8-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="181f8-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="181f8-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="181f8-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="181f8-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="181f8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="181f8-126">See Also</span></span>


[<span data-ttu-id="181f8-127">Identidades, ámbitos y espacios empresariales en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="181f8-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="181f8-128">[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="181f8-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

