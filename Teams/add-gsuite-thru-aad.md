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
description: Obtenga información sobre cómo configurar el complemento de reuniones de Microsoft Teams para Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387311"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurar el complemento de reunión de Microsoft Teams para Google Workspace

El complemento de reuniones de Microsoft Teams permite a los usuarios de Google Calendar programar y unirse a una reunión de Microsoft Teams directamente desde Google Workspace. Los usuarios obtendrán acceso a las características de reuniones de Teams, incluidas las conferencias de audio y vídeo, la pantalla compartida, la conversación de reuniones, las pizarras digitales y mucho más. Mantente conectado y organizado para hacer más cosas juntos en el trabajo, la escuela y la vida.

El complemento de reunión de Microsoft Teams para Google Workspace debe estar habilitado por un administrador de equipo antes de que los usuarios inquilinos puedan acceder a la aplicación.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Habilitar o deshabilitar el complemento de reunión de Microsoft Teams para Google Workspace en el portal de Azure

Como administrador de inquilinos, puede habilitar o deshabilitar un complemento de reunión de Microsoft Teams para Google Workspace desde la cuenta de administrador de su organización mediante el portal de Azure.

El complemento está habilitado de forma predeterminada.

1. Inicie sesión en el portal de Azure.

2. Seleccione **aplicaciones empresariales**  >  **todas las aplicaciones**.

3. Busque **el complemento de reunión de Microsoft Teams para Google Workspace**.

   ![Portal de Azure que muestra todas las aplicaciones](media/aad-add-google-workspace.png)

4. Seleccione **sí**.

   ![Portal de Azure que muestra las propiedades de Google Workspace](media/google-workspace-properties.png)

5. Faculta Para deshabilitar el complemento, seleccione **no** en lugar de **sí** en el paso 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Deshabilitar el complemento de reuniones de Microsoft Teams para Google Workspace con PowerShell

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

Para obtener más información, vea [crear una entidad de servicio de Azure con Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Eliminar el complemento de reunión de Microsoft Teams para Google Workspace

Consulte la documentación [eliminar una aplicación Google Workspace del área de trabajo](https://support.google.com/a/answer/6216211?hl=en) para obtener instrucciones.
