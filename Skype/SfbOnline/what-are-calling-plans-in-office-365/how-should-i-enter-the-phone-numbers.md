---
title: ¿Cómo tengo que introducir los números de teléfono?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Obtenga información sobre cómo configurar números de teléfono cuando los transporta a Skype empresarial. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280534"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="78b9a-103">¿Cómo tengo que introducir los números de teléfono?</span><span class="sxs-lookup"><span data-stu-id="78b9a-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="78b9a-104">Cuando transporta números de teléfono, debe escribirlos en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="78b9a-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="78b9a-105">Cada número de teléfono o rango de número de teléfono debe introducirse por separado en cada línea.</span><span class="sxs-lookup"><span data-stu-id="78b9a-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="78b9a-106">Cuando escribe números de teléfono únicos:</span><span class="sxs-lookup"><span data-stu-id="78b9a-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="78b9a-107">Se ignorarán todos los caracteres especiales (incluido el guión "-").</span><span class="sxs-lookup"><span data-stu-id="78b9a-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="78b9a-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78b9a-108">For example:</span></span>
    
  - <span data-ttu-id="78b9a-109">Para un número de 10 dígitos: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* se corregirá a **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="78b9a-110">Para un número de 11 dígitos: **1\*() (\*&amp;42&amp;\*()\*&amp;(55550649** se corregirá a **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="78b9a-111">Si hay 10 u 11 dígitos, se ignorarán todas las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="78b9a-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="78b9a-112">Por ejemplo, \*\* \<div> 4255551234\</div>\*\* será **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="78b9a-113">se omitirán "-", el espacio y los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="78b9a-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="78b9a-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78b9a-114">For example:</span></span>
    
  - <span data-ttu-id="78b9a-115">Para un número de 10 dígitos: **(425) 555-6776** se corregirá a **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="78b9a-116">Para un número de 11 dígitos: **1 (425) 555-6776** se corregirá a **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="78b9a-117">Todas las letras se tratarán como caracteres especiales y se pasarán por alto si hay un número de 10 dígitos o de 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="78b9a-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="78b9a-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78b9a-118">For example:</span></span>
    
  - <span data-ttu-id="78b9a-119">Para un número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** se corregirá a **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="78b9a-120">Para un número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** se corregirá a **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="78b9a-121">Se corregirá cualquier combinación de caracteres especiales, incluso en otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="78b9a-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="78b9a-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78b9a-122">For example:</span></span> 
    
  - <span data-ttu-id="78b9a-123">Para un número de 10 dígitos:**中文 4 中文2ajj5\*() (\*(5 ()... 551345** se corregirá a **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="78b9a-124">Para un número de 11 dígitos:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** se corregirá a **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="78b9a-125">Si los números contienen menos de 10 dígitos o más de 11 dígitos, se resaltarán para que el usuario los corrija:</span><span class="sxs-lookup"><span data-stu-id="78b9a-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="78b9a-126">\*\*5551245\* \* se resaltará y tendrá que corregirse.</span><span class="sxs-lookup"><span data-stu-id="78b9a-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="78b9a-127">**1234567891011** se resaltará y tendrá que corregirse.</span><span class="sxs-lookup"><span data-stu-id="78b9a-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="78b9a-128">Los números que tengan menos de 10 dígitos o más de 11 dígitos, con caracteres especiales, se resaltarán sin corregirse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="78b9a-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="78b9a-129">Para un número de 7 dígitos sin caracteres especiales introducidos: **123456abcdefg7** se resaltará y tendrá que corregirse, pero las letras no se pasarán por alto.</span><span class="sxs-lookup"><span data-stu-id="78b9a-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="78b9a-130">Para un número de 7 dígitos con caracteres especiales introducidos: **12345! @ # $&amp;\*% ^ ()--@ # $% ^&amp;\*()** se resaltarán para corregirse.</span><span class="sxs-lookup"><span data-stu-id="78b9a-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="78b9a-131">Los caracteres especiales no se tendrán en cuenta.</span><span class="sxs-lookup"><span data-stu-id="78b9a-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="78b9a-132">Cuando escribes un rango de números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="78b9a-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="78b9a-133">Solo se permiten dos números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="78b9a-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="78b9a-134">El número menor debe ser el primer número del rango.</span><span class="sxs-lookup"><span data-stu-id="78b9a-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="78b9a-135">Todos los caracteres especiales (excepto el guión "-") se tratan de la misma forma que los números individuales.</span><span class="sxs-lookup"><span data-stu-id="78b9a-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="78b9a-136">Por ejemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** se corregirá a **+ 14255550123-+ 13202040659**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="78b9a-137">El "-" se usa para separar solo los dos números.</span><span class="sxs-lookup"><span data-stu-id="78b9a-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="78b9a-138">No se admite incluir varios "-" en el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="78b9a-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="78b9a-139">Por ejemplo, **(425) 555-0649-(425) 555-1115** debe especificarse como **(425) 5550649-(425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="78b9a-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="78b9a-140">**Para obtener instrucciones paso a paso, consulte [transferir números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="78b9a-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="78b9a-141">Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="78b9a-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="78b9a-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="78b9a-142">Related topics</span></span>
[<span data-ttu-id="78b9a-143">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="78b9a-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="78b9a-144">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="78b9a-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="78b9a-145">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="78b9a-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="78b9a-146">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="78b9a-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="78b9a-147">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="78b9a-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 