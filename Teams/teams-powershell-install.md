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
ms.openlocfilehash: a99967df019a91460bde5fd4e3e6e7aee15444d3
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569116"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar Microsoft Teams PowerShell

En este artículo se explica cómo instalar el módulo PowerShell de Microsoft Teams con [PowerShellGet](/powershell/scripting/gallery/installing-psget). Estas instrucciones funcionan en [plataformas Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS y Windows.

## <a name="requirements"></a>Requisitos

Teams PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas. Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.

> [!WARNING]
> Hay problemas conocidos con PowerShell 7 y Teams PowerShell. Para obtener la mejor experiencia, le recomendamos que use PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Instalar el módulo de PowerShell de Teams

> [!NOTE]
> Para obtener la mejor experiencia, use los módulos Disponibilidad general (GA) o Vista previa pública, no ambos. No están pensados para trabajar juntos.


Use los cmdlets **de PowerShellGet** para instalar el módulo de PowerShell de Teams. La instalación del módulo para todos los usuarios en un sistema requiere privilegios elevados. Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux:

```powershell
Install-Module MicrosoftTeams
```

De forma predeterminada, la Galería de PowerShell (PSGallery) no está configurada como un repositorio de confianza para **PowerShellGet**. La primera vez que use psgallery, verá el siguiente mensaje:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sí** o **Sí a Todos** para continuar con la instalación.


## <a name="install-teams-powershell-public-preview"></a>Instalar la vista previa pública de PowerShell de Teams

> [!NOTE]
> Si usa la versión de vista previa pública de Teams PowerShell, le recomendamos que desinstale primero Skype Empresarial Online Connector.

Instalar el módulo de vista previa pública de PowerShell de Teams para todos los usuarios de un sistema requiere privilegios elevados. Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el comando en `sudo` macOS o Linux.

Si usa PowerShell 5.1, debe actualizar el módulo **PowerShellGet** previamente. Después de actualizar **PowerShellGet**, cierre y vuelva a abrir una sesión de PowerShell con privilegios elevados para asegurarse de que se carga el **PowerShellGet** más reciente.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar la vista previa pública de PowerShell de Teams, ejecute el comando de PowerShell siguiente.

> [!NOTE]
> Puede encontrar la versión preliminar más reciente en la Galería de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams -AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Instalar skype empresarial Online Connector

> [!NOTE]
>
> Skype Empresarial Online Connector forma parte actualmente del último módulo de PowerShell de Teams.
> Si usa la última versión pública de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a>Iniciar sesión

Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.

> [!NOTE]
> Si usa la versión preliminar pública más reciente de [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Actualizar PowerShell de Teams

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

Ahora ya está listo para administrar Teams con Teams PowerShell. Vea [Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md) para empezar.

## <a name="related-topics"></a>Temas relacionados

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
