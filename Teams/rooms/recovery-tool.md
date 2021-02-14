---
title: Usar la herramienta de recuperación de Sala de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que usaría para poner un sistema actualizado en un estado compatible.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021728"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar la herramienta de recuperación de Sala de Microsoft Teams

En este artículo se describe cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que usaría para poner un sistema actualizado en un estado compatible. Esta herramienta debe aplicarse cuando la consola de Salas de Microsoft Teams muestra un error de "configuración del sistema no actualizada" o antes de realizar un restablecimiento de fábrica con el botón [de inserción.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Requisitos previos

Descargue el último paquete de instalación de Salas de Microsoft Teams y [extraigalo](https://go.microsoft.com/fwlink/?linkid=851168) a un Memory Stick USB o a un recurso compartido de red accesible desde el dispositivo Microsoft Teams Rooms.

> [!NOTE]
> La extracción de los archivos desde el MSI se puede conseguir mediante muchos medios. Cualquier mecanismo que extraiga todos los archivos y conserve su estructura de directorios es aceptable. Una de estas maneras es usar el comando donde representa la ruta completa al paquete de instalación de Microsoft Teams Room y representa la ruta de acceso completa a la carpeta a la que quiere extraer los `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` archivos.

## <a name="running-the-tool"></a>Ejecución de la herramienta

1) Inicie sesión en la cuenta de administrador del dispositivo de Salas de Microsoft Teams e inicie un símbolo del sistema con privilegios elevados.
2) Compruebe desde el dispositivo salas de Microsoft Teams el que pueda acceder al archivo que se incluye en los archivos extraídos del paquete de instalación de Salas de `RecoveryTool.ps1 file` Microsoft Teams. El kit puede encontrarse en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.
3) `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`Ejecutar.
4) Para realizar una restauración de fábrica:
   1. Cuando el script se lo solicite, seleccione la opción 2: **Restablecer.**
   2. Si BitLocker está habilitado, sigue las instrucciones proporcionadas al final del resultado del script para deshabilitarlo.
   3. Realizar la restauración de fábrica.
      1. Abra la **aplicación Configuración** y seleccione Actualizar **& Seguridad**
      2. Vaya a la **pestaña Recuperación.**
      3. Debajo **de Restablecer este equipo,** **selecciona Introducción**
      4. Selecciona **Quitar todo,** luego **Siguiente** y **Restablecer**
        > [!WARNING]
        > El dispositivo Salas de Microsoft Teams puede quedar inutilizable si el comando Mantener mis archivos elimina las aplicaciones y la **configuración,** pero mantiene seleccionada la opción de archivos personales durante el proceso de restablecimiento de Windows. No seleccione esta opción.
      5. El sistema se reiniciará varias veces. Cuando se complete el restablecimiento, el sistema estará en la pantalla de Windows "fuera de la caja" (OOBE).



## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
