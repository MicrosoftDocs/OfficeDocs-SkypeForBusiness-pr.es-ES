---
title: Gestionar acceso de los usuarios a Microsoft Teams
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
ms.openlocfilehash: 83d2b0710b811431546f0df9931d3a0b867d2b2b
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "30683887"
---
<a name="manage-user-access-to-microsoft-teams"></a>Gestionar acceso de los usuarios a Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

En el nivel de usuario, acceso a Microsoft Teams puede habilitar o deshabilitar por usuario mediante la asignación o la eliminación de la licencia del producto Microsoft Teams.

Use las directivas de mensajería, administradas desde el centro de administración de equipos, para controlar qué chat y canal de características de mensajería están disponibles para los usuarios en los equipos. Puede usar la directiva predeterminada o crear una o varias directivas de mensajería personalizadas para las personas de su organización. Para obtener más información, lea [Administrar directivas de mensajería en los equipos](messaging-policies-in-teams.md).

> [!NOTE]
>Microsoft recomienda activar en los equipos de todos los usuarios de una compañía para que los equipos se pueden formar ecológicamente para proyectos y otras iniciativas dinámicos. Incluso si se decide piloto, puede ser útil para mantener los equipos habilitados para todos los usuarios, pero sólo communications para el grupo piloto de usuarios de destino.

## <a name="manage-teams-through-the-office-365-admin-center"></a>Administrar los equipos a través del centro de administración de Office 365

Licencias de nivel de usuario de los equipos se administran directamente a través de las interfaces de administración de usuario de Office 365 admin center. Un administrador puede asignar licencias a los nuevos usuarios cuando se crean nuevas cuentas de usuario o a los usuarios con cuentas existentes. El administrador debe tener privilegios de administrador Global de Office 365 o administrador de usuario para administrar las licencias de Microsoft Teams.

Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Una licencia de usuario de los equipos se puede deshabilitar en cualquier momento. Una vez que la licencia está deshabilitada, se impedirá el acceso de usuarios a Microsoft Teams y el usuario ya no podrán ver los equipos en la página principal y del iniciador de aplicación de Office 365.

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365, donde se ve Microsoft Teams seleccionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Administrar a través de PowerShell

> [!IMPORTANT]
> Nuevo MsolLicenseOptions permitirá a todos los servicios que estaban deshabilitados a menos que explictitly identitied en la secuencia de comandos personalizada. Por ejemplo, si deseara deje ambos & Exchange balanceo deshabilitado mientras además deshabilitar los equipos, necesitará incluya esto en la secuencia de comandos o ambos & Exchange balanceo se habilitará para aquellos usuarios que ha identificado. Si desea utilizar una interfaz gráfica de usuario para administrar esta funcionalidad, vea: [informes de licencia de Office 365 y la herramienta de administración-asignar licencias de quitar de forma masiva](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo. El nombre del plan de servicio es TEAMS1 para Microsoft Teams. GCC el nombre del plan de servicio es TEAMS_GOV. Para GCC alta el nombre del plan de servicio es TEAMS_GCCHIGH. DoD el nombre del plan de servicio es TEAMS_DOD (Véase [Deshabilitar acceso a los servicios con PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información.)

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
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Siguientes pasos         |<ul><li>Si incorporación mediante una prueba piloto cerrada, decida si desea hacerlo a través de licencias, o dirigidas comunicación.</li><li>Dependiendo de la toma de decisiones, realice los pasos para asegurarse de que sólo los usuarios que tienen acceso los equipos (si es necesario) la prueba piloto.</li><li>Las instrucciones para que los usuarios que va a (o no) de documentos tienen acceso a los equipos.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Administrar los equipos en el nivel de inquilino de Office 365
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

