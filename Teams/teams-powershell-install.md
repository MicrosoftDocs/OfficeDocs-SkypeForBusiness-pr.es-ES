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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768349"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar Microsoft Teams PowerShell

En este artículo se explica cómo instalar el Microsoft Teams PowerShell con [PowerShellGet](/powershell/scripting/gallery/installing-psget). Estas instrucciones funcionan en [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS y Windows plataformas.

## <a name="requirements"></a>Requirements

Teams PowerShell requiere PowerShell 5.1 o posterior en todas las plataformas. Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.

> [!NOTE]
> Para obtener la mejor experiencia, le recomendamos que use PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Instalar el Teams PowerShell

> [!NOTE]
> Para obtener la mejor experiencia, use los módulos Disponibilidad general (GA) o Vista previa pública, no ambos. No están pensados para trabajar juntos.


Use los cmdlets **de PowerShellGet** para instalar el Teams PowerShell. La instalación del módulo para todos los usuarios en un sistema requiere privilegios elevados. Inicie la sesión de PowerShell con **Ejecutar** como administrador en Windows o use el `sudo` comando en macOS o Linux:

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

## <a name="sign-in"></a>Iniciar sesión

Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.

> [!NOTE]
> Si usa la última versión Teams versión preliminar pública de [PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar el Skype Empresarial Online Connector.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Iniciar sesión con MFA y autenticación moderna

 Si su cuenta usa la autenticación multifactor, siga los pasos de esta sección.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>Actualizar Teams PowerShell

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

## <a name="install-teams-powershell-public-preview"></a>Instalar Teams vista previa pública de PowerShell

> [!NOTE]
> Si usa la versión de vista previa pública de Teams PowerShell, le recomendamos que desinstale primero Skype Empresarial Online Connector.

Instalar el Teams de vista previa pública de PowerShell para todos los usuarios de un sistema requiere privilegios elevados. Inicie la sesión de PowerShell con **Ejecutar** como administrador en Windows o use el `sudo` comando en macOS o Linux.

Si usa PowerShell 5.1, debe actualizar el módulo **PowerShellGet** previamente. Después de actualizar **PowerShellGet**, cierre y vuelva a abrir una sesión de PowerShell con privilegios elevados para asegurarse de que se carga el **PowerShellGet** más reciente.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar Teams vista previa pública de PowerShell, ejecute el comando de PowerShell siguiente.

> [!NOTE]
> Puede encontrar la versión preliminar más reciente en la Galería de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>Pasos siguientes

Ahora ya está listo para administrar Teams con Teams PowerShell. Vea [Administrar Teams con Teams PowerShell para](teams-powershell-managing-teams.md) empezar.

## <a name="related-topics"></a>Temas relacionados

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notas de la versión de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams referencia de cmdlet](/powershell/teams/?view=teams-ps)

[Skype Empresarial referencia de cmdlet](/powershell/skype/intro?view=skype-ps)
