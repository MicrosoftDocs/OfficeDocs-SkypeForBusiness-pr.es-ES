---
title: "Administrar Skype para las organizaciones de negocios en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Uso de Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su Skype para inquilinos de negocios en línea."
ms.openlocfilehash: 484911da152ce4bd8f682321575c0cfecafd4e73
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="7b199-103">Administrar Skype para las organizaciones de negocios en línea</span><span class="sxs-lookup"><span data-stu-id="7b199-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="7b199-104">Encontrará información acerca de su Skype para inquilinos de negocios en línea mediante el uso de los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7b199-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="7b199-105">Administrar Skype para arrendatarios de negocios en línea</span><span class="sxs-lookup"><span data-stu-id="7b199-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="7b199-106">Para obtener información acerca de su Skype para inquilinos de negocios en línea, llame el cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="7b199-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="7b199-107">Para devolver a sólo el inquilino nombre e Id., utilice este comando.</span><span class="sxs-lookup"><span data-stu-id="7b199-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="7b199-108">El valor del parámetro _TenantID_ es necesario al ejecutar los cmdlets como [Conjunto de CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [CsTenantFederationConfiguration del conjunto](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b199-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="7b199-109">Para obtener más información acerca de si la información de licencia para el inquilino especificado está disponible en el Skype para el centro de administración de negocios en línea, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="7b199-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7b199-110">See also</span><span class="sxs-lookup"><span data-stu-id="7b199-110">Related topics</span></span>
[<span data-ttu-id="7b199-111">Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b199-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
