---
title: Instalar Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a usar los controles de PowerShell para administrar Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662025"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar Microsoft Teams PowerShell

En este artículo se explica cómo instalar el módulo De PowerShell de Microsoft Teams con [PowerShellGet.](/powershell/scripting/gallery/installing-psget) Estas instrucciones funcionan en [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS y plataformas Windows.

## <a name="requirements"></a>Requisitos

Teams PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas. Instale la [última versión de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.

> [!WARNING]
> Hay problemas conocidos con PowerShell 7 y Teams PowerShell. Para obtener la mejor experiencia, se recomienda usar PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Instalar el módulo PowerShell de Teams

> [!NOTE]
> Para obtener la mejor experiencia, use los módulos de disponibilidad general (GA) o vista previa pública (no ambos). No están pensadas para trabajar en conjunto.


Use los **cmdlets de PowerShellGet** para instalar el módulo de PowerShell de Teams. Instalar el módulo para todos los usuarios de un sistema requiere privilegios elevados. Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux:

```powershell
Install-Module MicrosoftTeams
```

De forma predeterminada, la galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet.** La primera vez que use la PSGallery, verá el siguiente mensaje:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sí** o **Sí a Todos** para continuar con la instalación.


## <a name="install-teams-powershell-public-preview"></a>Instalar teams vista previa pública de PowerShell

> [!NOTE]
> Si usa la versión Public Preview de Teams PowerShell, le recomendamos encarecidamente que desinstale primero Skype Empresarial Online Connector.

Instalar el módulo de vista previa pública de PowerShell de Teams para todos los usuarios de un sistema requiere privilegios elevados. Inicie la sesión de PowerShell usando **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux.

Si usa PowerShell 5.1, debe actualizar el módulo **PowerShellGet** previamente. Después de actualizar **PowerShellGet,** cierre y vuelva a abrir una sesión de PowerShell con privilegios elevados para asegurarse de que se carga la última **sesión de PowerShellGet.**

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar teams powershell público preview, ejecute el siguiente comando de PowerShell.

> [!NOTE]
> Puede encontrar la versión preliminar más reciente en la galería de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams -AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Instalar Skype Empresarial Online Connector

> [!NOTE]
>
> Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
> Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Iniciar sesión

Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.

> [!NOTE]
> Si usa la versión preliminar pública de PowerShell más reciente de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Actualizar Teams con PowerShell

Para actualizar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al actualizar el módulo. Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.


## <a name="uninstall-teams-powershell"></a>Desinstalar Teams PowerShell



Para desinstalar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell con privilegios elevados y ejecute lo siguiente:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al desinstalar el módulo. Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.

## <a name="next-steps"></a>Siguientes pasos

Ahora ya está listo para administrar Teams con Teams PowerShell. Consulte [Administrar Equipos con PowerShell de Teams](teams-powershell-managing-teams.md) para empezar.

## <a name="related-topics"></a>Temas relacionados

[Administrar Teams con PowerShell de Teams](teams-powershell-managing-teams.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
