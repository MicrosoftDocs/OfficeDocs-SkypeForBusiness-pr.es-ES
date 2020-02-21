---
title: Ejecutar LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4c7d7de6dcb2f2eee15e7da0809dd6e3c41e07
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>Ejecutar LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

Antes de ejecutar la herramienta stress and performance de Lync Server 2013 (LyncPerfTool. exe), debe crear usuarios, contactos y escenarios. Para obtener información detallada acerca del uso de las herramientas para realizar estas acciones, consulte [Create Users and Contacts](create-users-and-contacts.md) y [Configure User Profile](configure-user-profile.md). Al ejecutar estas herramientas, también se generará un archivo que ejecutará LyncPerfTool. exe como parte de un archivo por lotes con los parámetros necesarios incluidos.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Ejecución de la herramienta de esfuerzo y rendimiento de Lync Server 2013

La herramienta UserProfileGenerator. exe crea un archivo por lotes que permite ejecutar LyncPerfTool. exe mediante el registro de los contadores de rendimiento de LyncPerfTool y la carga del archivo de configuración XML. El archivo por lotes ejecuta una instancia de LyncPerfTool. exe por cada archivo de configuración. Para ejecutar el archivo por lotes, haga lo siguiente:

1.  Copie la carpeta que contiene los archivos y las carpetas de configuración en el directorio que contiene LyncStressTool. exe en cada equipo cliente. (Por ejemplo, si ha generado los archivos de configuración en la carpeta denominada\_1,28 13.16.16, copie esa carpeta a la carpeta que contiene LyncPerfTool. exe en cada cliente).

2.  Navegue a la carpeta del cliente con el número adecuado y ejecute el script por lotes RunClient. Puede simplemente hacer doble clic en el archivo por lotes en el explorador de Windows y ejecutará todos los archivos de configuración de ese número de cliente. También puede ejecutar el script desde la carpeta del cliente correspondiente mediante la siguiente sintaxis:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Para ejecutar LyncPerfTool. exe directamente, abra un símbolo del sistema y, a continuación, escriba el comando siguiente en la línea de comandos (cuando haga esto por primera vez, asegúrese de registrar los contadores de rendimiento regsvr32/i/n/s LyncPerfToolPerf. dll, tal y como se muestra en la nota más adelante en este tema\<): LyncPerfTool. exe/File: configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Para que la herramienta muestre los valores en el archivo de configuración, incluya el parámetro/displayfile en el comando anterior, como se muestra a continuación:
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Para finalizar el proceso, presione Ctrl + C.

<div>


> [!NOTE]  
> Antes de ejecutar LyncPerfTool directamente, debe registrar los contadores de rendimiento. Escriba el siguiente comando para registrar los contadores de rendimiento:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Cada instancia de LyncPerfTool. exe que inicie iniciará inmediatamente la sesión de los usuarios, normalmente a una tasa de un usuario por segundo. La frecuencia máxima de inicio de sesión de usuario para el grupo es de unos 12 por segundo. Esto significa que no debe iniciar más de 12 instancias de LyncPerfTool al mismo tiempo, mientras los usuarios aún están iniciando sesión. 1000 los usuarios tardarán unos 20 minutos en iniciar sesión por completo, a una por segundo.



</div>

</div>

<div>

## <a name="see-also"></a>Consulta también


[Crear usuarios y contactos](create-users-and-contacts.md)  
[Configurar el perfil de usuario](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

