---
title: Gestionar acceso de los usuarios a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Aprenda a habilitar o deshabilitar el acceso a nivel de usuario por cada usuario.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a>Gestionar acceso de los usuarios a Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

En el nivel de usuario, acceso a Teams de Microsoft puede habilitar o deshabilitar en cada usuario asignar o quitando la licencia del producto Microsoft Teams.

Actualmente, no hay ninguna opción de directiva para activar equipos o un subconjunto de características de los equipos, o desactivar en un nivel de usuario individual fuera de licencias.

> [!NOTE]
>Microsoft recomienda activar equipos para todos los usuarios de una empresa para que los equipos se pueden formar orgánicamente para proyectos y otras iniciativas dinámicas. Incluso si decide a piloto, puede ser útil mantener equipos habilitados para todos los usuarios, pero sólo comunicaciones con el grupo piloto de usuarios de destino.

## <a name="manage-directly-through-the-office-365-admin-center"></a>Administrar directamente a través del centro de administración de Office 365

Licencias de nivel de usuario de los equipos se administran directamente a través de las interfaces de administración de Office 365 admin center usuario. Un administrador puede asignar licencias a nuevos usuarios cuando se crean nuevas cuentas de usuario o los usuarios con cuentas existentes. El administrador debe tener privilegios de administrador del usuario o de administrador Global de Office 365 para administrar las licencias de Microsoft Teams.

Cuando una SKU de licencia como E3 o E5 se asigna a un usuario, automáticamente se asigna una licencia de Microsoft Teams y el usuario queda habilitado para Microsoft Teams. Los administradores pueden tener un control granular de todos los servicios y las licencias de Office 365, y la licencia de Microsoft Teams para un usuario específico o un grupo de usuarios puede habilitarse o deshabilitarse.

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Una licencia de usuario de equipos puede desactivarse en cualquier momento. Una vez que la licencia se deshabilita, se impedirá el acceso de los usuarios a Teams de Microsoft y el usuario ya no podrá ver los equipos en la página principal y el iniciador de la aplicación de Office 365.

![Captura de pantalla de la sección Licencias de productos en el Centro de administración de Office 365, donde se ve Microsoft Teams seleccionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Gestionar a través de PowerShell

Para habilitar y deshabilitar Teams como licencia de carga de trabajo mediante PowerShell se sigue el mismo procedimiento que con cualquier otra carga de trabajo. El nombre del plan de servicio es TEAMS1 para Microsoft Teams. (Consulte [Deshabilitar el acceso a los servicios con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obtener más información).

**Ejemplo:** A continuación es sólo una muestra rápida sobre cómo deshabilitaría equipos para todos los miembros de un tipo de licencia particular. Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.

Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:

      Get-MsolAccountSku

Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Para deshabilitar los equipos para todos los usuarios con una licencia activa para su plan con nombre, ejecute el siguiente comando:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Punto de decisión         |<ul><li>¿Cuál es el plan de la organización para la incorporación de equipos en toda la organización?  (Prueba piloto o abrir)</li></ul>         |
|![Icono de Siguientes pasos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Siguientes pasos         |<ul><li>Si realiza la adopción a través de Piloto, decida si desea hacerlo a través de licencias o comunicación dirigida.</li><li>Dependiendo de la decisión, tome pasos para asegurarse de que sólo los usuarios autorizados para tener acceso a los equipos (si es necesario) del piloto.</li><li>Documentar las directrices para que los usuarios que serán (o no) tener acceso a los equipos.</li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a>Gestionar a través de interruptor del nivel del Sku de Office
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  Inicie sesión en el [Centro de administración de Office 365](https://go.microsoft.com/fwlink/?linkid=854614) con una cuenta que tenga privilegios de administrador global.

2.  Vaya a **Configuración** > **Servicios y complementos**.

    ![Captura de pantalla de la sección Configuración del Centro de administración de Office 365 con Servicios y complementos seleccionado. ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  En la página Servicios y complementos, haga clic en **Microsoft Teams**.

    ![Captura de pantalla de la página Servicios y complementos con Microsoft Teams seleccionado.](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  Para activar Teams para la organización, use el selector de licencias, seleccione cada licencia, después establezca el botón de alternancia en **Activado** y finalmente haga clic en **Guardar**.

    ![Captura de pantalla de la página de configuración de Microsoft Teams donde se ve el botón de alternancia establecido en Activado para habilitar Microsoft Teams.](media/Services-and-addins-control-Microsoft-Teams.PNG)
