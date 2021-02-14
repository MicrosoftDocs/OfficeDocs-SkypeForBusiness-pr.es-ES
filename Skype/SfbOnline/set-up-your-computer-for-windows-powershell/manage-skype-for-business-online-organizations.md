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
# <a name="manage-skype-for-business-online-organizations"></a>Administrar organizaciones de Skype Empresarial Online
> [!NOTE]
> La versión [preliminar pública de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams más reciente está integrada con Skype Empresarial Online Connector, proporcionando un módulo único para la administración de PowerShell de Teams.

Puede encontrar información sobre su inquilino de Skype Empresarial Online con los **cmdlets Get-CsTenant** y **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Administrar inquilinos de Skype Empresarial Online

Para devolver información sobre su espacio empresarial de Skype Empresarial Online, llame al cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sin ningún parámetro adicional.
  
```PowerShell
Get-CsTenant
```

Para devolver solo el nombre del inquilino y el id., use este comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro _TenantID_ es necesario al ejecutar cmdlets como [Set-CsTenantProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) y [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)
  
Para obtener información sobre si la información de licencias para el espacio empresarial especificado está disponible en el Centro de administración de Skype Empresarial Online, use el cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
