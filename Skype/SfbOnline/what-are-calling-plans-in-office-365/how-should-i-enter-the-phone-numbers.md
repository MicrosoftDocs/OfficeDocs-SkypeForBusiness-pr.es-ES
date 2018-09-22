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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Obtenga información sobre cómo configurar los números de teléfono cuando instalarlas en Skype para la empresa. '
ms.openlocfilehash: 8d214ea7cf21ea713de28763f36b9995160fb395
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958145"
---
# <a name="how-should-i-enter-the-phone-numbers"></a>¿Cómo tengo que introducir los números de teléfono?

Al convertir los números de teléfono, debe escribir en el formato correcto. 
  
> [!NOTE]
> Cada número de teléfono o el intervalo de número de teléfono debe especificarse por separado en cada línea. 
  
- Al escribir los números de teléfono único:
    
  - Se pasará por alto todos los caracteres especiales (incluidos guión "-"). Por ejemplo:
    
  - Para un número de 10 dígitos: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** se corregirán a **+14255550649**.
    
  - Para un número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** se corregirán a **+14255550649**.
    
  - Si hay 10 u 11 dígitos, se omitirá todas las etiquetas. Por ejemplo, ** \<div > 4255551234\</div >** será **+14255551234**.
    
  - "-", se omitirá espacio y paréntesis. Por ejemplo:
    
  - Para un número de 10 dígitos: **(425) 555-6776** se corregirán a **+14255556776**.
    
  - Para un número de 11 dígitos: se corregirán **1(425) 555-6776** a **+14255556776**.
    
  - Todas las letras se tratan como caracteres especiales y no tiene en cuenta si hay un número de teléfono de 10 dígitos o 11 dígitos. Por ejemplo:
    
  - Para un número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** se corregirán a **+14255550649**.
    
  - Para un número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** se corregirán a **+14255550649**.
    
  - Cualquier combinación de caracteres especiales, incluso en otros idiomas, se corregirán. Por ejemplo: 
    
  - Para un número de 10 dígitos:**中文4中文2ajj5\*() (\*(5()... 551345** se corregirán a **+14555551345**.
    
  - Para un número de 11 dígitos:**中文4中文2$ a5\*() (\*(5()... 55 (.1345** se corregirán a **+14555551345**.
    
  - Si los números contienen menos de 10 o más de 11 dígitos, se resaltará para que el usuario corregir:
    
  - \*\*5551245\* \* se resaltará y deberá corregirse.
    
  - **1234567891011** se resaltará y deberá corregirse.
    
  - Todos los números que son menos de 10 o más de 11 dígitos, con caracteres especiales, se resaltará sin que se corrigen automáticamente.
    
  - Para un número de 7 dígitos sin caracteres especiales que se introduce: **123456abcdefg7** se resaltará y es preciso corregir, pero no se pasa por alto las letras.
    
  - Para un número de 7 dígitos con caracteres especiales que se introduce: **12345!@#$%^&amp;\*()--@# $% ^&amp;\*() 7** se resaltará para corregirse. No se pasa por alto los caracteres especiales.
    
- Cuando se introduce un intervalo de números de teléfono.
    
  - Se permiten sólo dos números de teléfono. El número menor debe ser el primer número del intervalo.
    
  - Todos los caracteres especiales (excepto el guión "-") son tratar de la misma como números único. Por ejemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** se corregirá **+ 14255550123 - +13202040659**.
    
  - La "-" se usa para separar sólo los dos números. No se admite para incluir varios "-" en el intervalo de números. Por ejemplo, **(425) 555-0649-(425) 555-1115** debe especificarse como **(425) 5550649 - (425) 5551115**.
    
 **Para obtener instrucciones paso a paso, vea [transferir los números de teléfono para Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**

 > [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 