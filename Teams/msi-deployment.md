---
title: Instalar teams en masa con Windows Installer (MSI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Use archivos de Windows Installer (MSI) para distribuir el cliente de Teams a varios usuarios y equipos.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b8c8521aa5e19abe59aa9e4c60fcc41eff9b1c7
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713328"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>Instalar teams en masa con Windows Installer (MSI)

> [!Tip]
> Vea la siguiente sesión para conocer las ventajas del cliente de escritorio para Windows y cómo planearlo e implementarlo: [Cliente de escritorio de Teams para Windows](https://aka.ms/teams-clients).

Microsoft proporciona archivos MSI de 32 bits, 64 bits y ARM64 que puede usar para implementar en masa Microsoft Teams para seleccionar usuarios y equipos. Los archivos MSI se pueden usar con software de distribución de [Microsoft Endpoint Configuration Manager](/configmgr/core/understand/introduction), [directiva de grupo](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) o de terceros para implementar Teams en su organización. Las implementaciones masivas son útiles porque los usuarios no necesitan descargar e instalar el cliente de Teams manualmente. En su lugar, Teams se implementará en los equipos y, a continuación, se iniciará automáticamente la primera vez que los usuarios inicien sesión en un equipo.

Le recomendamos que implemente el paquete en equipos en lugar de un usuario específico. Al dirigir los equipos, todos los usuarios nuevos de esos equipos se beneficiarán de esta implementación.

>[!NOTE]
> Los equipos también se pueden distribuir a su organización como parte de Aplicaciones Microsoft 365 para empresas. Para más información, consulte [Implementar Microsoft Teams con las Aplicaciones de Microsoft 365 para empresas](/deployoffice/teams-install).

## <a name="msi-files"></a>Archivos MSI

En la tabla siguiente se proporcionan vínculos a archivos MSI de 32 bits, 64 bits y ARM64 para Teams. Descargue el MSI que desea instalar en los equipos de su organización. La arquitectura x86 (32 bits o 64 bits) que admite Teams es independiente de otras aplicaciones de Office instaladas en un equipo.

Si tiene equipos de 64 bits, se recomienda instalar el MSI de Teams de 64 bits incluso si el equipo ejecuta una versión de 32 bits de Office. El MSI de ARM64 solo se puede instalar en equipos que usan la arquitectura ARM, como el Surface Pro X.

> [!IMPORTANT]
> Instale la versión de 64 bits de Teams solo en sistemas operativos de 64 bits. Si intenta instalar la versión de 64 bits de Teams en un sistema operativo de 32 bits, la instalación no se realizará correctamente y no recibirá un mensaje de error.

|Entidad  |32 bits      |64 bits      | ARM64 |
|---------|---------|---------|-----------|
|Comercial     | [32-bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Gobierno de EE. UU. - GCC     | [32-bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64-bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Gobierno de EE. UU. - GCC High    | [32-bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64-bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Gobierno de EE. UU. - DoD     | [32-bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Cómo funciona el archivo MSI de Microsoft Teams

### <a name="pc-installation"></a>Instalación en PC

El MSI de Teams coloca un instalador en `%SystemDrive%\Program Files\Teams Installer` Windows de 32 bits y `%SystemDrive%\Program Files (x86)\Teams Installer` en Windows de 64 bits. Cada vez que un usuario inicia sesión en un nuevo perfil de usuario de Windows, se inicia el instalador y se instala una copia de la aplicación teams en la carpeta de `%LocalAppData%\Microsoft\Teams` ese usuario. Si un usuario ya tiene la aplicación teams instalada en la `%LocalAppData%\Microsoft\Teams` carpeta, el instalador MSI omite el proceso para ese usuario.

Los archivos MSI no se pueden usar para implementar actualizaciones. El cliente de Teams se actualizará automáticamente cuando detecte que hay una nueva versión disponible en el servicio. Para volver a implementar el instalador más reciente, use el proceso de volver a implementar MSI que se describe a continuación. Si implementa una versión anterior del archivo MSI, el cliente se actualizará automáticamente (excepto en entornos VDI) cuando sea posible para el usuario. Si se implementa una versión muy antigua, el MSI iniciará una actualización de la aplicación antes de que el usuario pueda usar Teams.

> [!IMPORTANT]
> No se recomienda cambiar las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización. Si tiene una versión demasiado antigua, se podría bloquear a los usuarios el acceso al servicio.

#### <a name="target-computer-requirements"></a>Requisitos del equipo de destino

Asegúrese de que los equipos en los que instala Teams cumplen los requisitos enumerados en [Requisitos de hardware para Microsoft Teams](hardware-requirements-for-the-teams-app.md).

### <a name="vdi-installation"></a>Instalación en VDI

Para obtener instrucciones detalladas sobre cómo implementar la aplicación de escritorio de Teams en VDI, consulte [Teams para Infraestructura de escritorio virtual](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Procedimiento de limpieza y reimplementación

Si un usuario desinstala Teams de su perfil de usuario, el instalador MSI realizará un seguimiento para comprobar que el usuario ha desinstalado la aplicación Teams y que no vuelve a instalar Teams para ese perfil de usuario. Para volver a implementar Teams para este usuario en un equipo concreto en el que se desinstaló, haga lo siguiente:

> [!IMPORTANT]
> Los siguientes pasos contienen información sobre cómo modificar el registro. Asegúrese de hacer una copia de seguridad del registro antes de modificarlo y de que sabe cómo restaurarlo en caso de que surja un problema. Para más información sobre cómo hacer una copia de seguridad del registro, cómo restaurarlo y modificarlo, consulte [Información del registro de Windows para usuarios avanzados](https://support.microsoft.com/help/256986).

1. Desinstale la aplicación Teams instalada para cada perfil de usuario. Para más información, consulte [Desinstalar Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Elimine el directorio recursivamente en `%LocalAppData%\Microsoft\Teams\` para cada perfil de usuario.
3. Elimine el valor del `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` Registro de cada perfil de usuario.
4. Vuelva a implementar el archivo MSI en ese equipo en particular.

> [!TIP]
> También puede utilizar nuestro [script de limpieza de la implementación de Teams](scripts/powershell-script-deployment-cleanup.md) para completar los pasos 1 y 2.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Evite que Microsoft Teams se inicie automáticamente después de la instalación

El comportamiento predeterminado del MSI es instalar la aplicación Teams en cuanto un usuario inicia sesión y, después, iniciar Teams automáticamente. Si no desea que Teams se inicie automáticamente para los usuarios una vez que se haya instalado, puede usar Directiva de grupo para establecer la configuración de una directiva o deshabilitar el inicio automático para el instalador MSI.

### <a name="use-group-policy-recommended"></a>Usar Directiva de grupo (recomendado)

Active la configuración **Impedir que Microsoft Teams se inicie automáticamente después de la instalación** [directiva de grupo](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software). Encontrará esta configuración de directiva en **Plantillas**\\**administrativas**\\ de Directivas de **configuración**\\ de usuario de **Microsoft Teams**. Este es el método recomendado, ya que puede activar o desactivar la opción de directiva según las necesidades de su organización.

Cuando habilita esta opción de directiva antes de instalar Teams, Teams no se inicia automáticamente cuando el usuario inicia sesión en Windows. Después de que un usuario inicia sesión en Teams por primera vez, Teams se iniciará automáticamente la próxima vez que el usuario inicie sesión.

Para obtener más información, consulte [Usar Directiva de grupo para evitar que Microsoft Teams se inicie automáticamente después de la instalación](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Si ya ha implementado Teams y desea establecer esta directiva para deshabilitar el inicio automático de Teams, en primer lugar, establezca el valor que desee en la opción Directiva de grupo y, a continuación, ejecute la [Secuencia de comandos de restablecimiento de inicio automático de Teams](scripts/powershell-script-teams-reset-autostart.md) para cada usuario.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Deshabilitar el inicio automático del instalador MSI

Puede deshabilitar el inicio automático para el instalador MSI usando el `OPTIONS="noAutoStart=true"` parámetro como se indica a continuación.  

Para la versión de 32 bits:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Para la versión de 64 bits:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Cuando un usuario inicia sesión en Windows, Teams se instala con el MSI. Teams no se iniciará hasta que el usuario inicie manualmente Teams. Después de que el usuario haya iniciado manualmente Teams, Teams se iniciará automáticamente cada vez que el usuario inicie sesión.

Tenga en cuenta que estos ejemplos también utilizan el parámetro **ALLUSERS=1**. Cuando establece este parámetro, el Instalador Teams de todo el equipo aparece en Programas y características y en el Panel de control y en Aplicaciones y características en la Configuración de Windows para todos los usuarios del equipo. Entonces, todos los usuarios podrán desinstalar Teams si cuentan con credenciales de administrador en el equipo.

> [!Note]
> Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados. Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción de deshabilitar el inicio automático.
