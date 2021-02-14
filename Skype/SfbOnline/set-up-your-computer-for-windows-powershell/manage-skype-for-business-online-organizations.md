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
description: Use Windows PowerShell y los Get-CsTenant y Get-CsTenantLicensingConfiguration cmdlets para obtener información sobre su inquilino de Skype Empresarial Online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085696"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="96f78-103">Administrar organizaciones de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="96f78-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="96f78-104">La versión [preliminar pública de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams más reciente está integrada con Skype Empresarial Online Connector, proporcionando un módulo único para la administración de PowerShell de Teams.</span><span class="sxs-lookup"><span data-stu-id="96f78-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="96f78-105">Puede encontrar información sobre su inquilino de Skype Empresarial Online con los **cmdlets Get-CsTenant** y **Get-CsTenantLicensingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="96f78-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="96f78-106">Administrar inquilinos de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="96f78-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="96f78-107">Para devolver información sobre su espacio empresarial de Skype Empresarial Online, llame al cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="96f78-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="96f78-108">Para devolver solo el nombre del inquilino y el id., use este comando.</span><span class="sxs-lookup"><span data-stu-id="96f78-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="96f78-109">El valor del parámetro _TenantID_ es necesario al ejecutar cmdlets como [Set-CsTenantProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)</span><span class="sxs-lookup"><span data-stu-id="96f78-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="96f78-110">Para obtener información sobre si la información de licencias para el espacio empresarial especificado está disponible en el Centro de administración de Skype Empresarial Online, use el cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)</span><span class="sxs-lookup"><span data-stu-id="96f78-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="96f78-111">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="96f78-111">Related topics</span></span>
[<span data-ttu-id="96f78-112">Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96f78-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
