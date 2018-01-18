---
title: "¿Cómo debo escribir los números de teléfono?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom: Calling Plans
description: "Aprenda a configurar los números de teléfono cuando instalarlas en Skype para el negocio. "
ms.openlocfilehash: 1906fc98f47402ec740d71ff69b67b07392ae57d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="e2333-103">¿Cómo debo escribir los números de teléfono?</span><span class="sxs-lookup"><span data-stu-id="e2333-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="e2333-104">Al convertir números de teléfono, debe escribir en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="e2333-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e2333-105">Cada número de teléfono o un rango de número de teléfono debe escribirse por separado en cada línea.</span><span class="sxs-lookup"><span data-stu-id="e2333-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="e2333-106">Al escribir números de teléfono único:</span><span class="sxs-lookup"><span data-stu-id="e2333-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="e2333-107">Se pasará por alto todos los caracteres especiales (incluidos los guiones "-").</span><span class="sxs-lookup"><span data-stu-id="e2333-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="e2333-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2333-108">For example:</span></span>
    
  - <span data-ttu-id="e2333-109">Para un número de 10 dígitos: \*\* &amp; \\*(425\\*() (\\*&amp;4&amp;\\*()) (\\*250649\*\* a **+14255550649**, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="e2333-109">For a 10-digit number: **&amp;\\*(425\\*()(\\*&amp;4&amp;\\*())(\\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e2333-110">Para un número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** a **+14255550649**, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="e2333-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e2333-111">Si hay 10 u 11 dígitos, se omitirán todas las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e2333-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="e2333-112">Por ejemplo, ** \<div > 4255551234\</div >** será **+14255551234**.</span><span class="sxs-lookup"><span data-stu-id="e2333-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="e2333-113">"-", se omitirá espacio y paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e2333-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="e2333-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2333-114">For example:</span></span>
    
  - <span data-ttu-id="e2333-115">Para un número de 10 dígitos: **(425) 555-6776** se corregirá para **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="e2333-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="e2333-116">Para un número de 11 dígitos: se corregirán **555-6776 1(425)** a **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="e2333-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="e2333-117">Todas las letras serán tratadas como caracteres especiales y pasa por alto si hay un número de teléfono de 10 o 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="e2333-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="e2333-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2333-118">For example:</span></span>
    
  - <span data-ttu-id="e2333-119">Para un número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** se corregirá para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="e2333-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e2333-120">Para un número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** se corregirá para **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="e2333-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e2333-121">Cualquier combinación de caracteres especiales, incluso en otros idiomas, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="e2333-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="e2333-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e2333-122">For example:</span></span> 
    
  - <span data-ttu-id="e2333-123">Para un número de 10 dígitos:**中文4中文2ajj5\*() (\*(5()... 551345** se corregirá para **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="e2333-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="e2333-124">Para un número de 11 dígitos:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** a **+14555551345**, se corregirá.</span><span class="sxs-lookup"><span data-stu-id="e2333-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="e2333-125">Si los números contienen menos de 10 o más de 11 dígitos, se resaltará el usuario corregir:</span><span class="sxs-lookup"><span data-stu-id="e2333-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="e2333-126">\*\*5551245\* \* se resaltará y deberá corregirse.</span><span class="sxs-lookup"><span data-stu-id="e2333-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="e2333-127">**1234567891011** se resaltará y deberá corregirse.</span><span class="sxs-lookup"><span data-stu-id="e2333-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="e2333-128">Se resaltarán los números de menos de 10 o más de 11 dígitos, con caracteres especiales, sin que se corrige automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e2333-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="e2333-129">Para un número de 7 dígitos sin caracteres especiales que se introduce: **123456abcdefg7** se resaltará y deberá corregirse, pero no se pasa por alto las letras.</span><span class="sxs-lookup"><span data-stu-id="e2333-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="e2333-130">Para un número de 7 dígitos con caracteres especiales que se introduce: **12345!@#$%^&amp;\*(): @# $% ^&amp;\*() 7** se resaltará para corregirse.</span><span class="sxs-lookup"><span data-stu-id="e2333-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="e2333-131">Los caracteres especiales no se omiten.</span><span class="sxs-lookup"><span data-stu-id="e2333-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="e2333-132">Cuando se introduce un intervalo de números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e2333-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="e2333-133">Se permiten sólo dos números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e2333-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="e2333-134">El número menor debe ser el primer número del intervalo.</span><span class="sxs-lookup"><span data-stu-id="e2333-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="e2333-135">Todos los caracteres especiales (excepto el guión "-") son como números solo tratar de la misma.</span><span class="sxs-lookup"><span data-stu-id="e2333-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="e2333-136">Por ejemplo, **(425) 555 0&amp;\\*(123-(1425) 5557899nm** se corregirá a **+14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="e2333-136">For example, **(425)555 0&amp;\\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="e2333-137">El "-" se utiliza para separar sólo los dos números.</span><span class="sxs-lookup"><span data-stu-id="e2333-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="e2333-138">No se admite para incluir múltiples "-" en el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="e2333-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="e2333-139">Por ejemplo, **(425) 555-0649-(425) 555-1115** se debe escribir como **(425) 5550649 - (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="e2333-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="e2333-140">**Para obtener instrucciones detalladas paso a paso, consulte [transferir números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="e2333-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="e2333-141">Si necesita obtener más números de teléfono que esto, ponte [en contacto con soporte técnico para productos de empresa - Admin ayuda](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="e2333-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="e2333-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e2333-142">Related topics</span></span>
[<span data-ttu-id="e2333-143">Transferencia de preguntas habituales de los números de teléfono</span><span class="sxs-lookup"><span data-stu-id="e2333-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="e2333-144">Diferentes tipos de números de teléfono utilizados para llamar a planes</span><span class="sxs-lookup"><span data-stu-id="e2333-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="e2333-145">Administrar números de teléfono de la organización</span><span class="sxs-lookup"><span data-stu-id="e2333-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="e2333-146">Términos y condiciones de las llamadas de emergencias</span><span class="sxs-lookup"><span data-stu-id="e2333-146">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="e2333-147">Skype para los negocios en línea: etiqueta de descargo de responsabilidad llamada de emergencia</span><span class="sxs-lookup"><span data-stu-id="e2333-147">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)