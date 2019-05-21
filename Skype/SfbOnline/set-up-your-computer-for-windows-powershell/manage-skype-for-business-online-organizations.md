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
# <a name="manage-skype-for-business-online-organizations"></a>Administrar las organizaciones de Skype empresarial online

Puede encontrar información sobre su inquilino de Skype empresarial online con los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Administrar inquilinos de Skype empresarial online

Para obtener información sobre el inquilino de Skype empresarial online, llame al cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.
  
```
Get-CsTenant
```

Para devolver solo el identificador y el nombre de inquilino, use este comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro _TenantID_ es necesario cuando se ejecutan cmdlets como [set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Para buscar información sobre si la información de licencias del inquilino especificado está disponible en el centro de administración de Skype empresarial online, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
