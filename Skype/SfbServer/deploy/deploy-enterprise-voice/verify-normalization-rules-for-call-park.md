---
title: Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información sobre las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: ca76c15d7f71afa75e9b9247eab9cd96e5baedb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771535"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial
 
Obtenga información sobre las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
  
Las órbitas de estacionamiento de llamadas no deben normalizarse. Compruebe los planes de marcado para asegurarse de que los números de órbita no se normalizan. Si debe crear una regla de normalización adicional para evitar que las órbitas se normalizan, siga el procedimiento de Crear o modificar un plan de marcado en [Skype Empresarial Server](dial-plans.md) para definir una nueva regla de normalización, de modo que **Pattern to match** identifique el intervalo de órbitas y **el** patrón de traducción sea **$1**. Por ejemplo, si el intervalo de órbitas de estacionamiento de llamadas  es de 7000 a 7999, el patrón que se va a coincidir es **^(7\d {3} )$** y el patrón de traducción **es** **$1**.
  
> [!IMPORTANT]
> Asegúrese de que la regla de normalización predeterminada en los planes de marcado no contiene **^(\d \* )**. De lo contrario, la regla de normalización de estacionamiento de llamadas nunca se ejecutará.
  
## <a name="see-also"></a>Consulte también

[Crear o modificar un plan de marcado en Skype Empresarial Server](dial-plans.md)

