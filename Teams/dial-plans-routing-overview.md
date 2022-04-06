---
title: Planes de marcado y enrutamiento
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Planes de marcado y enrutamiento en Microsoft Teams
ms.openlocfilehash: 1d99b5edef1cf6c4440a218097933e4ff5843f1d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686724"
---
# <a name="overview"></a>Información general

Los artículos de esta sección describen los planes de marcado y el enrutamiento de llamadas en Microsoft Teams. 

- [¿Qué son los planes de marcado?](what-are-dial-plans.md)
- [Crear y administrar planes de marcado](create-and-manage-dial-plans.md)
- [Enrutar llamadas a adormecedores sin asignar](routing-calls-to-unassigned-numbers.md)

Los artículos de esta sección se aplican a todas las opciones para conectarse a la red telefónica conmutada (RTC): Plan de llamadas, Conexión con operador y enrutamiento directo. Para obtener más información sobre todas las opciones de conectividad de RTC, vea [Opciones de conectividad de RTC](pstn-connectivity.md).

Si elige Plan de llamadas o Conexión con operador, la mayor parte del enrutamiento de llamadas la controla Microsoft o su proveedor. Sin embargo, el enrutamiento directo requiere pasos adicionales para configurar el enrutamiento de llamadas. 

Para el enrutamiento directo, debe configurar el enrutamiento de llamadas especificando las rutas de voz y asignando directivas de enrutamiento de voz a los usuarios. Puede configurar planes de marcado para la traducción de números en el nivel troncal para garantizar la interoperabilidad con los controladores de borde de sesión (SFC). Para obtener más información, vea [Configurar el enrutamiento de voz para enrutamiento directo](direct-routing-voice-routing.md), [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md) y [Traducir números de teléfono](direct-routing-translate-numbers.md).

Tenga en cuenta que puede asignar una directiva de enrutamiento de voz en línea de enrutamiento directo a los usuarios del plan de llamadas y Conexión con operador. Es posible que desee hacer esto, por ejemplo, para permitir que los usuarios llamen directamente a un centro de llamadas. Puede configurar un tronco de enrutamiento directo al centro de llamadas.

Si un usuario tiene una licencia de Plan de llamadas, por ejemplo, las llamadas salientes de ese usuario se enrutan automáticamente a través de la infraestructura RTC de Microsoft Calling Plan. Si configura y asigna una directiva de enrutamiento de voz en línea de enrutamiento directo al usuario, se comprueban las llamadas salientes del usuario para determinar si el número marcado coincide con un patrón de número definido en la directiva de enrutamiento de voz en línea. Si hay una coincidencia, la llamada se enruta a través del tronco del Direct Routing. Si no hay ninguna coincidencia, la llamada se enruta a través de la infraestructura RTC del plan de llamadas.

Para obtener más información, consulte [Consideraciones de directivas de enrutamiento de voz de enrutamiento directo](direct-routing-voice-routing.md#voice-routing-policy-considerations).



