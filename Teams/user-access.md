---
title: Administrar el acceso de los usuarios a Microsoft Teams
manager: SerdarSoysal
ms.author: mikeplum
author: MikePlumleyMSFT
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a administrar el acceso de los usuarios a Teams asignando o quitando una licencia de Teams a los usuarios de su organización.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9affb1fc93bf79cd7f583f0e74b02bd06f604f0d
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657260"
---
# <a name="manage-user-access-to-teams"></a>Gestionar acceso de los usuarios a Microsoft Teams

Para administrar el acceso a Teams a nivel de usuario, asigne o quite una licencia de producto de Microsoft Teams. Excepto si se une a reuniones de Teams de forma anónima, cada usuario de su organización debe tener una licencia de Teams para poder usar Teams. Puede asignar una licencia de Teams para nuevos usuarios cuando se creen cuentas de usuario nuevas o para usuarios con cuentas existentes.

De forma predeterminada, cuando se asigna un plan de licencias (por ejemplo, Microsoft 365 Enterprise E3 o Microsoft 365 Empresa Premium) a un usuario, se asigna automáticamente una licencia de Teams y el usuario está habilitado para Teams. Puede deshabilitar o habilitar Teams para un usuario quitando o asignando una licencia en cualquier momento.

Use las directivas de mensajería, administradas desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de Administración de Teams</a>, para controlar qué características de mensajería de canal y chat están disponibles para los usuarios de Teams. Puede usar la directiva predeterminada o bien crear una o más directivas de mensajería personalizadas para los miembros de su organización. Para obtener más información, lea [Administrar directivas de mensajería en Teams](messaging-policies-in-teams.md).
Puede administrar las licencias de Teams en la Centro de administración de Microsoft 365 o mediante PowerShell. Debe ser administrador global o administrador de administración de usuarios para administrar las licencias.

> [!NOTE]
> Le recomendamos que habilite Teams para todos los usuarios para que los equipos se puedan formar orgánicamente para proyectos y otras iniciativas dinámicas. Incluso si está ejecutando un piloto, puede ser útil mantener Teams habilitado para todos los usuarios, pero solo comunicaciones de destino para el grupo piloto de usuarios.

## <a name="using-the-microsoft-365-admin-center"></a>Usar el Centro de administración de Microsoft 365

Las licencias a nivel de usuario de Teams se administran directamente a través de las interfaces de administración de usuarios Centro de administración de Microsoft 365. Un administrador puede asignar licencias a nuevos usuarios al crear cuentas de usuario, así como a los usuarios con cuentas existentes.

> [!IMPORTANT]
> El administrador debe tener privilegios de administrador global o administrador de administración de usuarios para administrar las licencias de Microsoft Teams.
Use la Centro de administración de Microsoft 365 para administrar las licencias de Teams para usuarios individuales o conjuntos pequeños de usuarios a la vez. Puede administrar las licencias de Teams en la página **Licencias** (para un máximo de 20 usuarios a la vez) o en la página **Usuarios activos** . El método que elija dependerá de si desea administrar licencias de producto para usuarios específicos o administrar licencias de usuario de productos específicos.

Si necesita administrar licencias de Teams para un gran número de usuarios, como cientos o miles de usuarios, [use PowerShell](#using-powershell) o [licencias basadas en grupos en Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Asignar una licencia de Teams

Los pasos son diferentes dependiendo de si usa la página **Licencias** o la página **Usuarios activos** .  Para obtener instrucciones detalladas, consulte [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Captura de pantalla 1 de licencia de Teams habilitada para un usuario.](media/assign-teams-licenses-1.png)    | ![Captura de pantalla 2 de licencia de Teams habilitada para un usuario](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Quitar una licencia de Teams

> [!IMPORTANT]
> Deshabilitar una SKU de Teams tarda aproximadamente 24 horas en surtir efecto.

Al quitar una licencia de Teams de un usuario, Teams se deshabilita para ese usuario y ya no verá Teams en la página principal o en el iniciador de aplicaciones. Para conocer los pasos [detallados, consulte Anular la asignación de licencias de usuarios](/microsoft-365/admin/manage/remove-licenses-from-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Captura de pantalla 1 de la licencia de Teams deshabilitada para un usuario.](media/remove-teams-licenses-1.png)    | ![Captura de pantalla 2 de la licencia de Teams deshabilitada para un usuario](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Con PowerShell

Use PowerShell para administrar las licencias de Teams para los usuarios en masa. Puede habilitar y deshabilitar Teams a través de PowerShell del mismo modo que lo haría con cualquier otra licencia del plan de servicio. Necesitará los identificadores de los planes de servicio para Teams, que son los siguientes:

- Microsoft Teams: TEAMS1
- Microsoft Teams para GCC: TEAMS_GOV
- Microsoft Teams para DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Asignar licencias de Teams en masa

Para conocer los pasos [detallados, consulte Asignar licencias a cuentas de usuario con PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Quitar licencias de Teams en masa

Para conocer los pasos detallados, consulte [Deshabilitar el acceso a los servicios con PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) y [Deshabilitar el acceso a los servicios al asignar licencias de usuario](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Ejemplo 

El siguiente es un ejemplo de cómo usar los [cmdlets New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) y [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) para deshabilitar Teams para los usuarios que tienen un plan de licencia específico. Por ejemplo, siga estos pasos para deshabilitar primero Teams para todos los usuarios que tienen un plan de licencia determinado. Después, habilite Teams para cada usuario individual que tenga acceso a Teams.

> [!IMPORTANT]
> El cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) habilitará todos los servicios que se deshabilitaron anteriormente a menos que se identifiquen explícitamente en el script personalizado. Por ejemplo, si desea dejar Tanto Exchange como Sway deshabilitados mientras deshabilita Teams, tendrá que incluirlo en el script o exchange y Sway se habilitarán para los usuarios que haya identificado.

Ejecute el siguiente comando para mostrar todos los planes de licencia disponibles en su organización. Para obtener más información, consulte [Ver licencias y servicios con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).


```powershell
Get-MsolAccountSku
```

Ejecute los siguientes comandos, donde \<CompanyName:License> se encuentra el nombre de su organización y el identificador del plan de licencias que ha recuperado en el paso anterior. Por ejemplo, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Ejecute el siguiente comando para deshabilitar Teams para todos los usuarios que tengan una licencia activa para el plan de licencias.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Temas relacionados

- [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Asignar licencias de complementos de Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Ver licencias y servicios con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referencia de SKU para educación](sku-reference-edu.md)
