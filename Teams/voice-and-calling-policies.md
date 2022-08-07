---
title: Administrar directivas de voz y llamadas en Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Obtenga más información sobre las directivas de voz y llamadas de Teams.
audience: admin
ms.localizationpriority: medium
ms.collection:
- M365-voice
ms.openlocfilehash: 5a6676d29a439ed978385d096c6e8b0584049557
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270295"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Administrar directivas de voz y llamadas en Microsoft Teams

Las directivas de voz y llamadas se usan para controlar la voz y las llamadas en Microsoft Teams.

## <a name="emergency-calling-policies"></a>Directivas de llamadas de emergencia

Las [directivas de llamadas de emergencia](manage-emergency-calling-policies.md) se usan para configurar lo que ocurre cuando un usuario de la organización realiza una llamada de emergencia. Estas directivas se administran en el Centro de administración de Teams o mediante Windows PowerShell.

![Captura de pantalla de la directiva de llamadas de emergencia.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>Directivas de enrutamiento de llamadas de emergencia

Si su organización ha implementado el **enrutamiento directo del sistema telefónico**, puede usar [directivas de enrutamiento de llamadas de emergencia](manage-emergency-call-routing-policies.md) para determinar dónde se enrutan las llamadas de emergencia, si los servicios de emergencia mejorados están habilitados y qué números se usan para los servicios de emergencia. Estas directivas se administran con PowerShell o en el Centro de administración de Microsoft Teams.

![Captura de pantalla de la directiva de enrutamiento de llamadas de emergencia.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>Directivas de identificador de llamada

[Las directivas de identificador de llamada](caller-id-policies.md) se usan para cambiar o bloquear el identificador de llamada.

![Captura de pantalla de la directiva de identificación de llamadas.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>Directivas de enrutamiento de voz

Una [directiva de enrutamiento de voz](manage-voice-routing-policies.md) es un contenedor para los registros de uso de la red telefónica conmutada (RTC). Puede usar estas directivas si su organización ha implementado el **enrutamiento directo del sistema telefónico**. Las directivas de enrutamiento de voz se pueden administrar con PowerShell o en el Centro de administración de Teams.

![Captura de pantalla de la directiva de enrutamiento de voz.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>Directivas de llamada

[Las directivas de](teams-calling-policy.md) llamadas controlan qué características de desvío de llamadas y llamadas están disponibles para los usuarios, incluido si un usuario puede realizar llamadas privadas, enviar llamadas a grupos de llamadas y enrutar llamadas al correo de voz.

![Captura de pantalla de la directiva de llamadas.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>Estacionar llamadas y recuperar directivas

[Estacionar y recuperar llamadas](call-park-and-retrieve.md) permite a los usuarios poner a otros usuarios en espera y permite que el mismo usuario o cualquier otra persona pueda continuar la llamada.

![Captura de pantalla del parque de llamadas y la directiva de recuperación.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>Crear y administrar planes de marcado

[Los planes de marcado](create-and-manage-dial-plans.md) traducen los números de teléfono marcados para la autorización y el enrutamiento de llamadas. Puede crear y administrar planes de marcado a través de PowerShell o en el Centro de administración de Microsoft Teams.

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
