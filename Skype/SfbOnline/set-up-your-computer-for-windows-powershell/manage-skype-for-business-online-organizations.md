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
# <a name="manage-skype-for-business-online-organizations"></a>Administrar Skype para las organizaciones empresariales en línea

Puede encontrar información sobre su Skype para inquilino en línea de negocio mediante el uso de los cmdlets **Get-CsTenant** y **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Administración de Skype de inquilinos en línea de negocio

Para devolver información acerca de su Skype para inquilino empresarial en línea, llame al cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.
  
```
Get-CsTenant
```

Para devolver a sólo el inquilino nombre y el identificador, use este comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro _TenantID_ se requiere al ejecutar los cmdlets como [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Para obtener información acerca de si la información de licencias para el inquilino especificado está disponible en el Skype para el centro de administración de negocio en línea, use el cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 