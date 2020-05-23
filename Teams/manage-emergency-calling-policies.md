---
title: Administrar las directivas de llamadas de emergencia en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar las directivas de llamadas de emergencia en Microsoft Teams para definir qué sucede cuando un usuario de un equipo de su organización hace una llamada de emergencia.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea02c1c7f9d4142db9cb25c00714e04a28e0e5e3
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350204"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Administrar las directivas de llamadas de emergencia en Microsoft Teams

Si su organización usa planes de llamadas o el enrutamiento directo de sistemas telefónicos implementados, puede usar directivas de llamadas de emergencia en Microsoft Teams para definir lo que sucede cuando un usuario de un equipo de su organización hace una llamada de emergencia. Puedes establecer a quién deseas notificar y cómo se les notifica cuando un usuario que tiene asignada la Directiva llama a servicios de emergencia. Por ejemplo, puede configurar opciones de directiva para notificar automáticamente al escritorio de seguridad de su organización y hacer que escuchen llamadas de emergencia.  

Para administrar las directivas de llamadas de emergencia **Voice**, vaya a  >  **directivas de emergencia** de voz en el centro de administración de Microsoft Teams o mediante Windows PowerShell. Las directivas se pueden asignar a los usuarios y a los [sitios de red](cloud-voice-network-settings.md).

Para los usuarios, puede usar la directiva global (opción predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Tenga en cuenta que puede modificar la configuración de la directiva global, pero no puede cambiarle el nombre o eliminarla. Para los sitios de red, cree y asigne directivas personalizadas.

Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario y dicho usuario se encuentra en el sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.

## <a name="create-a-custom-emergency-calling-policy"></a>Crear una directiva de llamadas de emergencia personalizada

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.
4. Establezca cómo desea notificar a los usuarios de su organización, normalmente el escritorio, Cuándo se realiza una llamada de emergencia. Para ello, en **modo de notificación**, seleccione una de las siguientes opciones:
    - **Enviar notificación solo**: se envía un mensaje de chat de equipo a los usuarios y grupos que especifique.
    - **En conferencia, pero**desactivado: se envía un mensaje de chat de Teams a los usuarios y grupos que especifique y pueden escuchar (pero no participar) en la conversación entre el autor de la llamada y el operador PSAP.
    - **Conferencias en y están** reactivadas (próximamente **)**: se envía un mensaje de chat de equipos a los usuarios y grupos que especifique y pueden reactivar el audio para escuchar y participar en la conversación entre el autor de la llamada y el operador PSAP.
5.  Si seleccionó el modo **de notificación está silenciado en conferencia** , en el cuadro **número de llamadas para notificaciones** , puede escribir un número de teléfono RTC de un usuario o un grupo para llamar y unirse a la llamada de emergencia. Por ejemplo, escriba el número del escritorio de seguridad de su organización, que recibirá una llamada cuando se haga una llamada de emergencia y, después, podrá escuchar la llamada.
6. Busque y seleccione uno o más usuarios o grupos, como el escritorio de seguridad de su organización, para notificar cuando se realice una llamada de emergencia.  La notificación se puede enviar a las direcciones de correo electrónico de los usuarios, los grupos de distribución y los grupos de seguridad. Se puede notificar a un máximo de 50 usuarios.
7. Haga clic en **Guardar **.

### <a name="using-powershell"></a>Con PowerShell

Vea [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modificar una directiva de llamadas de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Consulte [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Asignar una directiva de llamadas de emergencia personalizada a los usuarios

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

Para asignar una directiva a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.
3. En **política de llamadas de emergencia**, seleccione la Directiva que desea asignar y, a continuación, haga clic en **Guardar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, busque los usuarios o filtre la vista para mostrar los usuarios que desea.
2. En la columna **&#x2713;** (marca), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en el &#x2713; (marca de verificación) en la parte superior de la tabla.
3. Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **aplicar**.  

También puede hacer lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de emergencia de **voz**  >  **Emergency policies**y, a continuación, haga clic en la pestaña **directivas de llamada** .
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
5. Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>Asignar una directiva de llamadas de emergencia personalizada a un usuario

Consulte [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>Asignar una directiva de llamadas de emergencia personalizada a los usuarios de un grupo

Es posible que desee asignar una directiva de llamadas de emergencia personalizada a varios usuarios que ya haya identificado. Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad. Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial.

En este ejemplo, asignamos una directiva llamada Directiva de llamadas de emergencia de operaciones a todos los usuarios del grupo de operaciones de contoso.  

> [!NOTE]
> Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtén la GroupObjectId del grupo en particular.
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
Obtener los miembros del grupo especificado.
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asignar todos los usuarios del grupo a una directiva de equipos en particular. En este ejemplo, es una directiva de enrutamiento de llamadas de emergencia.
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Asignar una directiva de llamadas de emergencia personalizada a un sitio de red

Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) para asignar una directiva de llamadas de emergencia a un sitio de red.

En el ejemplo siguiente se muestra cómo asignar una directiva denominada política de llamadas de emergencia de Contoso 1 al sitio de Sitio1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de enrutamiento de llamadas de emergencia en Teams](manage-emergency-call-routing-policies.md)
- [Información general de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios de Teams](assign-policies.md)
