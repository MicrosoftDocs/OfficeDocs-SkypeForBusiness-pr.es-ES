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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="09b7a-103">Configurar el complemento de reunión de Microsoft Teams para Google Workspace</span><span class="sxs-lookup"><span data-stu-id="09b7a-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="09b7a-104">El complemento de reuniones de Microsoft Teams permite a los usuarios de Google Calendar programar y unirse a una reunión de Microsoft Teams directamente desde Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="09b7a-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="09b7a-105">Los usuarios obtendrán acceso a las características de reuniones de Teams, incluidas las conferencias de audio y vídeo, la pantalla compartida, la conversación de reuniones, las pizarras digitales y mucho más.</span><span class="sxs-lookup"><span data-stu-id="09b7a-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="09b7a-106">Mantente conectado y organizado para hacer más cosas juntos en el trabajo, la escuela y la vida.</span><span class="sxs-lookup"><span data-stu-id="09b7a-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="09b7a-107">El complemento de reunión de Microsoft Teams para Google Workspace debe estar habilitado por un administrador de equipo antes de que los usuarios inquilinos puedan acceder a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09b7a-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="09b7a-108">Habilitar o deshabilitar el complemento de reunión de Microsoft Teams para Google Workspace en el portal de Azure</span><span class="sxs-lookup"><span data-stu-id="09b7a-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="09b7a-109">Como administrador de inquilinos, puede habilitar o deshabilitar un complemento de reunión de Microsoft Teams para Google Workspace desde la cuenta de administrador de su organización mediante el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="09b7a-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="09b7a-110">El complemento está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="09b7a-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="09b7a-111">Inicie sesión en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="09b7a-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="09b7a-112">Seleccione **aplicaciones empresariales**  >  **todas las aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="09b7a-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="09b7a-113">Busque **el complemento de reunión de Microsoft Teams para Google Workspace**.</span><span class="sxs-lookup"><span data-stu-id="09b7a-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Portal de Azure que muestra todas las aplicaciones](media/aad-add-google-workspace.png)

4. <span data-ttu-id="09b7a-115">Seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="09b7a-115">Select **Yes**.</span></span>

   ![Portal de Azure que muestra las propiedades de Google Workspace](media/google-workspace-properties.png)

5. <span data-ttu-id="09b7a-117">Faculta Para deshabilitar el complemento, seleccione **no** en lugar de **sí** en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="09b7a-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="09b7a-118">Deshabilitar el complemento de reuniones de Microsoft Teams para Google Workspace con PowerShell</span><span class="sxs-lookup"><span data-stu-id="09b7a-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="09b7a-119">Para obtener más información, vea [crear una entidad de servicio de Azure con Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="09b7a-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="09b7a-120">Eliminar el complemento de reunión de Microsoft Teams para Google Workspace</span><span class="sxs-lookup"><span data-stu-id="09b7a-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="09b7a-121">Consulte la documentación [eliminar una aplicación Google Workspace del área de trabajo](https://support.google.com/a/answer/6216211?hl=en) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="09b7a-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
