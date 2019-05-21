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
f1keywords: None
ms.custom:
- PowerShell
description: Use Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su inquilino de Skype empresarial online.
ms.openlocfilehash: 768ee4e0724bd04d38e9ce77b94372bdad498ecd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284694"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="2ae00-103">Administrar las organizaciones de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="2ae00-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="2ae00-104">Puede encontrar información sobre su inquilino de Skype empresarial online con los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2ae00-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="2ae00-105">Administrar inquilinos de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="2ae00-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="2ae00-106">Para obtener información sobre el inquilino de Skype empresarial online, llame al cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="2ae00-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="2ae00-107">Para devolver solo el identificador y el nombre de inquilino, use este comando.</span><span class="sxs-lookup"><span data-stu-id="2ae00-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="2ae00-108">El valor del parámetro _TenantID_ es necesario cuando se ejecutan cmdlets como [set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ae00-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="2ae00-109">Para buscar información sobre si la información de licencias del inquilino especificado está disponible en el centro de administración de Skype empresarial online, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="2ae00-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2ae00-110">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2ae00-110">Related topics</span></span>
[<span data-ttu-id="2ae00-111">Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ae00-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
