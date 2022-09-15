---
title: Configurar el complemento para reuniones de Microsoft Teams para Google Workspace
ms.author: mabond
author: mkbond007
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Obtenga información sobre cómo configurar el complemento para reuniones de Microsoft Teams para Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd6897b770215af75862438996a365acd463c96
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706647"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurar el complemento para reuniones de Microsoft Teams para Google Workspace

El uso del complemento para reuniones de Microsoft Teams permite a los usuarios del calendario de Google programar y unirse a una reunión de Microsoft Teams directamente desde Google Workspace. Los usuarios obtendrán acceso a las características de reuniones de Teams, incluidas las videoconferencias y audioconferencias, el uso compartido de la pantalla, el chat de reuniones, las pizarras digitales y mucho más. Manténgase conectado y organizado para hacer más cosas juntos en el trabajo, la escuela y la vida.

El complemento para la reunión de Microsoft Teams para Google Workspace debe estar habilitado por un administrador de Teams antes de que los usuarios del inquilino puedan acceder a la aplicación.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Habilite o deshabilite el complemento para reuniones de Microsoft Teams para Google Workspace en la Azure Portal

Como administrador de inquilinos, puede habilitar o deshabilitar un complemento de reunión de Microsoft Teams para Google Workspace desde la cuenta de administrador de su organización mediante la Azure Portal.

El complemento está habilitado de forma predeterminada.

1. Inicia sesión en la Azure Portal.

2. Seleccione **Aplicaciones** >  empresariales **Todas las aplicaciones**.

3. Busque **el complemento para reuniones de Microsoft Teams para Google Workspace**.

   ![Azure Portal que muestran todas las aplicaciones.](media/aad-add-google-workspace.png)

4. Seleccione **Sí**.

   ![Azure Portal que muestran las propiedades del área de trabajo de Google.](media/google-workspace-properties.png)

5. (Opcional) Para deshabilitar el complemento, seleccione **No** en lugar de **Sí** en el paso 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deshabilitar el complemento para reuniones de Microsoft Teams para Google Workspace con PowerShell

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Para obtener más información, vea [Crear una entidad de servicio de Azure con Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminar el complemento de reunión de Microsoft Teams para Google Workspace

Consulta la documentación de Google [Eliminar una aplicación de Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) para obtener instrucciones.

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Crear el complemento de reunión de Microsoft Teams para Google Workspace con PowerShell

En caso de que el complemento para la reunión de Microsoft Teams no esté presente en su inquilino, puede crearlo con PowerShell: 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
