---
title: "¿Cómo debo escribir los números de teléfono?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: "Aprenda a configurar los números de teléfono cuando instalarlas en Skype para el negocio. "
ms.openlocfilehash: a7364c5ebf72730179c6848dc79172f4f971ff6a
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="2df37-103">¿Cómo debo escribir los números de teléfono?</span><span class="sxs-lookup"><span data-stu-id="2df37-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="2df37-104">Al convertir números de teléfono, debe escribir en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="2df37-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2df37-105">Cada número de teléfono o un rango de número de teléfono debe escribirse por separado en cada línea.</span><span class="sxs-lookup"><span data-stu-id="2df37-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="2df37-106">Al escribir números de teléfono único:</span><span class="sxs-lookup"><span data-stu-id="2df37-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="2df37-107">Se pasará por alto todos los caracteres especiales (incluidos los guiones "-").</span><span class="sxs-lookup"><span data-stu-id="2df37-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="2df37-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2df37-108">For example:</span></span>
    
  - <span data-ttu-id="2df37-109">Para un número de 10 dígitos: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* a **+14255550649**, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="2df37-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="2df37-110">Para un número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** a **+14255550649**, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="2df37-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="2df37-111">Si hay 10 u 11 dígitos, se omitirán todas las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="2df37-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="2df37-112">Por ejemplo, ** \<div > 4255551234\</div >** será **+14255551234**.</span><span class="sxs-lookup"><span data-stu-id="2df37-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="2df37-113">"-", se omitirá espacio y paréntesis.</span><span class="sxs-lookup"><span data-stu-id="2df37-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="2df37-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2df37-114">For example:</span></span>
    
  - <span data-ttu-id="2df37-115">Para un número de 10 dígitos: **(425) 555-6776** se corregirá para **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="2df37-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="2df37-116">Para un número de 11 dígitos: se corregirán **555-6776 1(425)** a **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="2df37-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="2df37-117">Todas las letras serán tratadas como caracteres especiales y pasa por alto si hay un número de teléfono de 10 o 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="2df37-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="2df37-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2df37-118">For example:</span></span>
    
  - <span data-ttu-id="2df37-119">Para un número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** se corregirá para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="2df37-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="2df37-120">Para un número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** se corregirá para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="2df37-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="2df37-121">Cualquier combinación de caracteres especiales, incluso en otros idiomas, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="2df37-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="2df37-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2df37-122">For example:</span></span> 
    
  - <span data-ttu-id="2df37-123">Para un número de 10 dígitos:**中文4中文2ajj5\*() (\*(5()... 551345** se corregirá para **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="2df37-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="2df37-124">Para un número de 11 dígitos:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** a **+14555551345**, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="2df37-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="2df37-125">Si los números contienen menos de 10 o más de 11 dígitos, se resaltará el usuario corregir:</span><span class="sxs-lookup"><span data-stu-id="2df37-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="2df37-126">\*\*5551245\* \* se resaltará y deberá corregirse.</span><span class="sxs-lookup"><span data-stu-id="2df37-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="2df37-127">**1234567891011** se resaltará y deberá corregirse.</span><span class="sxs-lookup"><span data-stu-id="2df37-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="2df37-128">Se resaltarán los números de menos de 10 o más de 11 dígitos, con caracteres especiales, sin que se corrige automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2df37-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="2df37-129">Para un número de 7 dígitos sin caracteres especiales que se introduce: **123456abcdefg7** se resaltará y deberá corregirse, pero no se pasa por alto las letras.</span><span class="sxs-lookup"><span data-stu-id="2df37-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="2df37-130">Para un número de 7 dígitos con caracteres especiales que se introduce: **12345!@#$%^&amp;\*(): @# $% ^&amp;\*() 7** se resaltará para corregirse.</span><span class="sxs-lookup"><span data-stu-id="2df37-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="2df37-131">Los caracteres especiales no se omiten.</span><span class="sxs-lookup"><span data-stu-id="2df37-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="2df37-132">Cuando se introduce un intervalo de números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="2df37-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="2df37-133">Se permiten sólo dos números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="2df37-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="2df37-134">El número menor debe ser el primer número del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2df37-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="2df37-135">Todos los caracteres especiales (excepto el guión "-") son como números solo tratar de la misma.</span><span class="sxs-lookup"><span data-stu-id="2df37-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="2df37-136">Por ejemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** se corregirá a **+14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="2df37-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="2df37-137">El "-" se utiliza para separar sólo los dos números.</span><span class="sxs-lookup"><span data-stu-id="2df37-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="2df37-138">No se admite para incluir múltiples "-" en el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="2df37-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="2df37-139">Por ejemplo, **(425) 555-0649-(425) 555-1115** se debe escribir como **(425) 5550649 - (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="2df37-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="2df37-140">**Para obtener instrucciones detalladas paso a paso, consulte [transferir números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="2df37-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="2df37-141">Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="2df37-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="2df37-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2df37-142">Related topics</span></span>
[<span data-ttu-id="2df37-143">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="2df37-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="2df37-144">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="2df37-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="2df37-145">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="2df37-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="2df37-146">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="2df37-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="2df37-147">Skype Empresarial Online: etiqueta de declinación de responsabilidades en llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="2df37-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a><span data-ttu-id="2df37-148">¿Comentarios?</span><span class="sxs-lookup"><span data-stu-id="2df37-148">Feedback?</span></span>
<span data-ttu-id="2df37-149">Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="2df37-149">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>