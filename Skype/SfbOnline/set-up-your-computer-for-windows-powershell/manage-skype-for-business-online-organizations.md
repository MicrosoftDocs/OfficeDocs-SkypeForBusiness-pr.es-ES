---
title: Administrar Skype Empresarial en línea
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
description: Use Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su Skype Empresarial en línea.
ms.openlocfilehash: 733d7e30bc25f15bcf05c2746ef1eb2cb8aa5cfd8e7e780356c4a972ef97a183
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298750"
---
# <a name="manage-skype-for-business-online-organizations"></a>Administrar Skype Empresarial en línea

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> La versión Teams versión preliminar pública de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) se integra con Skype Empresarial Online Connector, lo que proporciona un único módulo para Teams administración de PowerShell.

Puede encontrar información sobre su espacio empresarial Skype Empresarial Online mediante los **cmdlets Get-CsTenant** y **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Administrar Skype Empresarial en línea

Para devolver información sobre su espacio empresarial Skype Empresarial online, llame al cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sin ningún parámetro adicional.
  
```PowerShell
Get-CsTenant
```

Para devolver solo el nombre del inquilino y el identificador, use este comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro _TenantID_ es necesario al ejecutar cmdlets como [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) y [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Para obtener información sobre si la información de licencias para el espacio empresarial especificado está disponible en el centro de administración de Skype Empresarial Online, use el cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
