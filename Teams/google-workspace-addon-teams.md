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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="e44b2-103">Configurar un Microsoft Teams de reunión para Google Workspace</span><span class="sxs-lookup"><span data-stu-id="e44b2-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="e44b2-104">Usar el complemento Microsoft Teams reunión permite a los usuarios del calendario de Google programar y unirse a una reunión Microsoft Teams directamente desde Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="e44b2-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="e44b2-105">Los usuarios tendrán acceso Teams de reuniones, como videoconferencias y audioconferencias, uso compartido de pantalla, chat de reunión, pizarras digitales y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e44b2-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="e44b2-106">Manténgase conectado y organizado para trabajar más juntos en el trabajo, la escuela y la vida.</span><span class="sxs-lookup"><span data-stu-id="e44b2-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="e44b2-107">El Microsoft Teams de reunión de Google Workspace debe estar habilitado por un administrador de Teams para que los usuarios inquilinos puedan acceder a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e44b2-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="e44b2-108">Habilitar o deshabilitar Microsoft Teams complemento de reunión de Google Workspace en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="e44b2-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="e44b2-109">Como administrador de inquilinos, puede habilitar o deshabilitar un complemento de reunión de Microsoft Teams para Google Workspace desde la cuenta de administrador de su organización con Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="e44b2-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="e44b2-110">El complemento está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e44b2-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="e44b2-111">Inicie sesión en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="e44b2-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="e44b2-112">Seleccione **Enterprise todas las**  >  **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e44b2-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="e44b2-113">Busque el **Microsoft Teams reunión de Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="e44b2-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Azure Portal que muestra todas las aplicaciones](media/aad-add-google-workspace.png)

4. <span data-ttu-id="e44b2-115">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e44b2-115">Select **Yes**.</span></span>

   ![Azure Portal que muestra las propiedades del área de trabajo de Google](media/google-workspace-properties.png)

5. <span data-ttu-id="e44b2-117">(Opcional) Para deshabilitar el complemento, seleccione **No** en lugar de **Sí** en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="e44b2-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="e44b2-118">Deshabilitar Microsoft Teams de reunión de Google Workspace con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e44b2-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="e44b2-119">Para obtener más información, vea Crear una entidad de [servicio de Azure con Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="e44b2-119">For more information, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="e44b2-120">Eliminar el complemento Microsoft Teams reunión de Google Workspace</span><span class="sxs-lookup"><span data-stu-id="e44b2-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="e44b2-121">Consulte la documentación de Google [Eliminar una aplicación de Google Workspace Marketplace para](https://support.google.com/a/answer/6216211?hl=en) obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="e44b2-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>