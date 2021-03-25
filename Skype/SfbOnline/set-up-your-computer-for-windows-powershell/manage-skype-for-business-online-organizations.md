---
title: Administrar organizaciones de Skype Empresarial Online
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
description: Use Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su inquilino de Skype Empresarial Online.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113186"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="e2c9f-103">Administrar organizaciones de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e2c9f-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="e2c9f-104">La versión preliminar pública más reciente de [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) se integra con Skype Empresarial Online Connector, proporcionando un único módulo para la administración de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="e2c9f-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="e2c9f-105">Puede encontrar información sobre su espacio empresarial de Skype Empresarial Online con los **cmdlets Get-CsTenant** y **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="e2c9f-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="e2c9f-106">Administrar inquilinos de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e2c9f-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="e2c9f-107">Para devolver información sobre su inquilino de Skype Empresarial Online, llame al cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sin parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="e2c9f-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="e2c9f-108">Para devolver solo el nombre del inquilino y el identificador, use este comando.</span><span class="sxs-lookup"><span data-stu-id="e2c9f-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="e2c9f-109">El valor del parámetro _TenantID_ es necesario al ejecutar cmdlets como [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) y [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)</span><span class="sxs-lookup"><span data-stu-id="e2c9f-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="e2c9f-110">Para obtener información sobre si la información de licencias para el espacio empresarial especificado está disponible en el Centro de administración de Skype Empresarial Online, use el cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)</span><span class="sxs-lookup"><span data-stu-id="e2c9f-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2c9f-111">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e2c9f-111">Related topics</span></span>
[<span data-ttu-id="e2c9f-112">Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2c9f-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
