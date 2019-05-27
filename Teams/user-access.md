---
title: Administrar el acceso de los usuarios a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e61a4456d926c8d939769e49968a79943c1138b4
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433282"
---
<a name="manage-user-access-to-microsoft-teams"></a>Administrar el acceso de los usuarios a Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

A nivel de usuario, el acceso a Microsoft Teams puede habilitarse o deshabilitarse por usuario, asignando o quitando la licencia de producto de Microsoft Teams.

Use las directivas de mensajería, que se controlan desde el centro de administración de Teams, para controlar qué características de mensajería y canales están disponibles para los usuarios en Teams. Puede usar la directiva predeterminada o bien crear una o más directivas de mensajería personalizadas para los miembros de su organización. Para obtener más información, lea [Administrar directivas de mensajería en Teams](messaging-policies-in-teams.md).

> [!NOTE]
>Microsoft recomienda que Teams se habilite para todos los usuarios de una empresa, de modo que los equipos puedan formarse de manera orgánica para proyectos y otras iniciativas dinámicas. Incluso si decide realizar un piloto, podría ser útil mantener Teams habilitado para todos los usuarios, pero solo enfocarse en las comunicaciones con el grupo piloto de usuarios.

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>Administrar equipos a través del centro de administración de Microsoft 365

Las licencias de nivel de usuario de Teams se administran directamente a través de las interfaces de administración de usuarios del centro de administración de Microsoft 365. Un administrador puede asignar licencias a nuevos usuarios al crear cuentas de usuario, así como a los usuarios con cuentas existentes. El administrador debe tener privilegios de Administrador global de Office 365 o de Administración de usuarios para administrar las licencias de Microsoft Teams.

Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Las licencias de usuario de Teams se pueden deshabilitar en cualquier momento. Una vez que la licencia se deshabilita, se evitará el acceso de los usuarios a Microsoft Teams y el usuario ya no podrá ver Teams en el iniciador de aplicaciones y la página de inicio de Office 365.

![Captura de pantalla que muestra equipos seleccionados en la sección licencias de producto.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Administrar mediante PowerShell

> [!IMPORTANT]
> New-MsolLicenseOptions habilitará todos los servicios que estaban deshabilitados a menos que se especifiquen explícitamente en el script personalizado. Por ejemplo, si quiere dejar Exchange y Sway deshabilitados mientras a la vez que deshabilita Teams, tendría que incluir esto en el script o tanto Exchange como Sway se habilitarán para los usuarios que ha identificado. Si quiere, puede utilizar una GUI para administrar esta funcionalidad, consulte: [Informes de licencia de Office 365 y herramienta de administración: asignar o quitar licencias de forma masiva](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo. El nombre del plan de servicio es TEAMS1 para Microsoft Teams. Para GCC el nombre del plan de servicio es TEAMS_GOV. Para GCC High el nombre del plan de servicio es TEAMS_GCCHIGH. Para DoD el nombre del plan de servicio es TEAMS_DOD (consulte [Deshabilitar el acceso a servicios con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información).

**Muestra:** a continuación encontrará una muestra rápida de cómo se deshabilita Teams para todos los miembros en un tipo de licencia particular. Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.

Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:

      Get-MsolAccountSku

Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Para deshabilitar Teams para todos los usuarios que tengan una licencia activa para su plan, ejecute el siguiente comando:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Punto de decisión         |<ul><li>¿Cuál es el plan de su organización para comenzar a usar Teams en toda la organización?  (Piloto o abierto)</li></ul>         |
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Siguientes pasos         |<ul><li>Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</li><li>Según su decisión, realice los pasos para asegurarse de que solo los usuarios piloto puedan acceder a Teams (si es necesario).</li><li>Documente qué usuarios tendrán (o no tendrán) acceso a Teams.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Administrar Teams en el nivel de espacio empresarial de Office 365
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

