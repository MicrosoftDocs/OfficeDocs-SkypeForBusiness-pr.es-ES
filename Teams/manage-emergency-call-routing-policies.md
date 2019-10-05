---
title: Administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar las directivas de enrutamiento de llamadas de emergencia para la característica de E911 dinámica de Microsoft Teams.
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e7a1295d481db2d970fae2c77be2cff6834c6448
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401834"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Administrar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Si ha implementado el enrutamiento directo de sistema telefónico en su organización, puede usar las directivas de enrutamiento de llamadas de emergencia en Microsoft Teams para configurar los números de emergencia y especificar cómo se enrutan las llamadas de emergencia. Una política de enrutamiento de llamadas determina si se habilitan los servicios de emergencia mejorados para los usuarios que tienen asignada la Directiva, los números que se usan para llamar a servicios de emergencia (por ejemplo, 911 en Estados Unidos) y cómo se enrutan las llamadas a servicios de emergencia.

Para administrar las directivas de enrutamiento de llamadas de emergencia, vaya a**directivas de emergencia** de **voz** > en el centro de administración de Microsoft Teams o mediante Windows PowerShell. Las directivas se pueden asignar a los usuarios y a los [sitios de red](location-based-routing-terminology.md).

Para los usuarios, puede usar la directiva global (opción predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla. Para los sitios de red, cree y asigne directivas personalizadas.

Si asignó una directiva de enrutamiento de llamadas de emergencia a un sitio de red y a un usuario y dicho usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red reemplaza la que está asignada al usuario.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Crear una directiva de enrutamiento de llamadas de emergencia personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de emergencia**de **voz** > y, a continuación, haga clic en la pestaña directivas de **enrutamiento de llamadas** .
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la Directiva.
4. Para habilitar los servicios de emergencia mejorados, Active **servicios de emergencia mejorados**. Cuando se habilitan los servicios de emergencia mejorados, Teams recupera la información de directivas y ubicaciones del servicio e incluye esa información como parte de la llamada de emergencia.
5. Defina uno o más números de emergencia. Para hacerlo, en **números de emergencia**, haga lo siguiente:
    1. **Cadena de marcado de emergencia**: escriba la cadena de marcado de emergencia. Esta cadena de marcado indica que una llamada es una llamada de emergencia.
    2. **Máscara de marcado de emergencia**: para cada número de emergencia, puede especificar cero o más máscaras de marcado de emergencia. Una máscara de marcado es el número que desea traducir en el valor de la cadena de marcado de emergencia. Esto permite que se marquen números de emergencia alternativos y que la llamada tenga acceso a los servicios de emergencia. <br>Por ejemplo, agrega 112 como máscara de marcado de emergencia, que es el número de servicio de emergencia para la mayoría de Europa y 911 como la cadena de marcado de emergencia. Un usuario de equipos de Europa que visita puede no saber que 911 es el número de emergencia en los Estados Unidos y cuando marca 112, la llamada se realiza a 911. Para definir varias máscaras de marcado, separe cada valor por punto y coma. Por ejemplo, 112; 212.
    3. **Uso de RTC**: seleccione el uso de la red de telefonía pública conmutada (RTC). El uso de RTC se usa para determinar qué ruta se usa para enrutar las llamadas de emergencia de los usuarios autorizados a usarlas. La ruta asociada con este uso debe apuntar a un tronco SIP dedicado a llamadas de emergencia o a una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) que dirige las llamadas de emergencia al punto de respuesta de seguridad pública más cercano (PSAP).

    > [!NOTE]
    > Las cadenas de marcado y las máscaras de marcado deben ser únicas dentro de una directiva. Esto significa que, para una directiva, puede definir varios números de emergencia y puede establecer varias máscaras de marcado para una cadena de marcado, pero cada cadena de marcado y máscara de marcado debe usarse solo una vez.

6. Haga clic en **Guardar **.

### <a name="using-powershell"></a>Usar PowerShell

Vea [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Modificar una política de enrutamiento de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de emergencia**de **voz** > y, a continuación, haga clic en la pestaña directivas de **enrutamiento de llamadas** .
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Usar PowerShell

Consulte [set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a los usuarios

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.
2. Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.
3. En **Directiva de enrutamiento de llamadas de emergencia**, seleccione la Directiva que desea asignar y, a continuación, haga clic en **Guardar**.

Para asignar una directiva de Teams personalizada a varios usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).

También puede hacer lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de emergencia**de **voz** > y, a continuación, haga clic en la pestaña directivas de **enrutamiento de llamadas** .
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.

### <a name="using-powershell"></a>Usar PowerShell

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a>Asignar una política de enrutamiento de llamadas de emergencia personalizada a un usuario

Consulte [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a los usuarios de un grupo

Es posible que desee asignar una directiva de enrutamiento de llamadas de emergencia personalizada a varios usuarios que ya haya identificado. Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad o de distribución. Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.

En este ejemplo, asignamos una directiva denominada Directiva de enrutamiento de llamadas de emergencia HR a todos los usuarios del grupo contoso HR.  

> [!NOTE]
> Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtén la GroupObjectId del grupo en particular.
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
Obtener los miembros del grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asignar todos los usuarios del grupo a una directiva de equipos en particular. En este ejemplo, es la Directiva de enrutamiento de llamadas de emergencia de RRHH.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Asignar una directiva de enrutamiento de llamadas de emergencia personalizada a un sitio de red

Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de enrutamiento de llamadas de emergencia a un sitio de red.

Este ejemplo muestra cómo asignar una directiva denominada Directiva de enrutamiento de llamadas de emergencia 1 al sitio de Sitio1.

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

- [Administrar las directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
