---
title: Directiva de itinerancia de red
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Obtenga información sobre cómo administrar la configuración de la directiva de itinerancia de red de Teams.
ms.openlocfilehash: c26cdec0fc41e40a9c3eac7d0324050740cf05ef
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853241"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>Administrar la configuración de vídeo y multimedia con la directiva de itinerancia de red

Además de administrar la configuración de vídeo y elementos multimedia con directivas de reunión, ahora puede controlar dinámicamente el uso de los siguientes atributos usados por el cliente de Microsoft Teams mediante TeamsNetworkRoamingPolicy: 

- Vídeo IP
- Velocidad de bits multimedia

Esta directiva le permite asignar la configuración a los sitios de red. El cliente de Teams seleccionará dinámicamente la configuración en función del sitio de red al que se conecte. Cuando el cliente de Teams inicia sesión desde un sitio de red con una directiva de itinerancia asignada, se usará esa directiva. Si no hay ninguna directiva asignada, se usarán los valores establecidos en la directiva de reunión. Para obtener más información sobre la configuración de audio y vídeo de la directiva de reunión, vea [Configuración de directiva de reunión para audio y vídeo](meeting-policies-audio-and-video.md).

## <a name="configure-the-teamsnetworkroamingpolicy"></a>Configurar TeamsNetworkRoamingPolicy

Para configurar TeamsNetworkRoamingPolicy, use los siguientes cmdlets de PowerShell:

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy contiene los siguientes parámetros:

- AllowIPVideo: esta configuración controla si se puede activar el vídeo en reuniones hospedadas por un usuario y en llamadas 1:1 y de grupo iniciadas por un usuario.

- MediaBitRateKb: esta configuración determina la velocidad total de bits multimedia para las transmisiones por audio, vídeo y uso compartido de aplicaciones en vídeo en las llamadas y reuniones para el usuario.

Después de configurar la directiva, asígnela a uno o varios sitios de red mediante el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) como se indica a continuación:

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
 ``` 
 
 Para quitar una directiva de un sitio de red, use el siguiente cmdlet:
 
 ```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
 ```

Para habilitar la directiva de itinerancia de red para los usuarios que no tienen habilitada la voz empresarial, también debe habilitar la configuración AllowNetworkConfigurationSettingsLookup en TeamsMeetingPolicy. Esta configuración está desactivada de forma predeterminada.

Para obtener más información sobre la creación de sitios de red, consulte [Configuración de red para las características de voz en la nube](cloud-voice-network-settings.md). 

## <a name="examples"></a>Ejemplos

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>Clientes compatibles

- Windows 
- Escritorio MacOS

## <a name="known-issues"></a>Problemas conocidos

Al especificar New- y Get-CsTeamsNetworkRoamingPolicy en Teams Online PowerShell v 2.0.0, verá que se muestran datos adicionales.


## <a name="related-topics"></a>Temas relacionados

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)
