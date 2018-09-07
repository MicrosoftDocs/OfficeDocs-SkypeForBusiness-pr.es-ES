---
title: Administrar Skype para las organizaciones empresariales en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información acerca de su Skype para inquilino en línea de negocio.
ms.openlocfilehash: 279f9431c69605377fcc0070bf9c81a027cb4064
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863337"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="c1b12-103">Administrar Skype para las organizaciones empresariales en línea</span><span class="sxs-lookup"><span data-stu-id="c1b12-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="c1b12-104">Puede encontrar información sobre su Skype para inquilino en línea de negocio mediante el uso de los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c1b12-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="c1b12-105">Administración de Skype de inquilinos en línea de negocio</span><span class="sxs-lookup"><span data-stu-id="c1b12-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="c1b12-106">Para devolver información acerca de su Skype para inquilino empresarial en línea, llame al cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="c1b12-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="c1b12-107">Para devolver a sólo el inquilino nombre y el identificador, use este comando.</span><span class="sxs-lookup"><span data-stu-id="c1b12-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="c1b12-108">El valor del parámetro _TenantID_ se requiere al ejecutar los cmdlets como [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1b12-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="c1b12-109">Para obtener información acerca de si la información de licencias para el inquilino especificado está disponible en el Skype para el centro de administración de negocio en línea, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .</span><span class="sxs-lookup"><span data-stu-id="c1b12-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c1b12-110">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c1b12-110">Related topics</span></span>
[<span data-ttu-id="c1b12-111">Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1b12-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 