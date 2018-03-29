---
title: Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información acerca de las reglas de normalización para el parque de llamada en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 4f3651394bbdb5556a83aa34739a86f8d06f1396
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a>Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial 2015
 
Obtenga información acerca de las reglas de normalización para el parque de llamada en Skype para Telefonía IP empresarial de Business Server.
  
No se deben normalizar las órbitas de llamada Park. Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados. Si debe crear una regla de normalización adicionales para evitar que sus órbitas se normalizan, siga el procedimiento de [crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md) para definir una nueva regla de normalización, por lo que este **modelo de coincidencia** identifica el intervalo de órbita y **modelo de traducción** es **$1**. Por ejemplo, si el rango de la órbita de llamada Park es 7000 a 7999, el **modelo de coincidencia** es **^ (7\d {3}) $** y **el modelo de traducción** es **$1**.
  
> [!IMPORTANT]
> Asegúrese de que no contiene la regla de normalización predeterminada en los planes de marcado **^(\d\*)**. De lo contrario, nunca se ejecutará la regla de normalización llamada Park.
  
## <a name="see-also"></a>Vea también

#### 

[Crear o modificar un plan de marcado de Skype para Business Server 2015](dial-plans.md)

