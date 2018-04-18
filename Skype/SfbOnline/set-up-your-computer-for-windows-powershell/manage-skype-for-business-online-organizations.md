---
title: Administrar Skype para las organizaciones de negocios en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: Uso de Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su Skype para inquilinos de negocios en línea.
ms.openlocfilehash: 1b58686b2330b43cc5978752ac4f6b4a91f9588e
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="manage-skype-for-business-online-organizations"></a>Administrar Skype para las organizaciones de negocios en línea

Encontrará información acerca de su Skype para inquilinos de negocios en línea mediante el uso de los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Administrar Skype para arrendatarios de negocios en línea

Para obtener información acerca de su Skype para inquilinos de negocios en línea, llame el cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.
  
```
Get-CsTenant
```

Para devolver a sólo el inquilino nombre e Id., utilice este comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro _TenantID_ es necesario al ejecutar los cmdlets como [Conjunto de CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [CsTenantFederationConfiguration del conjunto](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Para obtener más información acerca de si la información de licencia para el inquilino especificado está disponible en el Skype para el centro de administración de negocios en línea, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>See also
[Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 