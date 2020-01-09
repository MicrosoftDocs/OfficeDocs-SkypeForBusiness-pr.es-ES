---
title: Administrar directivas de identificación de llamadas en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar y administrar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas de los usuarios de su organización.
ms.openlocfilehash: aed6e3cbe2053ddc16b049608247f56705626249
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992890"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Administrar directivas de identificación de llamadas en Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, puede usar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas (también conocida como identificador de línea de llamada). De forma predeterminada, se puede ver el número de teléfono de los usuarios de Teams cuando hacen una llamada a un teléfono PSTN y el número de teléfono de los autores de llamadas RTC se puede ver al llamar a un usuario de Teams. Puede usar las directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de equipos de su organización o impedir que se muestre un número entrante.

Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar la identificación de llamadas para mostrar el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.

Para administrar las directivas de identificación de llamadas, vaya a**directivas de identificación de llamadas** de **voz** > en el centro de administración de Microsoft Teams. Puede usar la directiva global (opción predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios. Los usuarios de la organización obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada.

Puede editar la directiva global o crear y asignar una directiva personalizada. Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario. Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario.

## <a name="create-a-custom-caller-id-policy"></a>Crear una directiva de identificación de llamadas personalizada

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de identificación de llamadas**de **voz** > .
2. Haga clic en **Agregar**.
![Captura de pantalla de la nueva página de la Directiva de identificación de llamadas en el centro de administración](media/caller-id-policies-add-policy.png)
3. Escriba un nombre y una descripción para la Directiva.
4. Desde aquí, elija la configuración que desee:

    - **Bloquear la identificación de llamadas entrantes**: activa esta configuración para bloquear la identificación de llamadas entrantes de llamadas entrantes.
    - **Los usuarios pueden invalidar la Directiva de identificación de llamadas**: Active esta configuración para permitir a los usuarios invalidar la configuración de la Directiva sobre cómo mostrar su número a destinatarios o no. Esto significa que los usuarios pueden elegir si deseas Mostrar la identificación de llamadas.
    - **Reemplazar la identificación de llamadas**: establezca la identificación de llamadas que se va a mostrar para los usuarios seleccionando una de las siguientes opciones:

        - **Número de usuario**: muestra el número de usuario. 
        - **Número de servicio**: te permite establecer un número de teléfono de servicio para que se muestre como la identificación de llamadas.
        - **Anonymous**: muestra la identificación de llamadas como anónima.

    - **Número de servicio para reemplazar la identificación de llamadas**: elige un número de servicio para reemplazar la identificación de llamadas de los usuarios. Esta opción está disponible si seleccionaste **número de servicio** en **reemplazar identificación de llamadas**.

5. Haga clic en **Guardar **.

## <a name="edit-a-caller-id-policy"></a>Editar una directiva de identificación de llamadas

Puede editar la directiva global o cualquier directiva personalizada que cree. 

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de identificación de llamadas**de **voz** > .
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Cambie la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Asignar una directiva de identificación de llamadas personalizada a los usuarios

Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a uno o más usuarios o el módulo de PowerShell de Skype empresarial para asignar una directiva personalizada a grupos de usuarios, como un grupo de seguridad o un grupo de distribución.

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>Asignar una directiva de identificador de línea de llamada personalizada a un usuario

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, haga clic en el usuario.
2. Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.
3. En **Directiva de identificación de llamadas**, seleccione la Directiva que desea asignar y, a continuación, elija **Guardar**.

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>Asignar una directiva de identificador de línea de llamada personalizado a varios usuarios a la vez

Para asignar una directiva de identificador de línea de llamada personalizado a varios usuarios a la vez, vea [editar la configuración de usuario de Teams en masa](edit-user-settings-in-bulk.md).

También puede hacer lo siguiente:

1. Vaya a**directivas de identificación de llamadas**de**voz** > del centro > de **Administración de Microsoft Teams**.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva.
3. Seleccione **administrar usuarios**.
4. En el panel **administrar usuarios** , busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso para cada usuario que desee agregar.
5. Cuando haya terminado de agregar usuarios, seleccione **Guardar**.

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>Asignar una directiva de identificación de llamadas personalizada a los usuarios de un grupo

Es posible que desee asignar una directiva personalizada a varios usuarios que ya haya identificado. Por ejemplo, es posible que desee asignar una directiva a todos los usuarios de un grupo de seguridad. Para ello, puede conectarse al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial. Para obtener más información sobre cómo usar PowerShell para administrar equipos, consulte [información general de Teams PowerShell](teams-powershell-overview.md).

En este ejemplo, asignamos una directiva de la tapa de la llamada personalizada denominada compatibilidad con la Directiva de identificación de llamadas a todos los usuarios del grupo soporte de contoso.  

> [!NOTE]
> Asegúrese de conectarse primero al módulo de Azure Active Directory PowerShell para Graph y al módulo de PowerShell de Skype empresarial siguiendo los pasos de [conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtén la GroupObjectId del grupo en particular.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
Obtener los miembros del grupo especificado.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Asignar todos los usuarios del grupo a una directiva determinada de identificación de llamadas. En este ejemplo, es compatible con la Directiva de identificación de llamadas.
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
Según el número de miembros del grupo, este comando puede demorar varios minutos en ejecutarse.

 ## <a name="related-topics"></a>Temas relacionados

- [Nuevo: CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

