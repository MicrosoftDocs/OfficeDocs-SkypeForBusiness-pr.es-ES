---
title: Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información acerca de las reglas de normalización para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a>Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015
 
Obtenga información acerca de las reglas de normalización para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
  
No se deben normalizar órbitas de estacionamiento de llamadas. Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados. Si debe crear una regla de normalización adicionales para evitar que su Órbitas que se normalizará, siga el procedimiento descrito en [crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md) para definir una nueva regla de normalización, por lo que este **modelo de coincidencia** identifica el intervalo de Órbitas y **patrón de traducción** es **$1**. Por ejemplo, si el intervalo de órbitas de estacionamiento de llamadas se 7000-7999, el **modelo de coincidencia** es **^(7\d{3})$** y **patrón de traducción** es **$1**.
  
> [!IMPORTANT]
> Asegúrese de que la regla de normalización de forma predeterminada en los planes de marcado no contenga **^(\d\*)**. De lo contrario, nunca se ejecutará la regla de normalización de estacionamiento de llamadas.
  
## <a name="see-also"></a>Vea también

#### 

[Crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md)

