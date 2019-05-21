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
# <a name="how-should-i-enter-the-phone-numbers"></a>¿Cómo tengo que introducir los números de teléfono?

Cuando transporta números de teléfono, debe escribirlos en el formato correcto. 
  
> [!NOTE]
> Cada número de teléfono o rango de número de teléfono debe introducirse por separado en cada línea. 
  
- Cuando escribe números de teléfono únicos:
    
  - Se ignorarán todos los caracteres especiales (incluido el guión "-"). Por ejemplo:
    
  - Para un número de 10 dígitos: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** se corregirá a **+ 14255550649**.
    
  - Para un número de 11 dígitos: **1\*() (\*&amp;42&amp;\*()\*&amp;(55550649** se corregirá a **+ 14255550649**.
    
  - Si hay 10 u 11 dígitos, se ignorarán todas las etiquetas. Por ejemplo, ** \<div> 4255551234\</div>** será **+ 14255551234**.
    
  - se omitirán "-", el espacio y los paréntesis. Por ejemplo:
    
  - Para un número de 10 dígitos: **(425) 555-6776** se corregirá a **+ 14255556776**.
    
  - Para un número de 11 dígitos: **1 (425) 555-6776** se corregirá a **+ 14255556776**.
    
  - Todas las letras se tratarán como caracteres especiales y se pasarán por alto si hay un número de 10 dígitos o de 11 dígitos. Por ejemplo:
    
  - Para un número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** se corregirá a **+ 14255550649**.
    
  - Para un número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** se corregirá a **+ 14255550649**.
    
  - Se corregirá cualquier combinación de caracteres especiales, incluso en otros idiomas. Por ejemplo: 
    
  - Para un número de 10 dígitos:**中文 4 中文2ajj5\*() (\*(5 ()... 551345** se corregirá a **+ 14555551345**.
    
  - Para un número de 11 dígitos:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** se corregirá a **+ 14555551345**.
    
  - Si los números contienen menos de 10 dígitos o más de 11 dígitos, se resaltarán para que el usuario los corrija:
    
  - \*\*5551245\* \* se resaltará y tendrá que corregirse.
    
  - **1234567891011** se resaltará y tendrá que corregirse.
    
  - Los números que tengan menos de 10 dígitos o más de 11 dígitos, con caracteres especiales, se resaltarán sin corregirse automáticamente.
    
  - Para un número de 7 dígitos sin caracteres especiales introducidos: **123456abcdefg7** se resaltará y tendrá que corregirse, pero las letras no se pasarán por alto.
    
  - Para un número de 7 dígitos con caracteres especiales introducidos: **12345! @ # $&amp;\*% ^ ()--@ # $% ^&amp;\*()** se resaltarán para corregirse. Los caracteres especiales no se tendrán en cuenta.
    
- Cuando escribes un rango de números de teléfono.
    
  - Solo se permiten dos números de teléfono. El número menor debe ser el primer número del rango.
    
  - Todos los caracteres especiales (excepto el guión "-") se tratan de la misma forma que los números individuales. Por ejemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** se corregirá a **+ 14255550123-+ 13202040659**.
    
  - El "-" se usa para separar solo los dos números. No se admite incluir varios "-" en el intervalo de números. Por ejemplo, **(425) 555-0649-(425) 555-1115** debe especificarse como **(425) 5550649-(425) 5551115**.
    
  **Para obtener instrucciones paso a paso, consulte [transferir números de teléfono a Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**

  > [!NOTE]
  > Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 