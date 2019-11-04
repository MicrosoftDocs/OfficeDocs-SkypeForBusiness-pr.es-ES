---
title: Instalar Microsoft Teams con MSI (mediante SCCM)
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
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37567963"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar Microsoft Teams con MSI
=================================

> [!Tip]
> Vea la siguiente sesión para obtener información sobre las ventajas del cliente de escritorio de Windows, cómo se planea y cómo se implementa: [Teams cliente de escritorio de Windows](https://aka.ms/teams-clients)

Para usar System Center Configuration Manager, una directiva de grupo o cualquier mecanismo de distribución de terceros para una implementación ampliada, Microsoft ha proporcionado archivos MSI (tanto [de 32](https://aka.ms/teams32bitmsi) bits como de [64](https://aka.ms/teams64bitmsi)bits) que los administradores pueden usar para la implementación masiva de equipos para seleccionar usuarios o equipos. Los administradores pueden usar estos archivos para implementar equipos de forma remota, de modo que los usuarios no tengan que descargar manualmente la aplicación de Teams. Cuando se implementa, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en ese equipo. (Puede deshabilitar el inicio automático después de instalar la aplicación. [Consulte a continuación](#disable-auto-launch-for-the-msi-installer)). Le recomendamos que implemente el paquete en el equipo, de modo que todos los nuevos usuarios del equipo también se beneficien de esta implementación. 

Los equipos también pueden incluirse con una implementación de Office 365 ProPlus. Para obtener más información, consulte [implementar Microsoft Teams con Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).
 
> [!Note] 
> Para obtener más información sobre SCCM, consulte [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimiento de implementación (recomendado)
1. Recuperar el paquete más reciente.
2. Use los valores predeterminados rellenados previamente por el MSI.
3. Implementar en equipos siempre que sea posible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Cómo funciona el paquete MSI de Microsoft Teams

### <a name="pc-installation"></a>Instalación de PC

> [!Note] 
> Vea [instalación de VDI](#vdi-installation) para obtener instrucciones sobre cómo implementar Teams en un entorno de DesktopInfrastructure virtual (VDI).

El MSI de Teams colocará un instalador en archivos de programa. Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación de Teams en la carpeta appdata del usuario. Si un usuario ya tiene la aplicación de Teams instalada en la carpeta appdata, el instalador MSI omitirá el proceso para ese usuario.

No use el MSI para implementar actualizaciones, ya que el cliente se actualizará automáticamente cuando detecte que hay una nueva versión disponible en el servicio. Para volver a implementar el último instalador, use el proceso de reimplementación de MSI que se describe a continuación.Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente (excepto en entornos de VDI) cuando sea posible para el usuario. Si se implementa una versión muy antigua, el MSI desencadenará una actualización de la aplicación antes de que el usuario pueda usar Teams. 

> [!Important] 
> No recomendamos que cambie las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización. Tener una versión demasiado antigua impedirá que los usuarios tengan acceso al servicio. 

#### <a name="target-computer-requirements"></a>Requisitos del equipo de destino

- .NET Framework 4,5 o posterior
- Windows 7 o posterior
- 3 GB de espacio en disco para cada perfil de usuario (recomendado)

### <a name="vdi-installation"></a>Instalación de VDI

Este es el proceso para implementar la aplicación de escritorio de Teams. Para obtener instrucciones detalladas, vea [Teams para infraestructura de escritorio virtualizada](teams-for-vdi.md).

1. Descargue el paquete de MSI de Teams con uno de los siguientes vínculos en función del entorno. Recomendamos la versión de 64 bits para una VM VDI con un sistema operativo de 64 bits.

    - [versión de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versión de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Ejecute el siguiente comando para instalar el MSI en la máquina virtual de VDI (o actualizarlo).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Instala Teams en archivos de programa. En este momento, la configuración de la imagen de oro está completa.

    La siguiente sesión de inicio de sesión interactivo inicia Teams y solicita las credenciales. Tenga en cuenta que no es posible deshabilitar el inicio automático de equipos al instalar Teams en VDI mediante la propiedad ALLUSER.

3. Ejecute el siguiente comando para desinstalar el MSI de la máquina virtual de VDI (o prepararse para actualizarlo).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Esto desinstalará Teams de archivos de programa.

## <a name="clean-up-and-redeployment-procedure"></a>Procedimiento de limpieza y reimplementación

Si un usuario desinstala equipos de su perfil de usuario, el instalador MSI realizará un seguimiento de que el usuario ha desinstalado la aplicación de Teams y ya no instalará Teams para ese perfil de usuario. Para volver a implementar Teams para este usuario en un equipo determinado en el que se ha desinstalado, haga lo siguiente:

1. Desinstalar la aplicación de Teams instalada para todos los perfiles de usuario. 
2. Después de la desinstalación, eliminar el directorio de forma recursiva en%localappdata%\Microsoft\Teams\.
3. Vuelva a implementar el paquete MSI en ese equipo.

> [!TIP] 
> Puede usar nuestro script de limpieza de la [implementación de Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Deshabilitar el inicio automático para el instalador MSI

El comportamiento predeterminado del MSI es instalar el cliente de Teams en cuanto un usuario inicie sesión y, a continuación, inicie automáticamente Teams. Puede modificar este comportamiento con los parámetros siguientes de la siguiente manera:

- Cuando un usuario inicia sesión en Windows, Teams se instalará con el MSI
- Sin embargo, el cliente de Teams no se iniciará hasta que el usuario haya iniciado manualmente Teams
- Se agregará un acceso directo para iniciar Teams en el escritorio del usuario
- Una vez que se inicia manualmente, Teams se inicia automáticamente cuando el usuario inicia sesión

Para la versión de 32 bits
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Para la versión de 64 bits
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Si ejecuta el MSI manualmente, asegúrese de ejecutarlo con permisos elevados. Incluso si lo ejecuta como administrador, sin ejecutarlo con permisos elevados, el instalador no podrá configurar la opción para deshabilitar el inicio automático.
