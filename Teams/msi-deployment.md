---
title: Instalar Microsoft Teams con MSI (mediante SCCM)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Los administradores pueden usar el MSI de Teams para implementar Microsoft Teams en bloque y poder seleccionar usuarios o equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea2f6b85dc4802f2caac4df5b69754d27e8fb9a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33899020"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar Microsoft Teams con MSI
=================================

> [!Tip]
> Vea la sesión para obtener más información acerca de las ventajas del cliente de escritorio de Windows, cómo planear para él y cómo implementarlo siguiente: [Los equipos cliente de escritorio de Windows](https://aka.ms/teams-clients)

Para usar System Center Configuration Manager, o directiva de grupo o los mecanismos de distribución de terceros para amplia implementación, Microsoft ha proporcionado archivos MSI ( [32 bits](https://aka.ms/teams32bitmsi) y [64 bits](https://aka.ms/teams64bitmsi)) que los administradores pueden utilizar para la implementación de forma masiva de los equipos para seleccionar los usuarios o equipos. Los administradores pueden utilizar estos archivos para implementar de forma remota los equipos para que los usuarios no tienen que descargar manualmente la aplicación de los equipos. Cuando se implementa, los equipos automáticamente inicio para todos los usuarios que inician una sesión en ese equipo. (Puede deshabilitar el inicio automático después de instalar la aplicación. [Vea más adelante](#disable-auto-launch-for-the-msi-installer)). Se recomienda que implemente el paquete en el equipo, por lo que todos los nuevos usuarios de la máquina también se beneficiarán de esta implementación. 
 
> [!Note] 
> Para obtener más información acerca de SCCM, vea [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimiento de implementación (recomendado)
1. Recuperar el último paquete.
2. Use los valores predeterminados que se rellena automáticamente por el archivo MSI.
3. Implementar en equipos cuando sea posible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Cómo funciona el paquete MSI de los equipos de Microsoft

### <a name="pc-installation"></a>Instalación de PC

> [!Note] 
> Para obtener instrucciones acerca de cómo implementar los equipos en un entorno de DesktopInfrastructure Virtual (VDI), vea [instalación de VDI](#vdi-installation) .

El archivo MSI de los equipos colocará a un instalador en archivos de programa. Cada vez que un usuario firma en un nuevo perfil de usuario de Windows, se iniciará el programa de instalación y una copia de la aplicación de los equipos que se va a instalar en la carpeta appdata de dicho usuario. Si un usuario ya tiene la aplicación de los equipos instalada en la carpeta appdata, el instalador MSI omitirá el proceso de dicho usuario.

No use el archivo MSI para implementar actualizaciones, debido a que el cliente se actualización automática cuando se detecta que una nueva versión está disponible desde el servicio. Para volver a implementar el programa de instalación más reciente usar el proceso de reimplementación de MSI se describe a continuación.Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente siempre que sea posible para el usuario. Si se implementa una versión muy antigua, el archivo MSI activará una actualización de la aplicación antes de que el usuario se pueden utilizar los equipos. 

> [!Important] 
> No recomendamos que cambiar las ubicaciones de instalación predeterminadas, como esto podría interrumpir el flujo de actualización. Tener una versión demasiado antigua finalmente se bloquearán a los usuarios acceso al servicio. 

#### <a name="target-computer-requirements"></a>Requisitos del equipo de destino

- .NET framework 4.5 o posterior
- Windows 7 o posterior
- 3 GB de espacio en disco para cada perfil de usuario (recomendado)

### <a name="vdi-installation"></a>Instalación de VDI

Aquí es el proceso para implementar la aplicación de escritorio de los equipos. Para obtener instrucciones completas, consulte [los equipos de la infraestructura de escritorio virtualizado](teams-for-vdi.md).

1. Descargar el paquete de MSI de los equipos mediante uno de los siguientes vínculos según el entorno. Se recomienda la versión de 64 bits para una VM de VDI con un sistema operativo de 64 bits.

    - [versión de 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [versión de 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Ejecute el siguiente comando para instalar el archivo MSI en la VM VDI (o completar su actualización).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Este archivo instala los equipos a los archivos de programa. En este momento, la configuración de imagen oro está completa.

    La sesión de inicio de sesión interactivo siguiente inicia los equipos y solicita credenciales. Tenga en cuenta que no es posible deshabilitar el inicio automático de los equipos al instalar los equipos de la VDI mediante la propiedad correspondiente a.

3. Ejecute el siguiente comando para desinstalar el archivo MSI de la VM VDI (o preparar para su actualización).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Esto desinstala los equipos de los archivos de programa.

## <a name="clean-up-and-redeployment-procedure"></a>Limpieza y procedimiento de reimplementación

Si un usuario desinstala los equipos de su perfil de usuario, el instalador MSI realizará el seguimiento que el usuario ha desinstalado la aplicación de los equipos y ya no instalar los equipos para ese perfil de usuario. Para volver a implementar los equipos de este usuario en un equipo concreto donde se ha desinstalado, haga lo siguiente:

1. Desinstalar la aplicación de los equipos instalados para cada perfil de usuario. 
2. Después de la desinstalación, eliminar directorios de forma recursiva en % localappdata%\Microsoft\Teams\.
3. Vuelva a implementar el paquete MSI en dicho equipo.

> [!TIP] 
> Puede usar nuestra secuencia de comandos de [limpieza de implementación de equipos de Microsoft](scripts/Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Deshabilitar el inicio automático para el instalador MSI

Comportamiento predeterminado de MSI es instalar al cliente de los equipos tan pronto como un usuario inicia sesión y, a continuación, iniciar automáticamente los equipos. Puede modificar este comportamiento con los parámetros debajo de la siguiente manera:

- Cuando un usuario inicia sesión en Windows, los equipos se instalará con el archivo MSI
- Sin embargo, no se iniciará el cliente de los equipos hasta que el usuario ha iniciado los equipos manualmente
- Se agregará un acceso directo para iniciar los equipos en el escritorio del usuario
- Una vez que se inicie manualmente, los equipos se inicio automático cada vez que el usuario inicia sesión

Para la versión de 32 bits
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Para la versión de 64 bits
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Si se ejecuta el archivo MSI manualmente, asegúrese de ejecutar con permisos elevados. Incluso si se ejecuta como un administrador, sin ejecutar con permisos elevados, el programa de instalación no podrá configurar la opción para deshabilitar el inicio automático.
