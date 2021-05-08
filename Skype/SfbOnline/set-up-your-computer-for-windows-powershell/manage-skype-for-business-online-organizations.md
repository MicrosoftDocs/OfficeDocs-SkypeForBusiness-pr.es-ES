---
title: Administrar Skype Empresarial en línea
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su Skype Empresarial en línea.
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238790"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="a7c15-103">Administrar Skype Empresarial en línea</span><span class="sxs-lookup"><span data-stu-id="a7c15-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="a7c15-104">La versión Teams versión preliminar pública de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) se integra con Skype Empresarial Online Connector, lo que proporciona un único módulo para Teams administración de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7c15-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="a7c15-105">Puede encontrar información sobre su espacio empresarial Skype Empresarial Online mediante los **cmdlets Get-CsTenant** y **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a7c15-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="a7c15-106">Administrar Skype Empresarial en línea</span><span class="sxs-lookup"><span data-stu-id="a7c15-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="a7c15-107">Para devolver información sobre su espacio empresarial Skype Empresarial online, llame al cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="a7c15-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="a7c15-108">Para devolver solo el nombre del inquilino y el identificador, use este comando.</span><span class="sxs-lookup"><span data-stu-id="a7c15-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="a7c15-109">El valor del parámetro _TenantID_ es necesario al ejecutar cmdlets como [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) y [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)</span><span class="sxs-lookup"><span data-stu-id="a7c15-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="a7c15-110">Para obtener información sobre si la información de licencias para el espacio empresarial especificado está disponible en el centro de administración de Skype Empresarial Online, use el cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="a7c15-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a7c15-111">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a7c15-111">Related topics</span></span>
[<span data-ttu-id="a7c15-112">Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7c15-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
