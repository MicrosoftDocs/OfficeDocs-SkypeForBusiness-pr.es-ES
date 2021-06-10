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
description: En este artículo se explica cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que se usaría para poner un sistema des actualizado en un estado compatible.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117498"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar la herramienta de recuperación de Sala de Microsoft Teams

En este artículo se explica cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que se usaría para poner un sistema des actualizado en un estado compatible. Esta herramienta se debe aplicar cuando la consola Salas de Microsoft Teams muestra un error "configuración del sistema desconcúe" o antes de realizar una restauración de fábrica de restablecimiento del botón de [inserción.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Requisitos previos

Descargue el último [Salas de Microsoft Teams de](https://go.microsoft.com/fwlink/?linkid=851168) instalación y extraigalo a una memoria USB o a un recurso compartido de red accesible para Salas de Microsoft Teams dispositivo.

> [!NOTE]
> La extracción de los archivos del MSI puede realizarse por muchos medios. Cualquier mecanismo que extrae todos los archivos y conserva su estructura de directorios es aceptable. Una de estas maneras es usar el comando en el que se representa la ruta de acceso completa al paquete de instalación de sala de Microsoft Teams y representa la ruta de acceso completa a la carpeta a la que le gustaría extraer los `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` archivos.

## <a name="running-the-tool"></a>Ejecutar la herramienta

1) Inicie sesión en la cuenta de administrador en Salas de Microsoft Teams dispositivo e inicie un símbolo del sistema con privilegios elevados.
2) Compruebe desde el Salas de Microsoft Teams dispositivo al que puede obtener acceso , que se incluye en los archivos extraídos del Salas de Microsoft Teams `RecoveryTool.ps1 file` de instalación. El kit se puede encontrar en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.
3) Ejecutar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Para realizar una restauración de fábrica:
   1. Cuando se le solicite por el script, seleccione la opción 2: **Restablecer**.
   2. Si BitLocker, siga las instrucciones proporcionadas al final de la salida del script para deshabilitarlo.
   3. Realice la restauración de fábrica.
      1. Abra la **Configuración** y seleccione **Actualizar & seguridad**
      2. Vaya a la **pestaña Recuperación.**
      3. Debajo **de Restablecer este equipo,** selecciona **Introducción**
      4. Selecciona **Quitar todo** y, a **continuación, Siguiente** y **Restablecer**
        > [!WARNING]
        > El Salas de Microsoft Teams puede quedar inutilizable si la opción Mantener mis archivos: quita las aplicaciones y la **configuración,** pero mantiene la opción de archivos personales seleccionada durante el proceso de Windows restablecer. No seleccione esta opción.
      5. El sistema se reiniciará varias veces. Cuando se complete el restablecimiento, el sistema estará en la Windows "experiencia de fuera de la caja" (OOBE).



## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)