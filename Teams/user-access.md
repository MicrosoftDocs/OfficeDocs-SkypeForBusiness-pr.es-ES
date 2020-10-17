---
title: Administrar el acceso de los usuarios a Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a administrar el acceso de los usuarios a los equipos asignando o quitando una licencia de Teams a los usuarios de su organización.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521387"
---
# <a name="manage-user-access-to-teams"></a>Gestionar acceso de los usuarios a Microsoft Teams

Para administrar el acceso a los equipos en el nivel de usuario, asigne o quite una licencia de producto de Microsoft Teams. Cada usuario de su organización debe tener una licencia de Teams para poder usar Teams. Puede asignar una licencia de Teams a los nuevos usuarios cuando se crean nuevas cuentas de usuario o a los usuarios con cuentas existentes.

De forma predeterminada, cuando un plan de licencias (por ejemplo, Microsoft 365 Enterprise E3 o Microsoft 365 Business Premium) se asigna a un usuario, se asigna automáticamente una licencia de Teams y el usuario habilita Teams. Puede deshabilitar o habilitar Teams para un usuario si quita o asigna una licencia en cualquier momento.

Use directivas de mensajería, administradas desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de equipos</a>, para controlar las características de mensajería instantánea y de canales disponibles para los usuarios en Teams. Puede usar la directiva predeterminada o bien crear una o más directivas de mensajería personalizadas para los miembros de su organización. Para obtener más información, lea [Administrar directivas de mensajería en Teams](messaging-policies-in-teams.md).
Administra las licencias de Teams en el centro de administración de Microsoft 365 o mediante PowerShell. Para administrar las licencias, debe ser administrador global o administrador de administración de usuarios.

> [!NOTE]
> Le recomendamos que habilite Teams para todos los usuarios, de modo que se puedan formar orgánicamente para proyectos y otras iniciativas dinámicas. Incluso si está ejecutando un proyecto piloto, puede que le resulte útil mantener equipos habilitados para todos los usuarios, pero solo las comunicaciones dirigidas al grupo piloto de usuarios.

## <a name="using-the-microsoft-365-admin-center"></a>Usar el centro de administración de Microsoft 365

Las licencias de nivel de usuario de Teams se administran directamente a través de las interfaces de administración de usuarios del centro de administración de Microsoft 365. Un administrador puede asignar licencias a nuevos usuarios al crear cuentas de usuario, así como a los usuarios con cuentas existentes. 

> [!IMPORTANT]
> El administrador debe tener privilegios de administrador global o de administrador de administración de usuarios para administrar las licencias de Microsoft Teams.
Use el centro de administración de Microsoft 365 para administrar licencias de Teams para usuarios individuales o conjuntos pequeños de usuarios a la vez. Puede administrar las licencias de Teams en la página **licencias** (para un máximo de 20 usuarios a la vez) o en la página **usuarios activos** . El método que elija dependerá de si desea administrar las licencias de producto para usuarios específicos o administrar licencias de usuario para productos específicos.

Si necesita administrar licencias de Teams para un gran número de usuarios, como cientos o miles de usuarios, [use PowerShell](#using-powershell) o [licencias basadas en grupos en Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Asignar una licencia de Teams

Los pasos son diferentes dependiendo de si usa la página **licencias** o la página **usuarios activos** .  Para obtener instrucciones paso a paso, vea [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

|||
|---------|---------|
|![Captura de pantalla de la licencia de Teams habilitada para un usuario](media/assign-teams-licenses-1.png)    | ![Captura de pantalla de la licencia de Teams habilitada para un usuario](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Quitar una licencia de Teams

Cuando quita una licencia de Teams de un usuario, Teams está deshabilitado para ese usuario y ya no verá equipos en el iniciador de aplicaciones o en la Página principal. Para conocer los pasos detallados, vea [cancelar la asignación de licencias de usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).

|||
|---------|---------|
|![Captura de pantalla de la licencia de Teams deshabilitada para un usuario](media/remove-teams-licenses-1.png)    | ![Captura de pantalla de la licencia de Teams deshabilitada para un usuario](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Con PowerShell

Usar PowerShell para administrar licencias de Teams para usuarios en bloque. Habilite y deshabilite Teams mediante PowerShell de la misma manera en que lo haría para cualquier otra licencia de plan de servicio. Necesitará los identificadores de los planes de servicio para Teams, que son los siguientes:

- Microsoft Teams: TEAMS1
- Microsoft Teams para GCC: TEAMS_GOV
- Microsoft Teams para DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Asignar licencias de Teams en masa

Para conocer los pasos detallados, vea [asignar licencias a cuentas de usuario con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Quitar licencias de Teams en masa

Para conocer los pasos detallados, vea [deshabilitar el acceso a servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) y [deshabilitar el acceso a servicios al asignar licencias de usuario](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Ejemplo 

A continuación se describe un ejemplo de cómo usar los cmdlets [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) y [set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) para deshabilitar Teams para los usuarios que tienen un plan de licencias específico. Por ejemplo, siga estos pasos para deshabilitar primero Teams para todos los usuarios que tengan un plan de licencias determinado. A continuación, habilite Teams para cada usuario individual que debería tener acceso a teams.

> [!IMPORTANT]
> El cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) habilitará todos los servicios que se hayan deshabilitado anteriormente, a menos que se identifiquen explícitamente en el script personalizado. Por ejemplo, si desea dejar Exchange y Sway deshabilitados, y deshabilitar también Teams, tendrá que incluirlos en la secuencia de comandos o Exchange y Sway estarán habilitados para los usuarios que haya identificado.

Ejecute el siguiente comando para mostrar todos los planes de licencias disponibles en su organización. Para obtener más información, vea [ver licencias y servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).

      Get-MsolAccountSku

Ejecute los siguientes comandos, donde \<CompanyName:License> es el nombre de su organización y el identificador del plan de licencias que recuperó en el paso anterior. Por ejemplo, ContosoSchool: ENTERPRISEPACK_STUDENT.

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

Ejecute el siguiente comando para deshabilitar Teams para todos los usuarios que tienen una licencia activa para el plan de licencias.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>Administrar equipos en el nivel de la organización

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>Temas relacionados

- [Licencias de complementos de Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Asignar licencias de complementos de Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Ver licencias y servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referencia de SKU de educación](sku-reference-edu.md)