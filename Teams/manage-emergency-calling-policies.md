---
title: Administrar directivas de llamadas de emergencia en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar y administrar las directivas de llamadas de emergencia en Microsoft Teams para definir lo que ocurre cuando un usuario de Teams de su organización realiza una llamada de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1e516252317a0e5f14e705b674255048fb3defb5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804690"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Administrar directivas de llamadas de emergencia en Microsoft Teams

Si su [](set-up-calling-plans.md) organización usa planes de llamadas o enrutamiento directo de sistema telefónico [implementado,](direct-routing-landing-page.md)puede usar directivas de llamadas de emergencia en Microsoft Teams para definir lo que ocurre cuando un usuario de Teams de su organización realiza una llamada de emergencia. Puede establecer a quién notificar y cómo se le notificará cuando un usuario asignado a la directiva llame a los servicios de emergencia. Por ejemplo, puede configurar las opciones de directiva para notificar automáticamente al servicio de seguridad de su organización y que escuche en llamadas de emergencia.  

Para administrar las directivas de llamadas de emergencia, vaya a directivas **de** emergencia de voz en el Centro de administración de Microsoft Teams o  >   use Windows PowerShell. Las directivas se pueden asignar a usuarios y sitios [de red.](cloud-voice-network-settings.md)

Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiarle el nombre ni eliminarla. Para los sitios de red, puede crear y asignar directivas personalizadas.

Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red invalidará la directiva asignada al usuario.

## <a name="create-a-custom-emergency-calling-policy"></a>Crear una directiva de llamadas de emergencia personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y, a continuación, haga clic en la  >  pestaña **Directivas de** llamadas.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Configure cómo quiere notificar a las personas de su organización(normalmente el servicio de seguridad) cuando se realiza una llamada de emergencia. Para ello, en **modo de notificación,** seleccione una de las siguientes opciones:
    - **Enviar solo notificación:** se envía un mensaje de chat de Teams a los usuarios y grupos que especifique.
    - **Conferencias,** pero silenciadas: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden escuchar (pero no participar) la conversación entre el autor de la llamada y el operador PSAP.
    - **Conferencias** y cambios de llamada **(próximamente):** se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden activar el sonido para escuchar y participar en la conversación entre el autor de la llamada y el operador PSAP.
5.  Si seleccionó  el modo de notificación Con **conferencias,** pero está silenciado, en el cuadro Números para marcar para las notificaciones de llamadas de emergencia, puede introducir un número de teléfono RTC de un usuario o grupo para llamar y unirse a la llamada de emergencia. Por ejemplo, escriba el número del servicio de seguridad de su organización que recibirá una llamada cuando se haga una llamada de emergencia y podrá escucharla.
6. Busque y seleccione uno o varios usuarios o grupos, como el servicio de seguridad de su organización, para notificar cuando se realiza una llamada de emergencia.  La notificación se puede enviar a direcciones de correo electrónico de usuarios, grupos de distribución y grupos de seguridad. Se puede notificar a un máximo de 50 usuarios.
7. Haga clic en **Aplicar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [New-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)

## <a name="edit-an-emergency-calling-policy"></a>Editar una directiva de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede editar la directiva global o las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y, a continuación, haga clic en la  >  pestaña **Directivas de** llamadas.
2. Seleccione la directiva haciendo clic a la izquierda del nombre de la directiva y, a continuación, haga clic en **Editar.**
3. Realice los cambios que desee y, a continuación, haga clic en **Aplicar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Asignar una directiva de llamadas de emergencia personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vea también [Grant-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Asignar una directiva de llamadas de emergencia personalizada a un sitio de red

Use el [cmdlet Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de llamadas de emergencia a un sitio de red.

En el ejemplo siguiente se muestra cómo asignar una directiva denominada Directiva de llamadas de emergencia 1 de Contoso al sitio Sitio1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

[Administrar directivas de enrutamiento de llamadas de emergencia en Teams](manage-emergency-call-routing-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
