---
title: Usar la herramienta de recuperación de Sala de Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible.
ms.openlocfilehash: 04fd6b4b0786cffb4f1bb050a7b0bbdac8e2e653
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573654"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar la herramienta de recuperación de Sala de Microsoft Teams
 
En este artículo se describe cómo usar la herramienta de recuperación para salas de Microsoft Teams, que se usaría para poner un sistema obsoleto en un estado compatible. Usaría esta herramienta cuando la consola de Microsoft Teams Rooms muestre el error "configuración de sistema no actualizado".
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Requisitos previos

Descargue el [paquete de instalación de Microsoft Team Rooms](https://go.microsoft.com/fwlink/?linkid=851168) más reciente y extráigalo en un Memory stick USB o en un recurso compartido de red accesible para el dispositivo de salas de Microsoft Teams.

Es posible que también tenga que instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Comprobar la versión de Windows 

1. Inicie sesión en una cuenta de administrador yendo a **configuración> configuración de Windows> iniciar sesión en** el dispositivo de salas de Microsoft Teams. Esta opción te lleva a la pantalla de inicio de sesión.
2. Inicie sesión en una cuenta de administrador, la cuenta de `admin` administrador predeterminada con `sfb`la contraseña.
3. Haga clic en el menú Inicio y `winver.exe` escriba en el cuadro de búsqueda y haga clic en el*comando * ejecutar* en el resultado.
4. Anote el número que hay después de ' versión ' en la segunda línea del panel de información.

>[!NOTE]
>Si la versión mostrada es 1607 o anterior, siga los pasos que se indican en los pasos de <a href="#Windows-up">actualización de Windows antes</a> de la recuperación antes de <a href="#Perform">llevar a cabo una recuperación</a> . Si la versión mostrada es mayor que 1607, siga los pasos que se indican en <a href="#Perform">realizar una recuperación</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Actualizar Windows antes de la recuperación (si es necesario)

1. Mientras está conectado como usuario administrador, inicie un símbolo del sistema de PowerShell con privilegios elevados.
2. Ejecute el comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Ejecute Windows Update e instale la actualización de Windows 1709.
4. Una vez completada la actualización a 1709, vuelva a iniciar sesión en la cuenta de administrador e instale [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). La actualización puede realizarse desde el vínculo o mediante Windows Update.
5. Como paso opcional, instale las actualizaciones adicionales disponibles en Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Realizar una recuperación

1. Inicie sesión en la cuenta de administrador en el dispositivo de salas de Microsoft Teams e inicie un símbolo del sistema con privilegios elevados.
2. Compruebe en el dispositivo salas de Microsoft teams que tiene acceso al `RecoveryTool.ps1` archivo, que está incluido en los archivos extraídos del paquete de instalación salas de Microsoft Teams. El kit puede encontrarse en el recurso compartido de red o en la unidad USB que se usa al preparar los requisitos previos.
3. Ejecute el comando `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.
4. Cuando se le solicite mediante la opción de `1:"Repair System"`la secuencia de comandos, seleccione.
5. Al finalizar, reinicie el dispositivo de salas de Microsoft Teams. Se reiniciará de nuevo automáticamente y se recargará por completo la segunda vez.



<a name="See"> </a>  
## <a name="see-also"></a>Vea también
 
[Ayuda de Salas de Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)
