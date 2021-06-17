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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947572"
---
# <a name="install-microsoft-teams-powershell-module"></a>Instalar Microsoft Teams módulo de PowerShell

En este artículo se explica cómo instalar el módulo Microsoft Teams PowerShell con la Galería de PowerShell. El Microsoft Teams de PowerShell es compatible con todas Windows plataformas. 

## <a name="requirements"></a>Requirements

Microsoft Teams El módulo PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas. Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell)disponible para su sistema   operativo. 

Para comprobar la versión de PowerShell, ejecute el siguiente comando desde una sesión de PowerShell: 

```powershell
$PSVersionTable.PSVersion 
```
Le recomendamos que use el cmdlet Install-Module para instalar el módulo Microsoft Teams PowerShell. 
 
Si la Galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet**, la primera vez que use la PSGallery verá el siguiente mensaje:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sí** o **Sí a Todos** para continuar con la instalación.

## <a name="installing-using-the-powershellgallery"></a>Instalación con PowerShellGallery

Microsoft Teams El módulo PowerShell es compatible actualmente para su uso con PowerShell 5.1 en Windows. Siga estos pasos para instalar el módulo: 

- Actualizar a [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Si está en Windows 10 versión 1607 o posterior, ya tiene PowerShell 5.1 instalado. 
- Instale [.NET Framework 4.7.2](/dotnet/framework/install) o posterior. 
- Ejecute el siguiente comando para instalar la versión más reciente de PowerShellGet:
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- Instale el Teams PowerShell.

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>Instalación sin conexión 

En algunos entornos, no es posible conectarse a la Galería de PowerShell. En esas situaciones, siga estos [pasos de instalación manuales.](https://aka.ms/psgallery-manualdownload)  

## <a name="sign-in"></a>Iniciar sesión

Para empezar a trabajar con Microsoft Teams de PowerShell, inicie sesión con sus credenciales de Azure.

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>Actualizar Teams módulo de PowerShell

Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo. Por ejemplo, si usó originalmente Install-Module, debe usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.  

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

Ahora ya está listo para administrar Microsoft Teams con Microsoft Teams PowerShell. Vea [Administrar Teams con Teams PowerShell para](teams-powershell-managing-teams.md) empezar. 

## <a name="related-topics"></a>Temas relacionados

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notas de la versión de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams referencia de cmdlet](/powershell/teams/?view=teams-ps)

[Skype Empresarial referencia de cmdlet](/powershell/skype/intro?view=skype-ps)
