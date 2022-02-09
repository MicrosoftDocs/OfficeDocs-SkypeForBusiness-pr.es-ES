---
title: Administrar directivas de enrutamiento de llamadas para enrutamiento directo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo crear y administrar directivas de enrutamiento de llamadas Microsoft Teams enrutamiento directo.
ms.openlocfilehash: 348eef9e33dba4f33868c94d72e21289b1a87690
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457400"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>Administrar directivas de enrutamiento de llamadas para enrutamiento directo

Si ha implementado enrutamiento directo [](direct-routing-landing-page.md) en su organización, use directivas de enrutamiento de llamadas para permitir que los usuarios de Teams reciban y realicen llamadas telefónicas a la red telefónica conmutada (RTC) con su infraestructura de telefonía local.

Una directiva de enrutamiento de llamadas (también denominada directiva de enrutamiento de voz) es un contenedor para los registros de uso de RTC. Para crear y administrar directivas de enrutamiento de voz, vaya a Directivas de enrutamiento de **VoiceVoice**  >  en el centro de administración de Microsoft Teams o mediante Windows PowerShell.

Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiar el nombre ni eliminarlo.

Es importante saber que asignar una directiva de enrutamiento de voz a un usuario no permite realizar llamadas RTC en Teams. También tendrá que habilitar al usuario para enrutamiento directo y completar otros pasos de configuración. Para obtener más información, vea [Configurar enrutamiento directo](direct-routing-configure.md).

## <a name="create-a-custom-call-routing-policy"></a>Crear una directiva de enrutamiento de llamadas personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Directivas de enrutamiento **de VoiceVoice** >  y, a continuación, haga clic en **Agregar**.<br>

2. Escriba un nombre y una descripción para la directiva.

3. En **Registros de uso de** RTC, haga clic **en Agregar uso de RTC** y, a continuación, seleccione los registros que desea agregar. Si necesita crear un nuevo registro de uso de RTC, haga clic en **Agregar**.

4. Si ha agregado varios registros de uso de RTC, organice los registros en el orden que desee.
5. Cuando haya terminado, haga clic en **Aplicar**.

6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-call-routing-policy"></a>Editar una directiva de enrutamiento de llamadas

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede editar la directiva global o las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Directivas **de enrutamiento de VoiceVoice** > .

2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.

3. Haga **clic en Agregar o quitar registros de uso de RTC**, realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-call-routing-policy-to-users"></a>Asignar una directiva de enrutamiento de llamadas personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vea también [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Configurar el enrutamiento de llamadas para enrutamiento directo](direct-routing-voice-routing.md)

[Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)