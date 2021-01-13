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
description: Aprenda a usar y administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar números de emergencia y especificar cómo se enrutar las llamadas de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804680"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Administrar directivas de enrutamiento de llamadas de emergencia en Microsoft Teams

Si ha implementado [](direct-routing-landing-page.md) el enrutamiento directo de sistema telefónico en su organización, puede usar las directivas de enrutamiento de llamadas de emergencia de Microsoft Teams para configurar números de emergencia y especificar cómo se enruten las llamadas de emergencia. Una directiva de enrutamiento de llamadas de emergencia determina si los servicios de emergencia mejorados están habilitados para los usuarios que tienen asignada la directiva, los números que se usan para llamar a los servicios de emergencia (por ejemplo, el 911 en estados Unidos) y cómo se enrutar las llamadas a los servicios de emergencia.

Para administrar las directivas de enrutamiento de llamadas de emergencia, vaya a las directivas de emergencia de voz en el Centro de administración de Microsoft Teams o  >   use Windows PowerShell. Las directivas se pueden asignar a usuarios y sitios [de red.](cloud-voice-network-settings.md)

Para los usuarios, puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios recibirán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede editar la configuración de la directiva global, pero no puede cambiarle el nombre ni eliminarla. Para sitios de red, puede crear y asignar directivas personalizadas.

Si asignó una directiva de enrutamiento de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red invalida la directiva asignada al usuario.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Crear una directiva personalizada de enrutamiento de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y haga clic en la pestaña Directivas de enrutamiento  >   **de** llamadas.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Para habilitar las llamadas de emergencia dinámicas, active **las llamadas de emergencia dinámicas.** Cuando se habilitan las llamadas de emergencia dinámicas, Teams recupera la información de directiva y ubicación del servicio e incluye esa información como parte de la llamada de emergencia.
5. Defina uno o varios números de emergencia. Para ello, en Números **de emergencia,** **haga** clic en Agregar y, a continuación, haga lo siguiente:
    1. **Cadena de marcado de** emergencia: introduzca la cadena de marcado de emergencia. Esta cadena de marcado indica que una llamada es una llamada de emergencia.
        > [!NOTE]
        > Para el enrutamiento directo, estamos haciendo la transición desde los clientes de Teams que envían llamadas de emergencia con un "+" delante de la cadena de marcado de emergencia. Hasta que se complete la transición, el patrón de ruta de voz para que coincida con una cadena de marcado de emergencia debe asegurarse de que se hace una coincidencia con las cadenas que tienen o no tienen un "+" anterior, como 911 y +911. Por ejemplo, ^ \\ +?911 o .*.
    2. **Máscara de marcado de** emergencia: para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia. Una máscara de marcado es el número que desea traducir en el valor de la cadena de marcado de emergencia. Esto permite marcar números de emergencia alternativos y hacer que la llamada llegue a los servicios de emergencia. <br>Por ejemplo, agregue el 112 como la máscara de marcado de emergencia (que es el número de servicio de emergencia de casi toda Europa) y el 911 como la cadena de marcado de emergencia. Un usuario de Teams de Europa que está de visita puede no saber que el 911 es el número de emergencia en Estados Unidos y, cuando marca el 112, la llamada se realiza al 911. Para definir varias máscaras de marcado, separe cada valor por punto y coma. Por ejemplo, 112;212.
    3. **Registro de uso de RTC:** seleccione el registro de uso de la red telefónica conmutada (RTC). El registro de uso de RTC se usa para determinar la ruta que se usa para enrutar llamadas de emergencia de usuarios que están autorizados a usarlas. La ruta asociada a este uso debe apuntar a un tronco de Protocolo de inicio de sesión (SIP) dedicado a llamadas de emergencia o a una puerta de enlace del número de identificación de ubicación de emergencia (ELIN) que enruta las llamadas de emergencia al punto de respuesta de seguridad pública (PSAP) más cercano.

    > [!NOTE]
    > Las cadenas de marcado y las máscaras de marcado deben ser únicas dentro de una directiva. Esto significa que, para una directiva, puede definir varios números de emergencia y establecer varias máscaras de marcado para una cadena de marcado, pero cada cadena de marcado y máscara de marcado solo debe usarse una vez.

6. Haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Editar una directiva de enrutamiento de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Directivas de emergencia de voz y haga clic en la pestaña Directivas de enrutamiento  >   **de** llamadas.
2. Seleccione la directiva haciendo clic a la izquierda del nombre de la directiva y, a continuación, haga clic en **Editar.**
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="using-powershell"></a>Con PowerShell

Vea [Set-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Asignar una directiva personalizada de enrutamiento de llamadas de emergencia a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vea también [Grant-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Asignar una directiva de enrutamiento de llamada de emergencia personalizada a un sitio de red

Use el [cmdlet Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de enrutamiento de llamadas de emergencia a un sitio de red.

En este ejemplo se muestra cómo asignar una directiva denominada Directiva de enrutamiento de llamadas de emergencia 1 al sitio Site1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

[Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
