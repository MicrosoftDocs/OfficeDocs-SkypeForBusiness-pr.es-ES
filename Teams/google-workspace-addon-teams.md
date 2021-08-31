---
title: Configurar un Microsoft Teams de reunión para Google Workspace
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
description: Obtenga información sobre cómo configurar Microsoft Teams complemento de reunión para Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb5f7574bd5e07598c412cd7d17f02625de2f095
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729919"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurar un Microsoft Teams de reunión para Google Workspace

Usar el complemento Microsoft Teams reunión permite a los usuarios del calendario de Google programar y unirse a una reunión Microsoft Teams directamente desde Google Workspace. Los usuarios tendrán acceso Teams de reuniones, como videoconferencias y audioconferencias, uso compartido de pantalla, chat de reunión, pizarras digitales y mucho más. Manténgase conectado y organizado para trabajar más juntos en el trabajo, la escuela y la vida.

El Microsoft Teams de reunión de Google Workspace debe estar habilitado por un administrador de Teams para que los usuarios inquilinos puedan acceder a la aplicación.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Habilitar o deshabilitar Microsoft Teams complemento de reunión de Google Workspace en Azure Portal

Como administrador de inquilinos, puede habilitar o deshabilitar un complemento de reunión de Microsoft Teams para Google Workspace desde la cuenta de administrador de su organización con Azure Portal.

El complemento está habilitado de forma predeterminada.

1. Inicie sesión en Azure Portal.

2. Seleccione **Enterprise todas las**  >  **aplicaciones**.

3. Busque el **Microsoft Teams reunión de Google Workspace.**

   ![Azure Portal que muestra todas las aplicaciones.](media/aad-add-google-workspace.png)

4. Seleccione **Sí**.

   ![Azure Portal que muestra las propiedades del área de trabajo de Google.](media/google-workspace-properties.png)

5. (Opcional) Para deshabilitar el complemento, seleccione **No** en lugar de **Sí** en el paso 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deshabilitar Microsoft Teams de reunión de Google Workspace con PowerShell

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

Para obtener más información, vea Crear una entidad de [servicio de Azure con Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminar el complemento Microsoft Teams reunión de Google Workspace

Consulte la documentación de Google [Eliminar una aplicación de Google Workspace Marketplace para](https://support.google.com/a/answer/6216211?hl=en) obtener instrucciones.