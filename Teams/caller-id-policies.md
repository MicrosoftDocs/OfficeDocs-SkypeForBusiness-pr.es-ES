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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar y administrar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas de los usuarios de su organización.
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349784"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Administrar directivas de identificación de llamadas en Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Como administrador, puede usar directivas de identificación de llamadas en Microsoft Teams para cambiar o bloquear la identificación de llamadas (también conocida como identificador de línea de llamada). De forma predeterminada, se puede ver el número de teléfono de los usuarios de Teams cuando hacen una llamada a un teléfono PSTN y el número de teléfono de los autores de llamadas RTC se puede ver al llamar a un usuario de Teams. Puede usar las directivas de identificación de llamadas para mostrar un número de teléfono alternativo para los usuarios de equipos de su organización o impedir que se muestre un número entrante.

Por ejemplo, cuando los usuarios hacen una llamada, puede cambiar la identificación de llamadas para mostrar el número de teléfono principal de su organización en lugar de los números de teléfono de los usuarios.

Para administrar las directivas de identificación de llamadas, **Voice**vaya a  >  **directivas de identificación de llamadas** de voz en el centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear directivas personalizadas y asignarlas a los usuarios. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

Puede editar la directiva global o crear y asignar una directiva personalizada. Si un usuario tiene asignada una directiva personalizada, esa Directiva se aplica al usuario. Si un usuario no tiene asignada una directiva personalizada, la política global se aplica al usuario.

## <a name="create-a-custom-caller-id-policy"></a>Crear una directiva de identificación de llamadas personalizada

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.
2. Haga clic en **Agregar**. <br>
![Captura de pantalla de la nueva página de la Directiva de identificación de llamadas en el centro de administración](media/caller-id-policies-add-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. Desde aquí, elija la configuración que desee:

    - **Bloquear la identificación de llamadas entrantes**: activa esta configuración para bloquear la identificación de llamadas entrantes de llamadas entrantes.
    - **Invalidar la Directiva de identificación de llamadas**: activa esta configuración para permitir a los usuarios invalidar la configuración de la Directiva relativa a la presentación de su número a destinatarios o no. Esto significa que los usuarios pueden elegir si deseas Mostrar la identificación de llamadas. Para obtener más información, consulte [control del usuario final de la identificación de llamadas salientes](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).
    - **Cambie la identificación de llamadas por**: establezca la identificación de llamadas que se va a mostrar para los usuarios seleccionando una de las siguientes opciones:

        - **Número de usuario**: muestra el número de usuario. 
        - **Número de servicio**: te permite establecer un número de teléfono de servicio para que se muestre como la identificación de llamadas.
        - **Anonymous**: muestra la identificación de llamadas como anónima.

    - **Reemplazar la identificación de llamadas por este número de servicio**: elige un número de servicio para reemplazar la identificación de llamadas de los usuarios. Esta opción está disponible si seleccionaste **número de servicio** en **reemplazar la identificación de llamadas por**.

5. Haga clic en **Guardar **.

## <a name="edit-a-caller-id-policy"></a>Editar una directiva de identificación de llamadas

Puede editar la directiva global o cualquier directiva personalizada que cree. 

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Voice**  >  **directivas de identificación de llamadas**de voz.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Cambie la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Asignar una directiva de identificación de llamadas personalizada a los usuarios

Puede usar el centro de administración de Microsoft Teams para asignar una directiva personalizada a uno o más usuarios o al módulo de PowerShell de Skype empresarial para asignar una directiva personalizada a los usuarios de un grupo, como un grupo de seguridad o un grupo de distribución.

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a>Asignar una directiva de identificador de línea de llamada personalizada a los usuarios

Para asignar una directiva a un usuario:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. Haga clic en **directivas**y, junto a **directivas asignadas**, haga clic en **Editar**.
3. En **Directiva de identificación de llamadas**, seleccione la Directiva que desea asignar y, a continuación, elija **Guardar**.

Para asignar una directiva a varios usuarios a la vez:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**y, a continuación, busque los usuarios o filtre la vista para mostrar los usuarios que desea.
2. En la columna **&#x2713;** (marca), seleccione los usuarios. Para seleccionar todos los usuarios, haga clic en el &#x2713; (marca de verificación) en la parte superior de la tabla.
3. Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **aplicar**.  

También puede hacer lo siguiente:

1. Vaya a directivas de identificación de llamadas de voz del **centro de administración de Microsoft Teams**  >  **Voice**  >  **Caller ID policies**.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla.
3. Seleccione **Administrar usuarios**.
4. En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
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
- [Asignar directivas a los usuarios de Teams](assign-policies.md)
