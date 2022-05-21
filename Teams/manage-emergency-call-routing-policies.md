---
title: Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Aprenda a usar y administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar los números de emergencia y especificar cómo se enrutan las llamadas de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624124"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo

Si ha implementado [el enrutamiento directo](direct-routing-landing-page.md) en su organización, puede usar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar los números de emergencia y especificar cómo se enrutan las llamadas de emergencia. Una directiva de enrutamiento de llamadas de emergencia determina si los servicios de emergencia mejorados están habilitados para los usuarios que tienen asignada la directiva, los números que se usan para llamar a los servicios de emergencia (por ejemplo, el 911 en el Estados Unidos) y cómo se enrutan las llamadas a los servicios de emergencia. 

> [!Note]
> **Tenga en cuenta que estas directivas de ruteo de llamadas se aplican solamente al enrutamiento directo-- no se aplican a los planes de llamada o a Conexión con operador.**

Para administrar las directivas de enrutamiento de llamadas de emergencia, vaya a **Directivas de emergencia de Voice** >  en el centro de administración de Microsoft Teams o mediante Windows PowerShell. Las directivas se pueden asignar a usuarios y [sitios de red](cloud-voice-network-settings.md).

Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiarle el nombre ni eliminarla. Para los sitios de red, puede crear y asignar directivas personalizadas.

Si asignó una directiva de enrutamiento de llamadas de emergencia a un sitio de red y a un usuario y si ese usuario se encuentra en ese sitio de red, la directiva que se asigna al sitio de red invalida la directiva asignada al usuario.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Crear una directiva de enrutamiento de llamadas de emergencia personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a **Directivas** de **voiceemergency** >  y, a continuación, haga clic en la pestaña **Directivas de enrutamiento de llamadas**.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Para habilitar las llamadas de emergencia dinámicas, active **Llamadas de emergencia dinámicas**. Cuando se habilitan las llamadas de emergencia dinámicas, Teams recupera la información de directiva y ubicación del servicio e incluye esa información como parte de la llamada de emergencia.
5. Defina uno o varios números de emergencia. Para ello, en **Números de emergencia**, haga clic en **Agregar** y, a continuación, haga lo siguiente:
    1. **Cadena de marcado de emergencia**: escriba la cadena de marcado de emergencia. Esta cadena de marcado indica que una llamada es una llamada de emergencia y el patrón de ruta debe coincidir exactamente con esta cadena de marcado. 
        > [!NOTE]
        > **Para enrutamiento directo, Teams clientes ya no envían llamadas de emergencia con un "+" delante de la cadena de marcado de emergencia. Asegúrese de que el patrón de ruta de voz coincida con una cadena de marcado de emergencia refleja este cambio.**
    2. **Máscara de marcado** de emergencia: Para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia. Una máscara de marcado es el número que desea traducir al valor de la cadena de marcado de emergencia. Esto permite que se marquen los números de emergencia alternativos y que la llamada siga llegando a los servicios de emergencia. <br>Por ejemplo, agregue 112 como máscara de marcado de emergencia, que es el número de servicio de emergencia para la mayor parte de Europa, y 911 como cadena de marcado de emergencia. Es posible que un usuario Teams europeo que visita no sepa que el 911 es el número de emergencia de la Estados Unidos y, al llamar al 112, la llamada se realiza al 911. Para definir varias máscaras de marcado, separe cada valor con un punto y coma. Por ejemplo, 112;212.
    3. **Registro de uso de RTC**: seleccione el registro de uso de red telefónica conmutada (RTC). El registro de uso de RTC se usa para determinar la ruta que se usa para enrutar las llamadas de emergencia de los usuarios que están autorizados a usarlas. La ruta asociada a este uso debe apuntar a un tronco sip (Protocolo de inicio de sesión) dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enrute las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano.

    > [!NOTE]
    > Las cadenas de marcado y las máscaras de marcado deben ser únicas dentro de una directiva. Esto significa que para una directiva, puede definir varios números de emergencia y puede establecer varias máscaras de marcado para una cadena de marcado, pero cada cadena de marcado y máscara de marcado solo se debe usar una vez.

6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Editar una directiva de enrutamiento de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a **Directivas** de **voiceemergency** >  y, a continuación, haga clic en la pestaña **Directivas de enrutamiento de llamadas**.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte también [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a un sitio de red

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede asignar la directiva global o cualquier directiva personalizada que cree.

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Topología de LocationsNetwork** >  y haga clic en la pestaña **Sitios de red**.
2. Seleccione el sitio haciendo clic a la izquierda del nombre y, a continuación, haga clic en **Editar**.
3. En **Directiva de enrutamiento de llamadas de emergencia**, seleccione la directiva y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de enrutamiento de llamadas de emergencia a un sitio de red.

En este ejemplo se muestra cómo asignar una directiva denominada Directiva de enrutamiento de llamadas de emergencia 1 al sitio Site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

[Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
