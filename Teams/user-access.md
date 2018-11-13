---
title: Gestionar acceso de los usuarios a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1f73a709ae6235859cbdccab493d8fa6d198823
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294964"
---
<a name="manage-user-access-to-microsoft-teams"></a>Gestionar acceso de los usuarios a Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

En el nivel de usuario, acceso a Microsoft Teams puede habilitar o deshabilitar por usuario mediante la asignación o la eliminación de la licencia del producto Microsoft Teams.

Actualmente, no hay ninguna opción de directiva para activar los equipos o un subconjunto de las características de los equipos, o desactivar en un nivel de usuario individual fuera de licencias.

> [!NOTE]
>Microsoft recomienda activar en los equipos de todos los usuarios de una compañía para que los equipos se pueden formar ecológicamente para proyectos y otras iniciativas dinámicos. Incluso si se decide piloto, puede ser útil para mantener los equipos habilitados para todos los usuarios, pero sólo communications para el grupo piloto de usuarios de destino.

## <a name="manage-teams-through-the-office-365-admin-center"></a>Administrar los equipos a través del centro de administración de Office 365

Licencias de nivel de usuario de los equipos se administran directamente a través de las interfaces de administración de usuario de Office 365 admin center. Un administrador puede asignar licencias a los nuevos usuarios cuando se crean nuevas cuentas de usuario o a los usuarios con cuentas existentes. El administrador debe tener privilegios de administrador Global de Office 365 o administrador de usuario para administrar las licencias de Microsoft Teams.

Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Una licencia de usuario de los equipos se puede deshabilitar en cualquier momento. Una vez que la licencia está deshabilitada, se impedirá el acceso de usuarios a Microsoft Teams y el usuario ya no podrán ver los equipos en la página principal y del iniciador de aplicación de Office 365.

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365, donde se ve Microsoft Teams seleccionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Administrar a través de PowerShell

Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo. El nombre del plan de servicio es TEAMS1 para Microsoft Teams. Para organizaciones de gobierno, el nombre del plan de servicio es TEAMS_GOV. (Consulte [Deshabilitar el acceso a los servicios con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información).

**Ejemplo:** El siguiente es sólo un ejemplo rápido en cómo sería deshabilitar los equipos de todos los miembros de un tipo de licencia determinado. Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.

Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:

      Get-MsolAccountSku

Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Para deshabilitar los equipos de todos los usuarios con una licencia de activo para el plan con nombre, ejecute el siguiente comando:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Punto de decisión         |<ul><li>¿Qué es la planeación de la organización de la incorporación de los equipos en toda la organización?  (Piloto o abrir)</li></ul>         |
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Siguientes pasos         |<ul><li>Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</li><li>Dependiendo de la toma de decisiones, realice los pasos para asegurarse de que sólo los usuarios que tienen acceso los equipos (si es necesario) la prueba piloto.</li><li>Las instrucciones para que los usuarios que va a (o no) de documentos tienen acceso a los equipos.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Administrar los equipos en el nivel de inquilino de Office 365
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

