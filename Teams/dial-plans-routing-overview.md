---
title: Enrutamiento y planes de marcado de Microsoft Teams
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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Planes de marcado y enrutamiento en Microsoft Teams
ms.openlocfilehash: 1d8c4ed750369c6b5bf393ebceae850703f89395
ms.sourcegitcommit: 0a2476471713e1eba791060db2c8c888484033a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2023
ms.locfileid: "69722120"
---
# <a name="microsoft-teams-dial-plans-and-routing"></a>Enrutamiento y planes de marcado de Microsoft Teams

En los artículos de esta sección se describen los planes de marcado y el enrutamiento de llamadas en Microsoft Teams. 

- [¿Qué son los planes de marcado?](what-are-dial-plans.md)
- [Crear y administrar planes de marcado](create-and-manage-dial-plans.md)
- [Redirigir llamadas a números no asignados](routing-calls-to-unassigned-numbers.md)

Los artículos de esta sección se aplican a todas las opciones de conexión a la red telefónica conmutada (RTC): Plan de llamadas, Conexión de operadores, Teléfono móvil de Teams y Enrutamiento directo. Para obtener más información sobre todas las opciones de conectividad de RTC, vea [Opciones de conectividad de RTC](pstn-connectivity.md).

Si elige Plan de llamadas, Conexión de operadores o Teams Phone Mobile, la mayor parte del enrutamiento de llamadas la gestiona Microsoft o su proveedor. Sin embargo, el enrutamiento directo requiere pasos adicionales para configurar el enrutamiento de llamadas. 

Para el enrutamiento directo, debe configurar el enrutamiento de llamadas especificando las rutas de voz y asignando directivas de enrutamiento de voz a los usuarios. Puede configurar planes de marcado para la traducción de números en el nivel troncal para garantizar la interoperabilidad con los controladores de borde de sesión (SFC). Para obtener más información, vea [Configurar el enrutamiento de voz para enrutamiento directo](direct-routing-voice-routing.md), [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md) y [Traducir números de teléfono](direct-routing-translate-numbers.md).

Tenga en cuenta que puede asignar una directiva de enrutamiento de voz en línea de enrutamiento directo a los usuarios del plan de llamadas y a los usuarios de Operator Connect. Es posible que desee hacer esto, por ejemplo, para permitir que los usuarios llamen directamente a un centro de llamadas. Puede configurar un tronco de enrutamiento directo al centro de llamadas.

Si un usuario tiene una licencia de Plan de llamadas, por ejemplo, las llamadas salientes de ese usuario se enrutan automáticamente a través de la infraestructura RTC de Microsoft Calling Plan. Si configura y asigna una directiva de enrutamiento de voz en línea de enrutamiento directo al usuario, se comprueban las llamadas salientes del usuario para determinar si el número marcado coincide con un patrón de número definido en la directiva de enrutamiento de voz en línea. Si hay una coincidencia, la llamada se enruta a través del tronco del Direct Routing. Si no hay ninguna coincidencia, la llamada se enruta a través de la infraestructura RTC del plan de llamadas.

Para obtener más información, consulte [Consideraciones de directivas de enrutamiento de voz de enrutamiento directo](direct-routing-voice-routing.md#voice-routing-policy-considerations).



