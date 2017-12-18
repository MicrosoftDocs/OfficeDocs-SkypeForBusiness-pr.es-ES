---
title: "¿Cómo debo introducir los números de teléfono?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.PortOrderNumbers
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
description: "Learn how to set up phone numbers when you port them to Skype for Business. "
---

# ¿Cómo debo introducir los números de teléfono?

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Al convertir números de teléfono, debe escribir en el formato correcto.
  
> [!NOTE]
> Cada número de teléfono o rango de números debe introducirse en una línea aparte. 
  
- Cuando introduzca números de teléfono únicos:
    
  - Se omitirán todos los caracteres especiales (incluido el guion "-"). Por ejemplo:
    
  - Para un número de 10 dígitos: **&amp;*(425*()(*&amp;4&amp;*())(*250649** se corregirá a **+14255550649**.
    
  - Para un número de 11 dígitos: **1*()(*&amp;42&amp;*()(*&amp;55550649** se corregirá a **+14255550649**.
    
  - Se omitirán todas las etiquetas si hay 10 u 11 dígitos. Por ejemplo, **<div> 4255551234</div>** será **+14255551234**.
    
  - Se omitirán el paréntesis, el espacio y "-". Por ejemplo:
    
  - Para un número de 10 dígitos: **(425) 555-6776** se corregirá a **+14255556776**.
    
  - Para un número de 11 dígitos: **1(425) 555-6776** se corregirá a **+14255556776**.
    
  - Todas las letras se tratan como caracteres especiales y pasa por alto si hay un número de teléfono de 10 o 11 dígitos. Por ejemplo:
    
  - Para un número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** se corregirá a **+14255550649**.
    
  - Para un número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** se corregirá a **+14255550649**.
    
  - Se corregirá cualquier combinación de caracteres especiales, incluso en otros idiomas. Por ejemplo: 
    
  - Para un número de 10 dígitos: **中文4中文2ajj5*（）（*（5()...551345** se corregirá a **+14555551345**.
    
  - Para un número de 11 dígitos: **中文4中文2$a5*（）（*（5()...55(.1345** se corregirá a **+14555551345**.
    
  - Si los números contienen menos de 10 o más de 11 dígitos, se resaltarán para que el usuario corregir:
    
  - ** 5551245** se resaltará y deberá corregirse.
    
  - **1234567891011** se resaltará y deberá corregirse.
    
  - Los números que tienen menos de 10 o más de 11 dígitos, con todos los caracteres especiales, se resaltarán sin que se corrige automáticamente.
    
  - Para un número de 7 dígitos sin caracteres especiales que se introduce: **123456abcdefg7** se resaltarán y deben corregirse, pero no se pasan por alto las letras.
    
  - Para un número de 7 dígitos con caracteres especiales que se introduce: **12345!@#$%^ &amp; * (): @# $% ^ &amp; * () 7** se resaltará para corregirse. No se pasan por alto los caracteres especiales.
    
- Cuando introduzca un rango de números de teléfono:
    
  - Solo se permitirán dos números de teléfono. El número más bajo debe ser el primero del rango.
    
  - Todos los caracteres especiales (excepto el guión "-") es la misma considera solo números. Por ejemplo, **(425) 555 0 &amp; * (123-(1425) 5557899nm** se corregirán **+14255550123 - +13202040659**.
    
  - La "-" se usa para separar sólo los dos números. No se admite para incluir múltiples "-" en el intervalo de números. Por ejemplo:, **(425) 555-0649-(425) 555-1115** deben especificarse como **(425) 5550649 - (425) 5551115**.
    
 **Para obtener instrucciones detalladas paso a paso, consulte [Números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).**
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)
  
[Período de llamada de salida complementario de conferencias de audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

