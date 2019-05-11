---
title: Compruebe las reglas de normalización para el estacionamiento de llamadas en Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información acerca de las reglas de normalización para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 6f27daca3ef3f1bcdc4c70f04b92ccaa29a569a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892268"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Compruebe las reglas de normalización para el estacionamiento de llamadas en Skype para la empresa
 
Obtenga información acerca de las reglas de normalización para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
  
No se deben normalizar órbitas de estacionamiento de llamadas. Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados. Si debe crear una regla de normalización adicionales para evitar que su Órbitas que se normalizará, siga el procedimiento descrito en [crear o modificar un plan de marcado de Skype para Business Server](dial-plans.md) para definir una nueva regla de normalización, por lo que este **modelo de coincidencia** identifica el intervalo de Órbitas y **patrón de traducción** es **$1**. Por ejemplo, si el intervalo de órbitas de estacionamiento de llamadas se 7000-7999, el **modelo de coincidencia** es **^(7\d{3})$** y **patrón de traducción** es **$1**.
  
> [!IMPORTANT]
> Asegúrese de que la regla de normalización de forma predeterminada en los planes de marcado no contenga **^(\d\*)**. De lo contrario, nunca se ejecutará la regla de normalización de estacionamiento de llamadas.
  
## <a name="see-also"></a>Vea también

[Crear o modificar un plan de marcado de Skype para Business Server](dial-plans.md)

