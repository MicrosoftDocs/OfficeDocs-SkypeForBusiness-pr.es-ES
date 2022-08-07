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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: En este artículo se describe cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que usarías para poner un sistema obsoleto en un estado admitido.
ms.openlocfilehash: c50b59ff4ed1ee997b990b0776ef4a7ee0ac29c2
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271165"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar la herramienta de recuperación de Sala de Microsoft Teams

En este artículo se describe cómo usar la herramienta de recuperación para Salas de Microsoft Teams, que usarías para poner un sistema obsoleto en un estado admitido. Esta herramienta se debe aplicar cuando la consola de Salas de Microsoft Teams muestra un error "configuración del sistema obsoleta" o antes de realizar una [restauración de fábrica](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore) de restablecimiento rápido.

## <a name="prerequisites"></a>Requisitos previos

Descarga el [paquete de instalación de Salas de Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) más reciente y descárgalo en un memory stick USB o en un recurso compartido de red accesible para Salas de Microsoft Teams.

> [!NOTE]
> Extraer los archivos del MSI puede lograrse por muchos medios. Es aceptable cualquier mecanismo que extraiga todos los archivos y conserve su estructura de directorios. Una de estas formas es usar el comando `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` donde `PathToMsi` representa la ruta de acceso completa al paquete de instalación de Salas de Microsoft Teams y `PathToTarget` representa la ruta de acceso completa a la carpeta a la que desea extraer los archivos.

## <a name="running-the-tool"></a>Ejecutar la herramienta

1) Inicia sesión en la cuenta de administrador de tu dispositivo Salas de Microsoft Teams e inicia un símbolo del sistema con privilegios elevados.
2) Comprueba desde el dispositivo Salas de Microsoft Teams que puedes acceder `RecoveryTool.ps1` al archivo, que se incluye en los archivos extraídos del paquete de instalación Salas de Microsoft Teams. El kit puede encontrarse en el recurso compartido de red o la unidad USB que se usa al preparar los requisitos previos.
3) Ejecuta `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Para realizar una restauración de fábrica:
   1. Cuando el script se lo solicite, seleccione la opción 2: **Restablecer**.
   2. Si BitLocker está activado, sigue las instrucciones proporcionadas al final del resultado del script para deshabilitarlo.
   3. Realice la restauración de fábrica.
      1. Abre la aplicación **Configuración** y selecciona **Actualizar & Seguridad**
      2. Ve a la pestaña **Recuperación** .
      3. Debajo de **Restablecer este PC**, selecciona **Comenzar**
      4. Selecciona **Quitar todo** y, a continuación, **Siguiente** y **Restablecer**
        > [!WARNING]
        > El dispositivo Salas de Microsoft Teams puede dejar de usarse si la opción **Mantener mis archivos: quita aplicaciones y configuración, pero mantiene tus archivos personales**, está seleccionada durante el proceso de restablecimiento de Windows. No seleccione esta opción.
      5. El sistema se reiniciará varias veces. Una vez completado el restablecimiento, el sistema estará en la pantalla "Configuración rápida" (OOBE) de Windows.



## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
