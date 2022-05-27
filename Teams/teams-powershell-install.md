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
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682011"
---
# <a name="install-microsoft-teams-powershell-module"></a>Instalar Microsoft Teams módulo de PowerShell

En este artículo se explica cómo instalar el módulo Microsoft Teams PowerShell con Galería de PowerShell. El módulo Microsoft Teams PowerShell es compatible con todas las plataformas de Windows. Mac y Linux no son compatibles.

## <a name="requirements"></a>Requirements

Microsoft Teams módulo de PowerShell requiere PowerShell 5.1 o superior en todas las plataformas. Instale la [última versión de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.

Para comprobar su versión de PowerShell, ejecute el siguiente comando desde una sesión de PowerShell:

```powershell
$PSVersionTable.PSVersion
```

Le recomendamos que use el cmdlet Install-Module para instalar el módulo Microsoft Teams PowerShell.

Si Galería de PowerShell (PSGallery) no está configurado como repositorio de confianza para **PowerShellObtener**, la primera vez que use la PSGallery verá el siguiente mensaje:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sí** o **Sí a Todos** para continuar con la instalación.

## <a name="installing-using-the-powershellgallery"></a>Instalación con PowerShellGallery

Microsoft Teams módulo de PowerShell es compatible actualmente con PowerShell 5.1 en Windows. Siga estos pasos para instalar el módulo:

- Actualizar a [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Si usa Windows 10 versión 1607 o posterior, ya tiene instalado PowerShell 5.1.
- Instala [.NET Framework 4.7.2](/dotnet/framework/install) o posterior.
- Ejecute el siguiente comando para instalar la versión más reciente de PowerShellObtener:

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- Instale el módulo Teams PowerShell.

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>Instalación sin conexión

En algunos entornos, no es posible conectarse a la Galería de PowerShell. En estos casos, siga estos [pasos de instalación manual](https://aka.ms/psgallery-manualdownload).

## <a name="sign-in"></a>Iniciar sesión

Para empezar a trabajar con Microsoft Teams módulo de PowerShell, inicie sesión con sus credenciales de Azure.

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>Actualizar Teams módulo de PowerShell

Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo. Por ejemplo, si originalmente usaste Install-Module, deberías usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al actualizar el módulo. Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.

## <a name="uninstall-teams-powershell"></a>Desinstalar Teams PowerShell

Para desinstalar Microsoft Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell y ejecute lo siguiente:

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>Pasos siguientes

Ahora ya puede administrar Microsoft Teams con Microsoft Teams PowerShell. Vea [Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md) para empezar.

## <a name="related-topics"></a>Temas relacionados

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[notas de la versión de Teams PowerShell](teams-powershell-release-notes.md)

[referencia de cmdlet de Microsoft Teams](/powershell/teams/)

[referencia de cmdlet de Skype Empresarial](/powershell/skype/intro)
