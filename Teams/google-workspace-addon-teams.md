---
title: Configurar el complemento de reunión de Microsoft Teams para Google Workspace
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Obtenga información sobre cómo configurar el complemento de reunión de Microsoft Teams para Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120701"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurar el complemento de reunión de Microsoft Teams para Google Workspace

El uso del complemento de reunión de Microsoft Teams permite a los usuarios del calendario de Google programar y unirse a una reunión de Microsoft Teams directamente desde Google Workspace. Los usuarios tendrán acceso a las características de reuniones de Teams, como videoconferencias y audioconferencias, uso compartido de pantalla, chat de reunión, pizarras digitales y mucho más. Manténgase conectado y organizado para trabajar más juntos en el trabajo, la escuela y la vida.

El complemento de reunión de Microsoft Teams para Google Workspace debe estar habilitado por un administrador de Teams para que los usuarios inquilinos puedan acceder a la aplicación.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Habilitar o deshabilitar el complemento de reunión de Microsoft Teams para Google Workspace en Azure Portal

Como administrador de inquilinos, puede habilitar o deshabilitar un complemento de reunión de Microsoft Teams para Google Workspace desde la cuenta de administrador de su organización con Azure Portal.

El complemento está habilitado de forma predeterminada.

1. Inicie sesión en Azure Portal.

2. Seleccione **Aplicaciones**  >  **empresariales Todas las aplicaciones**.

3. Busque el **complemento de reunión de Microsoft Teams para Google Workspace.**

   ![Azure Portal que muestra todas las aplicaciones](media/aad-add-google-workspace.png)

4. Seleccione **Sí**.

   ![Azure Portal que muestra las propiedades del área de trabajo de Google](media/google-workspace-properties.png)

5. (Opcional) Para deshabilitar el complemento, seleccione **No** en lugar de **Sí** en el paso 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deshabilitar el complemento de reunión de Microsoft Teams para Google Workspace con PowerShell

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
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Para obtener más información, vea Crear una entidad de [servicio de Azure con Azure PowerShell.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminar el complemento de reunión de Microsoft Teams para Google Workspace

Consulte la documentación de Google [Eliminar una aplicación de Google Workspace Marketplace para](https://support.google.com/a/answer/6216211?hl=en) obtener instrucciones.