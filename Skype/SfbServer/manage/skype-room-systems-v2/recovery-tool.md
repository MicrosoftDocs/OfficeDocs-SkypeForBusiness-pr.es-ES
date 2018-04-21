---
title: Utilizar la herramienta de recuperación de sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: En este artículo se describe cómo utilizar la herramienta de recuperación de sistemas de salas de Skype v2, que se pueden utilizar para traer un sistema obsoleto en un estado admitido.
ms.openlocfilehash: 7c7a6188ec1cbd1153c09b768e81789fcffd266e
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>Utilizar la herramienta de recuperación de sistemas de salas de Skype v2
 
En este artículo se describe cómo utilizar la herramienta de recuperación de sistemas de salas de Skype v2, que se pueden utilizar para traer un sistema obsoleto en un estado admitido. Cuando la consola de sistemas de salas de Skype v2 muestra un error "config de sistema obsoleto", se utilizaría esta herramienta.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Requisitos previos

Descargue el último [paquete de instalación de sistemas de salas de Skype v2](https://go.microsoft.com/fwlink/?linkid=851168) y extraerlo a un USB memory stick o recurso compartido accesible para el dispositivo de los sistemas de salas de Skype v2.

También debe instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Comprobar la versión de Windows 

1. Inicio de sesión a una cuenta de administrador yendo a **Configuración > configuración de Windows > Inicio de sesión de administrador en** desde el dispositivo de los sistemas de salas de Skype v2. Esta opción le lleva a la pantalla de inicio de sesión.
2. Inicie una sesión en una cuenta de administrador, el administrador predeterminado cuenta siendo `admin` con la contraseña `sfb`.
3. Haga clic en el menú Inicio y escriba `winver.exe` en el cuadro Buscar y haga clic en **Comando ejecutar* en el resultado.
4. Tome nota del número después de 'Versión' en la segunda línea del panel de información.

>[!NOTE]
>Si la versión que se muestra es 1607 o anterior, siga los pasos en los pasos de <a href="#Windows-up">Windows Update antes de recuperación</a> antes de proceder con los pasos de <a href="#Perform">realizar una recuperación</a> . Si la versión que se muestra es mayor que 1607, siga sólo los pasos de <a href="#Perform">realizar una recuperación</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Actualizar Windows antes de la recuperación (si es necesario)

1. Aún iniciar sesión como un usuario administrador, inicie un símbolo del sistema con privilegios elevados de Powershell.
2. Ejecute el comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Ejecute Windows Update e instale la actualización para Windows 1709.
4. Después de la actualización a 1709 signo completa de nuevo en la cuenta de administrador e instale [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). Se puede realizar la actualización desde el vínculo o mediante Windows Update.
5. De forma opcional, instalar cualquier actualización adicional disponible desde Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Realizar una recuperación

1. Iniciar sesión en la cuenta de administrador en el dispositivo de los sistemas de salas de Skype v2 y, inicie un símbolo del sistema con privilegios elevados.
2. Compruebe desde el dispositivo v2 de sistemas de salas de Skype que es capaz de acceder a la `RecoveryTool.ps1` archivo, que se incluye en los archivos extraídos desde el paquete de instalación de sistemas de salas de Skype v2. El kit se puede encontrar en el recurso compartido de red o una unidad USB utilizado al preparar los requisitos previos.
3. Ejecute el comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4. Cuando se lo pida la opción Seleccionar secuencia de comandos `1:"Repair System"`.
5. Al finalizar, reinicie el dispositivo v2 de sistemas de salas de Skype. Se reiniciará automáticamente otra vez y elaborar totalmente recuperado la segunda vez.



<a name="See"> </a>  
## <a name="see-also"></a>Vea también


#### 

[Administrar espacio de Skype v2 de sistemas](skype-room-systems-v2.md)
#### 
