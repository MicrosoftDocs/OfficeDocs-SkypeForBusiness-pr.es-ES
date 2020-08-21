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
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824941"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar Microsoft Teams PowerShell

En este artículo se explica cómo instalar el módulo Microsoft Teams PowerShell con [PowerShellGet](/powershell/scripting/gallery/installing-psget). Estas instrucciones funcionan en plataformas de [Shell en la nube de Azure](/azure/cloud-shell/overview), Linux, MacOS y Windows.

## <a name="requirements"></a>Requisitos

Teams PowerShell requiere PowerShell 5,1 o superior en todas las plataformas. Instale la [versión más reciente de PowerShell](/powershell/scripting/install/installing-powershell) disponible para su sistema operativo.

> [!WARNING]
> Hay problemas conocidos con PowerShell 7 y Teams. Para obtener la mejor experiencia, le recomendamos que use el PowerShell 5,1.

## <a name="install-the-teams-powershell-module"></a>Instalar el módulo de PowerShell Teams

> [!NOTE]
> Para obtener la mejor experiencia, use los módulos disponibilidad general (GA) o Public Preview, no ambos. No están diseñados para trabajar en conjunto.


Use los cmdlets de **PowerShellGet** para instalar el módulo de PowerShell de Teams. La instalación del módulo para todos los usuarios de un sistema requiere privilegios elevados. Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el `sudo` comando en MacOS o Linux:

```powershell
Install-Module MicrosoftTeams
```

De forma predeterminada, la galería de PowerShell (PSGallery) no está configurada como repositorio de confianza para **PowerShellGet**. La primera vez que use el PSGallery, verá el siguiente mensaje:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **sí** o **sí a todo** para continuar con la instalación.


## <a name="install-teams-powershell-public-preview"></a>Instalar la versión preliminar pública de Team PowerShell

> [!NOTE]
> Si está usando la versión de la versión preliminar pública de Teams, le recomendamos encarecidamente que desinstale primero el conector de Skype empresarial online.

La instalación del módulo de vista previa pública de Teams PowerShell para todos los usuarios de un sistema requiere privilegios elevados. Inicie la sesión de PowerShell con **Ejecutar como administrador** en Windows o use el `sudo` comando en MacOS o Linux.

Si está usando PowerShell 5,1, debe actualizar el módulo **PowerShellGet** de antemano. Después de actualizar **powershellget**, cierre y vuelva a abrir una sesión de PowerShell elevada para asegurarse de que se cargue el último **PowerShellGet** .

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar la versión preliminar pública de Teams PowerShell, ejecute el siguiente comando de PowerShell.

> [!NOTE]
> Puede encontrar la versión preliminar más reciente en la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o en PowerShell ejecutando "Find-Module MicrosoftTeams-AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Instalar el conector de Skype empresarial online

> [!WARNING]
> En este momento, el conector de Skype empresarial online forma parte de Team PowerShell Public Preview. Una vez que hayamos implementado esta característica en la versión GA de Teams, ya no estará disponible el conector de Skype empresarial online.

Descargue e instale el [módulo de PowerShell de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=39366)y, a continuación, ejecute lo siguiente en PowerShell.

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Iniciar sesión

Para empezar a trabajar con Teams PowerShell, inicie sesión con sus credenciales de Azure.

> [!NOTE]
> Si está usando la última versión de la [versión preliminar pública de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), no necesita instalar el conector de Skype empresarial online.

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
> Si Teams PowerShell ya se ha importado a la sesión de PowerShell, no se podrá actualizar el módulo. Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.


## <a name="uninstall-teams-powershell"></a>Desinstalar Teams PowerShell



Para desinstalar Teams PowerShell, abra un nuevo símbolo del sistema de PowerShell elevado y ejecute lo siguiente:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Si Teams PowerShell ya se ha importado a la sesión de PowerShell, se producirá un error al desinstalar el módulo. Cierre PowerShell y vuelva a abrir una nueva sesión de PowerShell con privilegios elevados.

## <a name="next-steps"></a>Pasos siguientes

Ahora ya está listo para administrar equipos con el PowerShell de Teams. Consulte [Administración de equipos con el PowerShell de Teams](teams-powershell-managing-teams.md) para comenzar.

## <a name="related-topics"></a>Temas relacionados

[Administración de equipos con Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de la versión de Teams PowerShell](teams-powershell-release-notes.md)

[Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
