---
title: Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información sobre las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
---

# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial
 
Obtenga información sobre las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
  
Las órbitas de estacionamiento de llamadas no deben normalizarse. Compruebe los planes de marcado para asegurarse de que los números de órbita no se normalizan. Si debe crear una regla de normalización adicional para evitar que sus órbitas se normalizan, siga el procedimiento de [Crear](dial-plans.md) o modificar un plan de marcado en Skype Empresarial Server para definir una nueva regla de normalización, de modo que **Pattern to match** identifique el intervalo de órbitas y **el** patrón de traducción sea **$1**. Por ejemplo, si el intervalo de órbitas de estacionamiento de llamadas es de 7000 a 7999, el patrón que se va a coincidir es **^(7\d{3})$** y el patrón de traducción es **$1**. 
  
> [!IMPORTANT]
> Asegúrese de que la regla de normalización predeterminada en los planes de marcado no contiene **^(\d\*)**. De lo contrario, la regla de normalización de estacionamiento de llamadas nunca se ejecutará.
  
## <a name="see-also"></a>Vea también

[Crear o modificar un plan de marcado en Skype Empresarial Server](dial-plans.md)

