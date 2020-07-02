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
description: En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021728"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar la herramienta de recuperación de Sala de Microsoft Teams

En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible. Esta herramienta se debe aplicar cuando la consola de Microsoft Team Rooms muestra el error "configuración del sistema fuera de la fecha" o antes de realizar un botón de [inserción.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Requisitos previos

Descargue el [paquete de instalación de Microsoft Team Rooms](https://go.microsoft.com/fwlink/?linkid=851168) más reciente y extráigalo en un Memory stick USB o en un recurso compartido de red accesible para el dispositivo de salas de Microsoft Teams.

> [!NOTE]
> La extracción de los archivos desde el MSI puede hacerse con muchos medios. Cualquier mecanismo que extrae todos los archivos y conserva su estructura de directorios es aceptable. Una de estas maneras es usar el comando `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` donde `PathToMsi` representa la ruta de acceso completa al paquete de instalación de Microsoft Teams Room y `PathToTarget` representa la ruta de acceso completa de la carpeta en la que desea que se extraigan los archivos.

## <a name="running-the-tool"></a>Ejecutar la herramienta

1) Inicie sesión en la cuenta de administrador en el dispositivo de salas de Microsoft Teams e inicie un símbolo del sistema con privilegios elevados.
2) Compruebe en el dispositivo de salas de Microsoft Teams a la que tiene acceso el `RecoveryTool.ps1 file` , que está incluido en los archivos extraídos del paquete de instalación de Microsoft Teams Rooms. El kit puede encontrarse en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.
3) Ejecutar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Para realizar una restauración de fábrica:
   1. Cuando el script le solicite, seleccione la opción 2: **restablecer**.
   2. Si BitLocker está activado, siga las instrucciones que se proporcionan al final de la salida del script para deshabilitarlo.
   3. Realice la restauración de fábrica.
      1. Abra la aplicación **configuración** y seleccione **Actualizar & seguridad** .
      2. Vaya a la pestaña **recuperación** .
      3. Debajo de **restablecer este equipo**, **Seleccione introducción**
      4. Seleccione **quitar todo**y, a continuación, **siguiente** y **restablecer**
        > [!WARNING]
        > El dispositivo de salas de Microsoft Teams puede quedar inutilizable si la opción **mantener mis archivos: quita las aplicaciones y la configuración, pero mantiene su opción de archivos personales** seleccionada durante el proceso de restablecimiento de Windows. No seleccione esta opción.
      5. El sistema se reiniciará varias veces. Cuando se complete el restablecimiento, el sistema estará en la pantalla "experiencia de Windows" (OOBE).



## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
