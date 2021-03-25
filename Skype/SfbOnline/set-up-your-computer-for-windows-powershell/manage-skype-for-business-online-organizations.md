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
description: Use Windows PowerShell y los cmdlets Get-CsTenant y Get-CsTenantLicensingConfiguration para obtener información sobre su inquilino de Skype Empresarial Online.
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113186"
---
# <a name="manage-skype-for-business-online-organizations"></a>Administrar organizaciones de Skype Empresarial Online
> [!NOTE]
> La versión preliminar pública más reciente de [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) se integra con Skype Empresarial Online Connector, proporcionando un único módulo para la administración de PowerShell de Teams.

Puede encontrar información sobre su espacio empresarial de Skype Empresarial Online con los **cmdlets Get-CsTenant** y **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Administrar inquilinos de Skype Empresarial Online

Para devolver información sobre su inquilino de Skype Empresarial Online, llame al cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) sin parámetros adicionales.
  
```PowerShell
Get-CsTenant
```

Para devolver solo el nombre del inquilino y el identificador, use este comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

El valor del parámetro _TenantID_ es necesario al ejecutar cmdlets como [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) y [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Para obtener información sobre si la información de licencias para el espacio empresarial especificado está disponible en el Centro de administración de Skype Empresarial Online, use el cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
