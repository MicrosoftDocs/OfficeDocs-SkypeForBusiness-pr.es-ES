---
title: Utilizar la herramienta de recuperación de sistemas de salón de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este artículo se describe cómo usar la herramienta de recuperación para sistemas de salón de Skype v2, que se pueden utilizar para incorporar un sistema caducado en un estado admitido.
ms.openlocfilehash: fd71fc189b7471e4e315b6602014a967be09f9c0
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>Utilizar la herramienta de recuperación de sistemas de salón de Skype v2
 
En este artículo se describe cómo usar la herramienta de recuperación para sistemas de salón de Skype v2, que se pueden utilizar para incorporar un sistema caducado en un estado admitido. ¿Utilizar esta herramienta cuando la consola de v2 de sistemas de salón de Skype muestra un error "sistema config caducada".
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Requisitos previos

Descargue el último [paquete de instalación de sistemas de salón de Skype v2](https://go.microsoft.com/fwlink/?linkid=851168) y extraer a un USB memoria pincel recurso compartido de red accesible para el dispositivo de v2 de sistemas de salón de Skype.

También es posible que necesite instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Comprobar la versión de Windows 

1. Inicio de sesión a una cuenta de administrador, vaya a **Configuración > configuración de Windows > Administrador de inicio de sesión en** desde el dispositivo v2 de sistemas de salón de Skype. Esta opción le lleva a la pantalla de inicio de sesión.
2. Cuenta de inicio de sesión a una cuenta de administrador, el administrador predeterminado bienestar `admin` con la contraseña `sfb`.
3. Haga clic en el menú Inicio y el tipo `winver.exe` en el cuadro de búsqueda y haga clic en **Run Command* en el resultado.
4. Tome nota del número después de 'Versión' en la segunda línea del panel de información.

>[!NOTE]
>Si la versión que se muestra es 1607 o anterior, siga los pasos descritos en los pasos de <a href="#Windows-up">Actualización de Windows antes de recuperación</a> antes de comenzar a los pasos de <a href="#Perform">realizar una recuperación</a> . Si la versión que se muestra es mayor que 1607, siga sólo los pasos de <a href="#Perform">realizar una recuperación</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Actualizar Windows antes de la recuperación (si es necesario)

1. Mientras sigue iniciado sesión como un usuario con permisos de administrador, inicie un símbolo del sistema con privilegios elevados de Powershell.
2. Ejecute el comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Ejecute Windows Update e instale la actualización de Windows 1709.
4. Después de la actualización a 1709 inicio de sesión completo de nuevo en la cuenta de administrador e instale [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). Se puede realizar la actualización desde el vínculo o mediante Windows Update.
5. Como un paso opcional, instale las actualizaciones adicionales disponibles desde Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Realizar una recuperación

1. Inicie sesión en la cuenta de administrador en su dispositivo de sistemas de salón de Skype v2 y, inicie un símbolo del sistema con privilegios elevados.
2. Compruebe desde el dispositivo v2 de Skype salón sistemas que pueden tener acceso a la `RecoveryTool.ps1` archivo, que se incluye en los archivos extraídos desde el paquete de instalación de sistemas de salón de Skype v2. El kit de puede encontrarse en el recurso compartido de red o una unidad USB utilizado al preparar los requisitos previos.
3. Ejecute el comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4. Cuando se le solicite mediante la opción Seleccionar de secuencia de comandos `1:"Repair System"`.
5. Al finalizar, reinicie el dispositivo de v2 de sistemas de salón de Skype. Se reiniciará automáticamente nuevo y surgen recuperado totalmente la segunda vez.



<a name="See"> </a>  
## <a name="see-also"></a>Vea también


#### 
[Ayuda de la versión 2 de sistemas de salón de Skype](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administración de salón de Skype v2 de sistemas](skype-room-systems-v2.md)
#### 
