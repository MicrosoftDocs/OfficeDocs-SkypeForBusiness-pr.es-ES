---
title: Usar PowerShell para controlar el acceso de invitado a un equipo
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo usar PowerShell para permitir o bloquear el acceso de invitados a todos los equipos o a determinados equipos de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e2833d1afedb975edf2532fb69c4fdbbdb31d4
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655911"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usar PowerShell para controlar el acceso de invitado a un equipo
================================================

Además de usar el centro de administración de Microsoft 365 y el portal de Azure Active Directory (Azure AD), puede usar Windows PowerShell para controlar el acceso de invitados. Con PowerShell, puede hacer lo siguiente:
  
- Permitir o bloquear el acceso de invitados a todos los equipos y grupos de Microsoft 365

- Permitir que los invitados se agreguen a todos los equipos y grupos de Microsoft 365

- Permitir o bloquear usuarios invitados de un equipo específico o de un grupo de Microsoft 365

Para obtener más información, vea "usar PowerShell para controlar el acceso de invitados" en [administrar el acceso de invitados en grupos de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).

  
También se puede usar PowerShell para permitir o bloquear un usuario invitado en función de su dominio. Por ejemplo, vamos a imaginar que su negocio (Contoso) tiene una asociación con otra empresa (Fabrikam). Fabrikam se puede agregar a su lista de permitidos de manera que sus usuarios puedan agregar a esos invitados a sus grupos. Para obtener más información, consulte [permitir o bloquear el acceso de invitados a grupos de Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Si desea bloquear invitados en Teams y aún desea permitirles el acceso a los sitios de SharePoint, puede usar los cmdlets de PowerShell de Azure AD para deshabilitar el parámetro AllowGuestsToAccessGroups en el objeto Company, suponiendo que el uso compartido externo esté activado para los sitios de SharePoint.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Usar PowerShell para activar o desactivar el acceso de invitados

1.  Descargue el módulo de PowerShell de Skype Empresarial Online en https://www.microsoft.com/download/details.aspx?id=39366
 
2.  Conecte una sesión de PowerShell al punto de conexión de Skype Empresarial Online.

    ```powershell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  Compruebe la configuración y si `AllowGuestUser` es `$False`, use el cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para establecerlo en `$True`.

    ```powershell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Ahora puede tener usuarios invitados en Teams en su organización.


## <a name="guest-access-vs-external-access"></a>Acceso de invitado frente a acceso externo

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
