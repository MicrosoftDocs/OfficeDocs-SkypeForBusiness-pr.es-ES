---
title: Administrar directivas de enrutamiento de llamadas de emergencia
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de enrutamiento de llamadas de emergencia en Microsoft Teams configurar números de emergencia y especificar cómo se enrutar las llamadas de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096184"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Administrar directivas de enrutamiento de llamadas de emergencia en Microsoft Teams

Si ha implementado [](direct-routing-landing-page.md) Sistema telefónico enrutamiento directo en su organización, puede usar directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar números de emergencia y especificar cómo se enruten las llamadas de emergencia. Una directiva de enrutamiento de llamadas de emergencia determina si los servicios de emergencia mejorados están habilitados para los usuarios a los que se les asignó la directiva, los números usados para llamar a servicios de emergencia (por ejemplo, 911 en Estados Unidos) y cómo se enrutar las llamadas a los servicios de emergencia.

Para administrar las directivas de enrutamiento de llamadas de emergencia, vaya a Directivas de emergencia de voz en el centro de administración de Microsoft Teams o mediante  >   Windows PowerShell. Las directivas se pueden asignar a usuarios y sitios [de red.](cloud-voice-network-settings.md)

Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiar el nombre ni eliminarlo. Para los sitios de red, cree y asigne directivas personalizadas.

Si asignó una directiva de enrutamiento de llamadas de emergencia a un sitio de red y a un usuario y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Crear una directiva de enrutamiento de llamadas de emergencia personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del centro Microsoft Teams de administración, vaya a Directivas de emergencia de voz y, a continuación, haga clic en la pestaña Directivas de enrutamiento  >   **de** llamadas.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Para habilitar las llamadas de emergencia dinámicas, active **Llamadas de emergencia dinámicas.** Cuando las llamadas de emergencia dinámicas están habilitadas, Teams recupera información de directiva y ubicación del servicio e incluye esa información como parte de la llamada de emergencia.
5. Defina uno o varios números de emergencia. Para ello, en **Números de emergencia,** haga clic **en Agregar** y, a continuación, haga lo siguiente:
    1. **Cadena de marcado de emergencia:** escriba la cadena de marcado de emergencia. Esta cadena de marcado indica que una llamada es una llamada de emergencia.
        > [!NOTE]
        > Para enrutamiento directo, nos estamos alejando de Teams clientes que envían llamadas de emergencia con un "+" delante de la cadena de marcado de emergencia. Hasta que se complete la transición, el patrón de ruta de voz para que coincida con una cadena de marcado de emergencia debe asegurarse de que se realiza una coincidencia para las cadenas que tienen y no tienen un "+" anterior, como 911 y +911. Por ejemplo, ^ \\ +?911 o .*.
    2. **Máscara de marcado de** emergencia: para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia. Una máscara de marcado es el número que desea traducir al valor de la cadena de marcado de emergencia. Esto permite que se marquen números de emergencia alternativos y que la llamada llegue a los servicios de emergencia. <br>Por ejemplo, agregue 112 como máscara de marcado de emergencia, que es el número de servicio de emergencia de la mayor parte de Europa, y 911 como cadena de marcado de emergencia. Un Teams de Europa que está de visita puede no saber que el 911 es el número de emergencia en Los Estados Unidos y, cuando llaman al 112, la llamada se realiza al 911. Para definir varias máscaras de marcado, separe cada valor por punto y coma. Por ejemplo, 112;212.
    3. **Registro de uso rtc:** seleccione el registro de uso de red telefónica conmutada (RTC). El registro de uso de RTC se usa para determinar qué ruta se usa para enrutar llamadas de emergencia de usuarios autorizados a usarlas. La ruta asociada con este uso debe apuntar a un tronco del Protocolo de inicio de sesión (SIP) dedicado a las llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al Punto de respuesta de seguridad pública (PSAP) más próximo.

    > [!NOTE]
    > Las cadenas de marcado y las máscaras de marcado deben ser únicas dentro de una directiva. Esto significa que, para una directiva, puede definir varios números de emergencia y puede establecer varias máscaras de marcado para una cadena de marcado, pero cada cadena de marcado y máscara de marcado solo debe usarse una vez.

6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Editar una directiva de enrutamiento de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede editar la directiva global o las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del centro Microsoft Teams de administración, vaya a Directivas de emergencia de voz y, a continuación, haga clic en la pestaña Directivas de enrutamiento  >   **de** llamadas.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vea también [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a un sitio de red

Use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de enrutamiento de llamadas de emergencia a un sitio de red.

En este ejemplo se muestra cómo asignar una directiva denominada Directiva de enrutamiento de llamadas de emergencia 1 al sitio de Sitio1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

[Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)