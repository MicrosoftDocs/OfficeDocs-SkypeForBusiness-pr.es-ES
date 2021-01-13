---
title: Administrar directivas de enrutamiento de voz en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
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
localization_priority: Normal
search.appverid: MET150
description: Aprenda a crear y administrar directivas de enrutamiento de voz en Microsoft Teams.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802560"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Administrar directivas de enrutamiento de voz en Microsoft Teams

Si ha implementado [](direct-routing-landing-page.md) el enrutamiento directo de sistema telefónico en su organización, use las directivas de enrutamiento de voz para permitir que los usuarios de Teams y Skype Empresarial Online reciban y realicen llamadas telefónicas a la red telefónica conmutada (RTC) con su infraestructura de telefonía local.

Una directiva de enrutamiento de voz es un contenedor para los registros de uso de RTC. Para crear y administrar directivas de enrutamiento de voz, vaya a las directivas de enrutamiento de voz de voz en el Centro de administración de Microsoft Teams o mediante el  >   uso de Windows PowerShell.

Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiarle el nombre ni eliminarla.

Es importante saber que asignar una directiva de enrutamiento de voz a un usuario no les permite realizar llamadas RTC en Teams. También necesitará habilitar el usuario para el enrutamiento directo de Sistema telefónico y completar otros pasos de configuración. Para obtener más información, [vea Configurar enrutamiento directo.](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Crear una directiva de enrutamiento de voz personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las **directivas** de enrutamiento de voz y, a continuación, haga clic  >  en **Agregar.**<br>
    ![Captura de pantalla de la página Agregar directiva de enrutamiento de voz en el Centro de administración de Microsoft Teams ](media/manage-voice-routing-policies.png) 
2. Escriba un nombre y una descripción para la directiva.
3. En **Registros de uso de RTC,** haga clic en Agregar uso de RTC y, a continuación, seleccione los registros que desea agregar.  Si necesita crear un nuevo registro de uso de RTC, haga clic en **Agregar.**
4. Si ha agregado varios registros de uso de RTC, organice los registros en el orden que desee.
5. Cuando haya terminado, haga clic en **Aplicar.**
6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

See [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Editar una directiva de enrutamiento de voz

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas **de** enrutamiento  >  **de voz.**
2. Seleccione la directiva haciendo clic a la izquierda del nombre de la directiva y, a continuación, haga clic en **Editar.**
3. Haga clic en Agregar o quitar registros de uso de **RTC,** realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Asignar una directiva de enrutamiento de voz personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vea también [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Configurar el enrutamiento de voz para enrutamiento directo](direct-routing-voice-routing.md)

[Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
