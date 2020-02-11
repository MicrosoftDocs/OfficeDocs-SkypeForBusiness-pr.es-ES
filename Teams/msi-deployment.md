---
title: Instalar Microsoft Teams mediante MSI mediante el administrador de configuración de Microsoft Endpoint
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Los administradores pueden usar el MSI de Teams para implementar Microsoft Teams en bloque y poder seleccionar usuarios o equipos.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f57eeb44fd728d1b656ce13f56cf2c5997805b9
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888369"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Instalar Microsoft Teams mediante el administrador de configuración de Microsoft Endpoint

> [!Tip]
> Vea la siguiente sesión para obtener información sobre las ventajas del cliente de escritorio de Windows, cómo se planea y cómo se implementa: [Teams cliente de escritorio de Windows](https://aka.ms/teams-clients)

Para usar Microsoft Endpoint Configuration Manager, una directiva de grupo o cualquier mecanismo de distribución de terceros para una implementación ampliada, Microsoft ha proporcionado archivos MSI (tanto de 32 bits como de 64 bits) que los administradores pueden usar para la implementación masiva de equipos con el fin de seleccionar usuarios o equipo. Los administradores pueden usar estos archivos para implementar equipos de forma remota, de modo que los usuarios no tengan que descargar manualmente la aplicación de Teams. Cuando se implementa, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en ese equipo. (Puede deshabilitar el inicio automático después de instalar la aplicación. [Consulte a continuación](#disable-auto-launch-for-the-msi-installer)). Le recomendamos que implemente el paquete en el equipo, de modo que todos los nuevos usuarios del equipo también se beneficien de esta implementación.

Estos son los vínculos a los archivos MSI:


|Entidad  |32 bits      |64 bits      |
|---------|---------|---------|
|Publicidad     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Gobierno federal-GCC     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Gobierno Federal: GCC High    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Gobierno Federal: DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Los equipos también pueden incluirse con una implementación de Office 365 ProPlus. Para obtener más información, consulte [implementar Microsoft Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Para obtener más información sobre Microsoft Endpoint Configuration Manager, vea [¿Qué es Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimiento de implementación (recomendado)

1. Recuperar el paquete más reciente.
2. Use los valores predeterminados rellenados previamente por el MSI.
3. Implementar en equipos siempre que sea posible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Cómo funciona el paquete MSI de Microsoft Teams

### <a name="pc-installation"></a>Instalación de PC

El MSI de Teams colocará un instalador en archivos de programa. Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación de Teams en la carpeta appdata del usuario. Si un usuario ya tiene la aplicación de Teams instalada en la carpeta appdata, el instalador MSI omitirá el proceso para ese usuario.

No use el MSI para implementar actualizaciones, ya que el cliente se actualizará automáticamente cuando detecte que hay una nueva versión disponible en el servicio. Para volver a implementar el último instalador, use el proceso de reimplementación de MSI que se describe a continuación.Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente (excepto en entornos de VDI) cuando sea posible para el usuario. Si se implementa una versión muy antigua, el MSI desencadenará una actualización de la aplicación antes de que el usuario pueda usar Teams.

> [!Important]
> No recomendamos que cambie las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización. Tener una versión demasiado antigua impedirá que los usuarios tengan acceso al servicio.

#### <a name="target-computer-requirements"></a>Requisitos del equipo de destino

- .NET Framework 4,5 o posterior
- Windows 7 o posterior
- Windows Server 2012 R2 o posterior
- 3 GB de espacio en disco para cada perfil de usuario (recomendado)

### <a name="vdi-installation"></a>Instalación de VDI

Para obtener instrucciones completas sobre cómo implementar la aplicación de escritorio de Teams en VDI, vea [Teams for virtualizated Desktop Infrastructure](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedimiento de limpieza y reimplementación

Si un usuario desinstala equipos de su perfil de usuario, el instalador MSI realizará un seguimiento de que el usuario ha desinstalado la aplicación de Teams y ya no instalará Teams para ese perfil de usuario. Para volver a implementar Teams para este usuario en un equipo determinado en el que se ha desinstalado, haga lo siguiente:

1. Desinstalar la aplicación de Teams instalada para todos los perfiles de usuario.
2. Después de la desinstalación, eliminar el directorio de forma recursiva en%localappdata%\Microsoft\Teams\.
3. Vuelva a implementar el paquete MSI en ese equipo.

> [!TIP]
> Puede usar nuestro script de limpieza de la [implementación de Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de Configuration Manager.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Impedir que los equipos se inicien automáticamente después de la instalación

El comportamiento predeterminado del MSI es instalar la aplicación de Teams en cuanto un usuario inicia sesión y, a continuación, iniciar automáticamente Teams. Si no quiere que los usuarios se inicien automáticamente para los usuarios después de la instalación, puede usar la Directiva de grupo para establecer una configuración de directiva o deshabilitar el inicio automático para el instalador MSI.

#### <a name="use-group-policy-recommended"></a>Usar la Directiva de grupo (recomendado)

Habilite la opción **impedir que Microsoft Teams se inicie automáticamente después de la instalación** . Puede encontrar esta configuración de directiva en Usuario\directivas\plantillas Administrativas\microsoft Teams. Este es el método recomendado porque puede desactivar o activar la configuración de directiva según las necesidades de su organización.

Al habilitar esta configuración de Directiva antes de instalar Teams, Teams no se inicia automáticamente cuando los usuarios inician sesión en Windows. Después de que un usuario inicia sesión en Teams por primera vez, Teams se inicia automáticamente la próxima vez que el usuario inicia sesión.

Para obtener más información, vea [usar la Directiva de grupo para evitar que los equipos se inicien automáticamente después de la instalación](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Si ya ha implementado Teams y desea configurar esta directiva para deshabilitar la función AutoStart de Teams, primero establezca la configuración de directiva de grupo en el valor que desee y, a continuación, ejecute el [script de restablecimiento de equipos de AutoStart](scripts/powershell-script-teams-reset-autostart.md) para cada usuario.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Deshabilitar el inicio automático para el instalador MSI

Puede deshabilitar el inicio automático para el instalador MSI mediante el parámetro **Options = "noautostart = true"** de la siguiente manera.  

Para la versión de 32 bits

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

Para la versión de 64 bits

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

Cuando un usuario inicia sesión en Windows, Teams se instala con el MSI y se agrega un acceso directo a iniciar Teams en el escritorio del usuario. Los equipos no se iniciarán hasta que el usuario inicie manualmente Teams. Una vez que el usuario inicia manualmente Teams, Teams se inicia automáticamente cada vez que el usuario inicia sesión.

> [!Note]
> Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados. Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción para deshabilitar el inicio automático.
