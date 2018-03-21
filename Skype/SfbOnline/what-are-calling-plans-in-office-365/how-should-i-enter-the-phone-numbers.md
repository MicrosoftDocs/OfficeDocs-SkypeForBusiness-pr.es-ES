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
ms.openlocfilehash: c68a42838021c9f8a564b55dbac078af07d9031b
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a>¿Cómo debo escribir los números de teléfono?

Al convertir números de teléfono, debe escribir en el formato correcto. 
  
> [!NOTE]
> Cada número de teléfono o un rango de número de teléfono debe escribirse por separado en cada línea. 
  
- Al escribir números de teléfono único:
    
  - Se pasará por alto todos los caracteres especiales (incluidos los guiones "-"). Por ejemplo:
    
  - Para un número de 10 dígitos: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** a **+14255550649**, se corregirá.
    
  - Para un número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** a **+14255550649**, se corregirá.
    
  - Si hay 10 u 11 dígitos, se omitirán todas las etiquetas. Por ejemplo, ** \<div > 4255551234\</div >** será **+14255551234**.
    
  - "-", se omitirá espacio y paréntesis. Por ejemplo:
    
  - Para un número de 10 dígitos: **(425) 555-6776** se corregirá para **+14255556776**.
    
  - Para un número de 11 dígitos: se corregirán **555-6776 1(425)** a **+14255556776**.
    
  - Todas las letras serán tratadas como caracteres especiales y pasa por alto si hay un número de teléfono de 10 o 11 dígitos. Por ejemplo:
    
  - Para un número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** se corregirá para **+14255550649**.
    
  - Para un número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** se corregirá para **+14255550649**.
    
  - Cualquier combinación de caracteres especiales, incluso en otros idiomas, se corregirá. Por ejemplo: 
    
  - Para un número de 10 dígitos:**中文4中文2ajj5\*() (\*(5()... 551345** se corregirá para **+14555551345**.
    
  - Para un número de 11 dígitos:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** a **+14555551345**, se corregirá.
    
  - Si los números contienen menos de 10 o más de 11 dígitos, se resaltará el usuario corregir:
    
  - \*\*5551245\* \* se resaltará y deberá corregirse.
    
  - **1234567891011** se resaltará y deberá corregirse.
    
  - Se resaltarán los números de menos de 10 o más de 11 dígitos, con caracteres especiales, sin que se corrige automáticamente.
    
  - Para un número de 7 dígitos sin caracteres especiales que se introduce: **123456abcdefg7** se resaltará y deberá corregirse, pero no se pasa por alto las letras.
    
  - Para un número de 7 dígitos con caracteres especiales que se introduce: **12345!@#$%^&amp;\*(): @# $% ^&amp;\*() 7** se resaltará para corregirse. Los caracteres especiales no se omiten.
    
- Cuando se introduce un intervalo de números de teléfono.
    
  - Se permiten sólo dos números de teléfono. El número menor debe ser el primer número del intervalo.
    
  - Todos los caracteres especiales (excepto el guión "-") son como números solo tratar de la misma. Por ejemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** se corregirá a **+14255550123 - +13202040659**.
    
  - El "-" se utiliza para separar sólo los dos números. No se admite para incluir múltiples "-" en el intervalo de números. Por ejemplo, **(425) 555-0649-(425) 555-1115** se debe escribir como **(425) 5550649 - (425) 5551115**.
    
 **Para obtener instrucciones detalladas paso a paso, consulte [transferir números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).**

 > [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)