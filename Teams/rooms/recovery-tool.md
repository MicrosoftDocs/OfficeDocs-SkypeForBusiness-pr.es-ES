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
description: En este artículo se explica cómo usar la herramienta de recuperación para salas de Microsoft Teams, que usaría para poner un sistema desa fechado en un estado compatible.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117498"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar la herramienta de recuperación de Sala de Microsoft Teams

En este artículo se explica cómo usar la herramienta de recuperación para salas de Microsoft Teams, que usaría para poner un sistema desa fechado en un estado compatible. Esta herramienta se debe aplicar cuando la consola salas de Microsoft Teams muestra un error "configuración del sistema desconcúe" o antes de realizar una restauración de fábrica de restablecimiento del botón de [inserción.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Requisitos previos

Descargue el paquete de instalación más reciente de Salas de [Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) y descárigalo a una memoria USB o a un recurso compartido de red accesible para el dispositivo Salas de Microsoft Teams.

> [!NOTE]
> La extracción de los archivos del MSI puede realizarse por muchos medios. Cualquier mecanismo que extrae todos los archivos y conserva su estructura de directorios es aceptable. Una de estas maneras es usar el comando en el que se representa la ruta completa al paquete de instalación de Microsoft Teams Room y representa la ruta completa a la carpeta a la que le gustaría extraer `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` los `PathToTarget` archivos.

## <a name="running-the-tool"></a>Ejecutar la herramienta

1) Inicie sesión en la cuenta de administrador en el dispositivo Salas de Microsoft Teams e inicie un símbolo del sistema con privilegios elevados.
2) Compruebe desde el dispositivo Salas de Microsoft Teams que puede acceder al , que se incluye en los archivos extraídos del paquete de instalación salas de `RecoveryTool.ps1 file` Microsoft Teams. El kit se puede encontrar en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.
3) Ejecutar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Para realizar una restauración de fábrica:
   1. Cuando se le solicite por el script, seleccione la opción 2: **Restablecer**.
   2. Si BitLocker está en, siga las instrucciones proporcionadas al final de la salida del script para deshabilitarlo.
   3. Realice la restauración de fábrica.
      1. Abra la **aplicación Configuración** y seleccione Actualizar **& seguridad**
      2. Vaya a la **pestaña Recuperación.**
      3. Debajo **de Restablecer este equipo,** selecciona **Introducción**
      4. Selecciona **Quitar todo** y, a **continuación, Siguiente** y **Restablecer**
        > [!WARNING]
        > El dispositivo Salas de Microsoft Teams puede quedar inutilizable si la opción Mantener mis **archivos:** quita aplicaciones y configuraciones, pero mantiene seleccionada la opción archivos personales durante el proceso de restablecimiento de Windows. No seleccione esta opción.
      5. El sistema se reiniciará varias veces. Cuando se complete el restablecimiento, el sistema estará en la pantalla "experiencia de fuera de la caja" (OOBE) de Windows.



## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)