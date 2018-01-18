---
title: "Administrar Skype para las organizaciones de negocios en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Uso de Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su Skype para inquilinos de negocios en línea."
ms.openlocfilehash: cab693fa153eae99ac605981112a30ec09f49920
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
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
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
