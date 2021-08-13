---
title: Descargar e instalar el módulo Skype Empresarial Online Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: Descargue, instale y, a continuación, use Skype Empresarial Online Connector para crear una sesión de Windows PowerShell que se conecte a Skype Empresarial Online.
ms.openlocfilehash: fd0a114bcd434e624937b323fbfa787d252db96ffafb701c3f13ff3a677b7118
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339288"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Descargar e instalar el módulo Teams PowerShell

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> La última Teams versión pública de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) se integra con Skype Empresarial Online Connector, lo que proporciona un único módulo para Teams y Skype Empresarial administración de PowerShell en línea.


1. Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra un Windows PowerShell de comandos y ejecute los siguientes comandos: 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectar todos los servicios de Microsoft 365 o Office 365 en una única ventana de [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
