---
title: Administrar las organizaciones de Skype empresarial online
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
description: Use Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su inquilino de Skype empresarial online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085696"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="3bb25-103">Administrar las organizaciones de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="3bb25-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="3bb25-104">La versión más reciente de la [versión preliminar pública de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada en el conector de Skype empresarial online, que ofrece un único módulo para la administración de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="3bb25-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="3bb25-105">Puede encontrar información sobre su inquilino de Skype empresarial online con los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3bb25-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="3bb25-106">Administrar inquilinos de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="3bb25-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="3bb25-107">Para obtener información sobre el inquilino de Skype empresarial online, llame al cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="3bb25-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="3bb25-108">Para devolver solo el identificador y el nombre de inquilino, use este comando.</span><span class="sxs-lookup"><span data-stu-id="3bb25-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="3bb25-109">El valor del parámetro _TenantID_ es necesario cuando se ejecutan cmdlets como [set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="3bb25-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="3bb25-110">Para buscar información sobre si la información de licencias del inquilino especificado está disponible en el centro de administración de Skype empresarial online, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="3bb25-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3bb25-111">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3bb25-111">Related topics</span></span>
[<span data-ttu-id="3bb25-112">Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3bb25-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
