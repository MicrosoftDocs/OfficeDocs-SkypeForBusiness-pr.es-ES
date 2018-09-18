---
title: Instalar Microsoft Teams con MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Los administradores pueden usar el MSI de Teams para implementar Microsoft Teams en bloque y poder seleccionar usuarios o equipos.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882041"
---
<a name="install-microsoft-teams-using-msi"></a>Instalar Microsoft Teams con MSI
=================================

Si prefiere usar System Center Configuration Manager, la directiva de grupos o cualquier otro mecanismo de distribución de terceros para llevar a cabo una implementación general, Microsoft ofrece archivos MSI (de [32 bits](https://aka.ms/teams32bitmsi) y [64 bits](https://aka.ms/teams64bitmsi)) que los administradores de Teams pueden usar para seleccionar usuarios u ordenadores. Los administradores pueden usar estos archivos para implementar Teams de forma remota de manera que los usuarios no tengan que descargar manualmente la aplicación de Teams. Una vez que la aplicación se haya implementado, Teams se iniciará automáticamente para todos los usuarios que inicien sesión en esa máquina. Le recomendamos que implemente el paquete en el equipo para que todos los usuarios nuevos de la máquina se beneficien también de esta implementación. 
 
> [!Note] 
> Si desea saber más sobre SCCM, consulte [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimiento de implementación (recomendado)
1. Recupere el paquete más reciente.
2. Use los valores predeterminados que el MSI habrá rellenado previamente.
3. Realice la implementación en ordenadores siempre que sea posible.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Cómo funciona el paquete MSI de Microsoft Teams

El MSI de Teams colocará un programa de instalación en Archivos de programa. Cada vez que un usuario inicie sesión en un nuevo perfil de usuario de Windows, se iniciará el instalador y se instalará una copia de la aplicación de Teams en la carpeta AppData de ese usuario. En el caso de que el usuario ya tenga esta aplicación instalada en esta carpeta, el instalador MSI omitirá el proceso para ese usuario.

No use el MSI para implementar actualizaciones, puesto que el cliente se encargará de actualizar de forma automática cuando detecte una nueva versión del servicio. Para volver a implementar la última versión del instalador, use el proceso que se describe a continuación para implementar de nuevo el MSI. Si implementa una versión anterior del paquete MSI, el cliente se actualizará automáticamente en cuanto pueda el usuario. Si la versión que se implementa es mucho anterior, el MSI activará una actualización de la aplicación antes de que el usuario pueda usar Teams. 

> [!Important] 
> No se recomienda cambiar las ubicaciones predeterminadas para la instalación para evitar que se interrumpa el flujo de actualización. Asimismo, si mantiene una versión demasiado antigua, los usuarios acabarían por no poder acceder al servicio. 


## <a name="target-computer-requirements"></a>Requisitos del ordenador de destino

- .NET Framework 4.5 o posterior
- Windows 7 o posterior
- 3 GB de espacio en disco para cada perfil de usuario (recomendado)

## <a name="clean-up-and-redeployment-procedure"></a>Procedimiento de limpieza y reimplementación
Si un usuario desinstala Teams de su perfil de usuario, el instalador MSI rastreará que el usuario haya desinstalado la aplicación de Teams y que no la haya vuelto a instalar para ese perfil de usuario. Para volver a implementar Teams para este usuario en un ordenador determinado en el que se había desinstalado antes, tiene que hacer lo siguiente:

1. Desinstale la aplicación de Teams que hay instalada para cada perfil de usuario. 
2. Después de desinstalar, elimine el directorio repetidamente en %localappdata%\Microsoft\Teams\. 
3. Vuelva a implementar el paquete MSI en ese ordenador.

> [!TIP] 
> Puede usar nuestro script para [limpieza de implementaciones de Microsoft Teams](.\scripts\Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.                              

