---
title: Instalar Teams con el administrador de configuración de Microsoft Endpoint
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b29e850193e50049986f37c0cb19bbfb96a6c13
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43138370"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Instalar Microsoft Teams con Microsoft Endpoint Configuration Manager

> [!Tip]
> Vea la siguiente sesión para obtener más información sobre las ventajas del cliente de escritorio de Windows, cómo planearlo y cómo implementarlo: [Teams cliente de escritorio de Windows](https://aka.ms/teams-clients).

Para usar Microsoft Endpoint Configuration Manager, o Directiva de grupo o cualquier otro mecanismo de distribución de terceros para una amplia implementación, Microsoft ha proporcionado archivos MSI (tanto de 32 bits como de 64 bits) que los administradores pueden usar para la implementación masiva de Teams para seleccionar usuarios o equipos. Los administradores pueden usar estos archivos para implementar Teams de forma remota, de modo que los usuarios no tengan que descargar manualmente la aplicación Teams. Tras la implementación, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en el equipo. (Puede deshabilitar el inicio automático después de instalar la aplicación. [Consulte más adelante](#disable-auto-launch-for-the-msi-installer)). Le recomendamos que implemente el paquete en el equipo de forma que todos los nuevos usuarios del equipo se beneficiarán también de esta implementación.

Estos son los vínculos a los archivos MSI:


|Entidad  |32 bits      |64 bits      |
|---------|---------|---------|
|Comercial     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Administración Pública Federal: GCC     | [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Administración Pública Federal: GCC High    | [32 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 bits](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Administración Pública Federal: DoD     | [32 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 bits](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

> [!NOTE]
> Instale la versión de Teams de 64 en los sistemas operativos de 64 bits. Si intenta instalar la versión de 64 bits de Teams en un sistema operativo de 32 bits, la instalación no se realizará correctamente y no recibirá un mensaje de error.

Teams también se pueden incluir con una implementación de Office 365 ProPlus. Para obtener más información, consulte [Implementar Microsoft Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Para obtener más información sobre Microsoft Endpoint Configuration Manager, vea [¿Qué es Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>Proceso de implementación (recomendado)

1. Recupere el último paquete.
2. Use las opciones predeterminadas rellenadas previamente por el MSI.
3. Si es posible, impleméntelo en los equipos.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Cómo funciona el paquete MSI de Microsoft Teams

### <a name="pc-installation"></a>Instalación en PC

El MSI de Teams colocará un instalador en Archivos de programa. Cada vez que un usuario inicia sesión en un nuevo Perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación Teams en la carpeta `AppData` de ese usuario. Si un usuario ya tiene la aplicación Teams instalada en la carpeta `AppData`, el instalador de MSI omitirá el proceso para ese usuario.

No use el MSI para implementar actualizaciones, ya que el cliente se actualizará automáticamente cuando detecte una nueva versión disponible en el servicio. Para volver a implementar el último instalador, utilice el proceso de reimplementación de MSI que se describe a continuación. Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente (excepto en entornos VDI) cuando sea posible para el usuario. Si se implementa una versión muy antigua, el MSI iniciará una actualización de la aplicación antes de que el usuario pueda usar Teams.

> [!Important]
> No es recomendable que cambie las ubicaciones de instalación predeterminadas, ya que esto podría romper el flujo de actualización. Si tiene una versión demasiado antigua, se podría bloquear a los usuarios el acceso al servicio.

#### <a name="target-computer-requirements"></a>Requisitos del equipo de destino

- .NET Framework 4.5 o posterior
- Windows 8.1 o posterior
- Windows Server 2012 R2 o posterior
- 3 GB de espacio en disco por cada perfil de usuario (recomendado)

### <a name="vdi-installation"></a>Instalación en VDI

Para obtener instrucciones detalladas sobre cómo implementar la aplicación de escritorio de Teams en VDI, consulte [Teams para Infraestructura de escritorio virtual](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedimiento de limpieza y reimplementación

Si un usuario desinstala equipos de su perfil de usuario, el instalador MSI realizará un seguimiento de que el usuario ha desinstalado la aplicación de Teams y ya no instalará Teams para ese perfil de usuario. Para volver a implementar Teams para este usuario en un equipo concreto en el que se desinstaló, haga lo siguiente:

> [!IMPORTANT]
> Los pasos siguientes contienen información acerca de cómo modificar el registro. Asegúrese de hacer una copia de seguridad del registro antes de modificarlo y de que sabe restaurar el registro en caso de que se produzca un problema. Para obtener más información sobre cómo realizar copias de seguridad, restaurar y modificar el registro, consulte la [información del registro de Windows para usuarios avanzados](https://support.microsoft.com/help/256986).

1. Desinstale la aplicación de Teams instalada para cada perfil de usuario. Para obtener más información, consulte [desinstalar Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Elimine el directorio de `%localappdata%\Microsoft\Teams\`forma recursiva.
3. Elimine `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` el valor del registro.
4. Vuelva a implementar el paquete MSI en ese equipo concreto.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Evite que Microsoft Teams se inicie automáticamente después de la instalación

El comportamiento predeterminado del MSI es instalar la aplicación Teams en cuanto un usuario inicia sesión y, después, iniciar Teams automáticamente. Si no desea que Teams se inicie automáticamente para los usuarios una vez que se haya instalado, puede usar Directiva de grupo para establecer la configuración de una directiva o deshabilitar el inicio automático para el instalador MSI.

### <a name="use-group-policy-recommended"></a>Usar Directiva de grupo (recomendado)

Habilite la opción de Directiva de Grupo **Evitar que Microsoft Teams se inicie automáticamente después de la instalación**. Puede encontrar esta opción de directiva en Configuración de usuario\Directivas\Plantillas administrativas\Microsoft Teams. Este es el método recomendado, ya que puede activar o desactivar la opción de directiva según las necesidades de su organización.

Cuando habilita esta opción de directiva antes de instalar Teams, Teams no se inicia automáticamente cuando el usuario inicia sesión en Windows. Después de que un usuario inicia sesión en Teams por primera vez, Teams se iniciará automáticamente la próxima vez que el usuario inicie sesión.

Para obtener más información, consulte [Usar Directiva de grupo para evitar que Microsoft Teams se inicie automáticamente después de la instalación](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Si ya ha implementado Teams y desea establecer esta directiva para deshabilitar el inicio automático de Teams, en primer lugar, establezca el valor que desee en la opción Directiva de grupo y, a continuación, ejecute la [Secuencia de comandos de restablecimiento de inicio automático de Teams](scripts/powershell-script-teams-reset-autostart.md) para cada usuario.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Deshabilitar el inicio automático del instalador MSI

Puede deshabilitar el inicio automático para el instalador MSI mediante el parámetro **OPTIONS="noAutoStart=true"** como se indica a continuación.  

Para la versión de 32 bits:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Para la versión de 64 bits:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Cuando un usuario inicia sesión en Windows, Teams se instala con el MSI y se añade un acceso directo para iniciar Teams en el escritorio del usuario. Teams no se iniciará hasta que el usuario inicie manualmente Teams. Después de que el usuario haya iniciado manualmente Teams, Teams se iniciará automáticamente cada vez que el usuario inicie sesión.

Tenga en cuenta que estos ejemplos también usan el parámetro **ALLUSERS = 1** . Al establecer este parámetro, el instalador para todo el equipo se muestra en programas y características en el panel de control y en aplicaciones & características de configuración de Windows para todos los usuarios del equipo. Todos los usuarios pueden desinstalar Teams si disponen de credenciales de administrador en el equipo.

> [!Note]
> Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados. Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción de deshabilitar el inicio automático.
