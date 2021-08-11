---
title: Administrar directivas de llamadas y voz en Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Obtenga información sobre Teams de llamadas y llamadas.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b3cea712fee971ce441e5406bc32c1304c4a53374baf290046945595d3bea1f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335810"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Administrar directivas de llamadas y llamadas en Microsoft Teams

Las directivas de voz y llamadas se usan para controlar la voz y las llamadas en Microsoft Teams.

## <a name="emergency-calling-policies"></a>Directivas de llamadas de emergencia

Use directivas [de llamadas de emergencia](manage-emergency-calling-policies.md) para configurar lo que ocurre cuando un usuario de su organización realiza una llamada de emergencia. Estas directivas se administran en el Teams de administración o mediante Windows PowerShell.

![Captura de pantalla de la directiva de llamadas de emergencia.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Directivas de enrutamiento de llamadas de emergencia

Si su organización ha implementado **Sistema telefónico** enrutamiento directo, puede usar directivas de enrutamiento de llamadas de emergencia para determinar dónde se enruten las llamadas de emergencia, si los servicios de emergencia mejorados están habilitados y qué números se usan para los servicios de emergencia. [](manage-emergency-call-routing-policies.md) Estas directivas se administran con PowerShell o en el centro Microsoft Teams administración.

![Captura de pantalla de la directiva de enrutamiento de llamadas de emergencia.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Directivas de identificación de llamadas

[Las directivas de identificación de](caller-id-policies.md) llamadas se usan para cambiar o bloquear el identificador de llamada.

![Captura de pantalla de la directiva de identificación de llamadas.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Directivas de enrutamiento de voz

Una [directiva de enrutamiento de](manage-voice-routing-policies.md) voz es un contenedor para los registros de uso de red telefónica conmutada (RTC). Puede usar estas directivas si su organización ha implementado **Sistema telefónico enrutamiento directo.** Las directivas de enrutamiento de voz se pueden administrar con PowerShell o en el Teams de administración.

![Captura de pantalla de la directiva de enrutamiento de voz.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Directivas de llamada

[Las directivas de](teams-calling-policy.md) llamadas controlan qué características de llamadas y reenvío de llamadas están disponibles para los usuarios, incluido si un usuario puede realizar llamadas privadas, enviar llamadas a grupos de llamadas y enrutar llamadas al correo de voz.

![Captura de pantalla de la directiva de llamadas.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Parque de llamadas y directivas de recuperación

[El parque de llamadas y la recuperación](call-park-and-retrieve.md) permite a los usuarios poner a otros usuarios en espera y permite al mismo usuario o a otra persona continuar la llamada.

![Captura de pantalla del parque de llamadas y la directiva de recuperación.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Crear y administrar planes de marcado

[Los planes de marcado](create-and-manage-dial-plans.md) traducen los números de teléfono marcados para la autorización de llamadas y el enrutamiento. Puede crear y administrar planes de marcado a través de PowerShell o en el Microsoft Teams de administración.

![Captura de pantalla del plan de marcado.](media/dial-plans.png)

## <a name="related-topics"></a>Temas relacionados

* [Administrar directivas de llamadas de emergencia en Microsoft Teams](manage-emergency-calling-policies.md)
* [Administrar directivas de enrutamiento de llamadas de emergencia](manage-emergency-call-routing-policies.md)
* [Administrar directivas del id. de llamada en Microsoft Teams](caller-id-policies.md)
* [Administrar directivas de enrutamiento de voz](manage-voice-routing-policies.md)
* [Directivas de llamadas en Microsoft Teams](teams-calling-policy.md)
* [Estacionamiento y recuperación de llamadas en Microsoft Teams](call-park-and-retrieve.md)
* [Crear y administrar planes de marcado](create-and-manage-dial-plans.md)
* [Administrar Teams con directivas](manage-teams-with-policies.md)
