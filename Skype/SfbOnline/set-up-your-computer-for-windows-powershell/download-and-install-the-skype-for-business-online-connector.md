---
title: Descargar e instalar el módulo Conector de Skype Empresarial Online
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
description: Descargue, instale y, a continuación, use el conector de Skype Empresarial Online para crear una sesión de Windows PowerShell que se conecte a Skype Empresarial Online.
ms.openlocfilehash: 0e00b9dd18b04deaf3d2123de1fa9609040c4e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097206"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Descargar e instalar el módulo de PowerShell de Teams

> [!NOTE]

> La última versión pública de PowerShell de Teams está integrada con Skype Empresarial Online Connector, proporcionando un único módulo para la administración de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) en línea de Teams y Skype Empresarial.


1. Instale el [módulo de PowerShell de Teams.](/microsoftteams/teams-powershell-install)
    
2. Abra un Windows PowerShell de comandos y ejecute los siguientes comandos: 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectarse a todos los servicios de [Microsoft 365 u Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) en una sola ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)