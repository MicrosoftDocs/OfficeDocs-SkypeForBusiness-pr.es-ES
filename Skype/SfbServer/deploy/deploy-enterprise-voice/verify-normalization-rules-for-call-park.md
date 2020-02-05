---
title: Comprobar reglas de normalización para el parque de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga más información sobre las reglas de normalización de llamadas en la telefonía IP empresarial de Skype empresarial.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766893"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Comprobar reglas de normalización para el parque de llamadas en Skype empresarial
 
Obtenga más información sobre las reglas de normalización de llamadas en la telefonía IP empresarial de Skype empresarial.
  
Las órbitas del parque de llamadas no deben normalizarse. Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados. Si tiene que crear una regla de normalización adicional para evitar que las órbitas se normalizaran, siga el procedimiento de [crear o modificar un plan de marcado en Skype empresarial Server](dial-plans.md) para definir una nueva regla de normalización, de modo que el **patrón para que coincida** identifique el intervalo de la órbita y el **patrón de traducción** es de **$1**. Por ejemplo, si el intervalo de llamadas de la órbita de la órbita es 7000-7999, el **patrón de coincidencia** es **{3}^ (7 \ d) $** y el **patrón de traducción** es **$1**.
  
> [!IMPORTANT]
> Asegúrese de que la regla de normalización predeterminada en los planes de marcado no contiene **^\*(\d)**. En caso contrario, la regla de normalización del parque de llamadas nunca se ejecutará.
  
## <a name="see-also"></a>Vea también

[Crear o modificar un plan de marcado en Skype empresarial Server](dial-plans.md)

