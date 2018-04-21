---
title: Instalar Microsoft Teams que usan MSI
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Los administradores pueden utilizar el MSI de equipos a granel implementar Microsoft Teams para seleccionar usuarios o equipos.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8d1f8b77b4b362b95fb03d3f0202bfc6da619e8
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
<a name="install-microsoft-teams-using-msi"></a>Instalar Microsoft Teams que usan MSI
===========================================

Para usar System Center Configuration Manager, o directiva de grupo o cualquier mecanismos de distribución parte 3ª de amplia distribución, Microsoft ha proporcionado archivos MSI ( [32 bits](http://aka.ms/teams32bitmsi) y [64 bits](http://aka.ms/teams64bitmsi)) que pueden utilizar administradores para la implementación masiva de equipos para seleccionar los usuarios o equipos. Administradores pueden utilizar estos archivos para desplegar de forma remota los equipos para que los usuarios no tienen que descargar manualmente los equipos de la aplicación. Cuando se implementa, equipos auto inicio para todos los usuarios iniciar una sesión en ese equipo. Se recomienda implementar el paquete en el equipo, por lo que todos los usuarios nuevos del equipo también se beneficiarán de esta implementación. 
 
> [!Note] 
> Para obtener más información acerca de SCCM, vea [Introducción a System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Procedimiento de implementación (recomendado)
1. Recuperar el paquete más reciente
2. Utilice los valores predeterminados rellenadas previamente por MSI
3. Implementar en equipos cuando sea posible

## <a name="how-the-microsoft-teams-msi-package-works"></a>Cómo funciona el paquete MSI de equipos de Microsoft

El MSI de equipos colocará a un instalador en archivos de programa. Cada vez que un usuario cierre la sesión en un perfil de usuario de Windows, se iniciará el instalador y una copia de la aplicación de los equipos se instalarán en la carpeta de appdata del usuario. Si un usuario ya ha instalado en la carpeta appdata de la aplicación de los equipos, el instalador MSI omitirá el proceso para ese usuario.

Utilizar el archivo MSI para implementar actualizaciones, el cliente se actualización automática cuando se detecta que una nueva versión está disponible en el servicio. Para volver a implementar el programa de instalación más reciente utilice el proceso de reimplementación de MSI que se describe a continuación. Si implementa una versión anterior del paquete de MSI, el cliente se actualizará automáticamente siempre que sea posible para el usuario. Si se implementa una versión muy antigua, el archivo MSI activará una actualización de la aplicación antes de que el usuario es capaz de utilizar los equipos. 

> [!Important] 
> No recomendamos que cambie las ubicaciones de instalación predeterminadas, ya que esto podría interrumpir el flujo de actualización. Tener una versión demasiado antigua eventualmente bloqueará a los usuarios tengan acceso al servicio. 


## <a name="target-machine-requirements"></a>Requisitos del equipo de destino

1. .NET framework 4.5 o posterior
2. Windows 7 o posterior
2. 3GB de espacio en disco para cada perfil de usuario (recomendado)

## <a name="clean-up-and-redeployment-procedure"></a>Limpiar arriba y reimplementación de procedimiento
Si un usuario desinstala los equipos de su perfil de usuario, el instalador MSI realizará el seguimiento que el usuario ha desinstalado la aplicación de los equipos y ya no instalar equipos para dicho perfil de usuario. Para volver a implementar los equipos para este usuario en un equipo concreto donde se desinstaló, haga lo siguiente:

1. Desinstalar la aplicación de los equipos instalados para cada perfil de usuario 
2. Después de la desinstalación, elimine los directorios de forma recursiva en %localappdata%\Microsoft\Teams\ 
3. Implementar el paquete MSI a ese equipo

> [!TIP] 
> Puede utilizar nuestra secuencia de comandos de [limpiar la implementación de equipos de Microsoft](.\scripts\Powershell-script-teams-deployment-clean-up.md) para llevar a cabo los pasos 1 y 2 a través de SCCM.                              

