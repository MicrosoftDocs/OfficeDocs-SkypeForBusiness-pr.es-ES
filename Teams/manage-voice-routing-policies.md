---
title: Administrar directivas de enrutamiento de voz en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a crear y administrar directivas de enrutamiento de voz en Microsoft Teams.
ms.openlocfilehash: 7fa2530e170d398598e56d4b4f846cc316871b16
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160982"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Administrar directivas de enrutamiento de voz en Microsoft Teams

Si ha implementado el [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md) en su organización, puede usar las directivas de enrutamiento de voz para permitir que los usuarios de Teams y Skype empresarial online reciban y realicen llamadas telefónicas a la red de telefonía pública conmutada (RTC) con su infraestructura de telefonía local.

Una directiva de enrutamiento de voz es un contenedor de registros de uso de RTC. Para crear y administrar directivas de enrutamiento de voz, **vaya a** > **directivas de enrutamiento** de voz de voz en el centro de administración de Microsoft Teams o mediante Windows PowerShell.

Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla.

Es importante saber que asignar una directiva de enrutamiento de voz a un usuario no les permite realizar llamadas RTC en Teams. También tendrá que habilitar el enrutamiento directo del usuario para el sistema telefónico y completar otros pasos de configuración. Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md).

## <a name="create-a-custom-voice-routing-policy"></a>Crear una directiva de enrutamiento de voz personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de enrutamiento de voz**de **voz** > y haga clic en **Agregar**.<br>
    ![Captura de pantalla de la página Agregar Directiva de enrutamiento de voz en el centro de administración de Microsoft Teams](media/manage-voice-routing-policies.png) 
2. Escriba un nombre y una descripción para la directiva.
3. En **registros de uso de RTC**, haga clic en **Agregar uso de RTC**y, a continuación, seleccione los registros que desee agregar. Si necesita crear un registro de uso de RTC nuevo, haga clic en **Agregar**.
4. Si ha agregado varios registros de uso de RTC, organícelos en el orden que desee.
5. Cuando haya terminado, haga clic en **aplicar**.
6. Haga clic en **Guardar **.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Editar una directiva de enrutamiento de voz

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de enrutamiento de voz**de **voz** > .
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Haga clic en **Agregar o quitar registros de uso de RTC**, realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Asignar una directiva de enrutamiento de voz personalizada a los usuarios

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.
3. En **Directiva de enrutamiento de voz**, seleccione la Directiva que desea asignar y, a continuación, haga clic en **Guardar**.

Para asignar una directiva de Teams personalizada a varios usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).

También puede hacer lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de enrutamiento de voz**de **voz** > .
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
5. Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Configurar el enrutamiento de voz para el enrutamiento directo](direct-routing-voice-routing.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
