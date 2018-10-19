---
title: Uso de PowerShell para administrar los equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Aprenda a usar Windows PowerShell para administrar todas las características que se encuentran en Microsoft Teams de.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c8eb0c37f71972bb20fac60706ff7a369d971d4
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678349"
---
# <a name="using-powershell-to-manage-teams"></a>Uso de PowerShell para administrar los equipos

Las características de los equipos se pueden administrar mediante PowerShell o el Microsoft Teams y Skype para centro de administración de negocio. 

> ! [Nota] No todas las características en los equipos se pueden administrar con el módulo del conector de los equipos. Debe usar la Skype para Business connector. Vea [descargar e instalar el Skype para conector de negocio en línea](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

### <a name="step-1-prerequisites"></a>Paso 1: requisitos previos

Administración remota de Microsoft Teams mediante PowerShell sólo se admite en los equipos de 64 bits que ejecutan uno de los siguientes sistemas operativos:
  
- Windows 10
- Windows 8.1
- Windows 8 
- Windows Server 2012 R2
- Windows Server 2012
- Windows Server 2008
- Windows 7
    
Además de un sistema operativo compatible, el equipo también debe ejecutar lo siguiente:
  
- PowerShell 3.0 o posterior
    
- Módulo de conector de PowerShell de los equipos


### <a name="step-2-install-powershell-30-or-higher"></a>Paso 2: Instalar PowerShell 3.0 o posterior
[Use este tema para obtener ayuda](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a>Paso 3: Descargar e instalar el módulo del conector de los equipos
[Use este tema para obtener ayuda](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

Instalar el módulo más reciente desde el uso de la Galería de PowerShell: 
  
  Install-módulo MicrosoftTeams

O bien, para obtener más información, el paquete se puede encontrar aquí:https://www.powershellgallery.com/packages/MicrosoftTeams/

### <a name="step-4-connect-using-the-teams-connector-module"></a>Paso 4: Conectar con el módulo del conector de los equipos
[Use este tema para obtener ayuda](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a>Temas relacionados
- [Administrar las características de los equipos con PowerShell](manage-features-with-powershell.md)
