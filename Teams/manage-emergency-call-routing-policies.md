---
title: Administrar directivas de enrutamiento de llamadas de emergencia
author: lanachin
ms.author: v-lanac
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
description: Aprenda a usar y administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar los números de emergencia y especificar cómo se enrutarán las llamadas de emergencia.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 2ec28dfa2e3e3c685ea70d882c4dd6d4d342ec7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532757"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams

Si ha implementado el [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md) en su organización, puede usar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar los números de emergencia y especificar cómo se enrutan las llamadas de emergencia. Una política de enrutamiento de llamadas determina si se habilitan los servicios de emergencia mejorados para los usuarios que tienen asignada la Directiva, los números que se usan para llamar a servicios de emergencia (por ejemplo, 911 en Estados Unidos) y cómo se enrutan las llamadas a servicios de emergencia.

Para administrar las directivas de enrutamiento de llamadas de **Voice**emergencia, vaya a  >  **directivas de emergencia** de voz en el centro de administración de Microsoft Teams o mediante Windows PowerShell. Las directivas se pueden asignar a los usuarios y a los [sitios de red](cloud-voice-network-settings.md).

Para los usuarios, puede usar la directiva global (opción predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla. Para los sitios de red, cree y asigne directivas personalizadas.

Si asignó una directiva de enrutamiento de llamadas de emergencia a un sitio de red y a un usuario y dicho usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red reemplaza la que está asignada al usuario.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Crear una directiva de enrutamiento de llamadas de emergencia personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de enrutamiento de llamadas** .
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Para habilitar las llamadas de emergencia dinámicas, activa las **llamadas de emergencia dinámicas**. Cuando se habilitan las llamadas de emergencia dinámicas, Teams recupera la información de directivas y ubicaciones del servicio e incluye esa información como parte de la llamada de emergencia.
5. Defina uno o más números de emergencia. Para hacerlo, en **números de emergencia**, haga clic en **Agregar**y, a continuación, haga lo siguiente:
    1. **Cadena de marcado de emergencia**: escriba la cadena de marcado de emergencia. Esta cadena de marcado indica que una llamada es una llamada de emergencia.
        > [!NOTE]
        > Para el enrutamiento directo, estamos pasando de los clientes de Teams a través de una llamada de emergencia con un "+" delante de la cadena de marcado de emergencia. Hasta que se complete la transición, el patrón de enrutamiento de voz que se corresponda con una cadena de marcado de emergencia debe garantizar que se realice una coincidencia con las cadenas que tengan y no tengan una "+" anterior, como 911 y + 911. Por ejemplo, ^ \\ +? 911 o. *.
    2. **Máscara de marcado de emergencia**: para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia. Una máscara de marcado es el número que desea traducir en el valor de la cadena de marcado de emergencia. Esto permite que se marquen números de emergencia alternativos y que la llamada tenga acceso a los servicios de emergencia. <br>Por ejemplo, agrega 112 como máscara de marcado de emergencia, que es el número de servicio de emergencia para la mayoría de Europa y 911 como la cadena de marcado de emergencia. Un usuario de equipos de Europa que visita puede no saber que 911 es el número de emergencia en los Estados Unidos y cuando marca 112, la llamada se realiza a 911. Para definir varias máscaras de marcado, separe cada valor por punto y coma. Por ejemplo, 112; 212.
    3. **Registro de uso de RTC**: seleccione el registro de uso de la red de telefonía pública conmutada (RTC). El registro de uso de RTC se usa para determinar qué ruta se usa para enrutar llamadas de emergencia de los usuarios autorizados a usarlos. La ruta asociada con este uso debe apuntar a un tronco de protocolo de inicio de sesión (SIP) dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que dirige las llamadas de emergencia al punto de respuesta de seguridad pública más cercano (PSAP).

    > [!NOTE]
    > Las cadenas de marcado y las máscaras de marcado deben ser únicas dentro de una directiva. Esto significa que, para una directiva, puede definir varios números de emergencia y puede establecer varias máscaras de marcado para una cadena de marcado, pero cada cadena de marcado y máscara de marcado debe usarse solo una vez.

6. Haga clic en **Guardar **.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Modificar una política de enrutamiento de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de enrutamiento de llamadas** .
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Consulte también [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a un sitio de red

Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de enrutamiento de llamadas de emergencia a un sitio de red.

Este ejemplo muestra cómo asignar una directiva denominada Directiva de enrutamiento de llamadas de emergencia 1 al sitio de Sitio1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

[Administrar las directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

[Información general de PowerShell para Teams](teams-powershell-overview.md)

[Asignar directivas a los usuarios de Teams](assign-policies.md)
