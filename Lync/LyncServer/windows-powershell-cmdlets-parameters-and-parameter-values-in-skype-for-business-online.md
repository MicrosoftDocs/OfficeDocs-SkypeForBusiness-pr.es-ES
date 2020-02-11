---
title: Cmdlets, parámetros y valores de parámetros de Windows PowerShell en Skype empresarial online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9fadf59b353458b2e7c48f597c11b92342e7edc
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Cmdlets, parámetros y valores de parámetros de Windows PowerShell en Skype empresarial online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-05_

Si está familiarizado con la ventana de comandos que se encuentra en todas las versiones de Windows (o si está familiarizado con MS-DOS), tendrá una ventaja cuando se trata de aprender a usar Windows PowerShell. En la ventana de comandos, escriba un comando y presione Entrar. En respuesta, el equipo ejecuta un comando o un archivo ejecutable. Por ejemplo, para obtener información acerca de todos los archivos y carpetas en el directorio actual, escriba este comando en el símbolo del sistema y, a continuación, presione ENTRAR:

```console
dir
```

A su vez, obtendrá información sobre todos los archivos y carpetas en el directorio actual:

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Es un ejemplo de resultado cuando solo escribe el nombre de un comando o un archivo ejecutable. Sin embargo, muchos de los comandos que se ejecutan desde la ventana de comandos también aceptan *argumentos*. Los argumentos son datos adicionales que se pasan al comando, que modifican el comportamiento del comando. Por ejemplo, si solo desea ver los nombres de los archivos y la carpeta en el directorio actual, sin otra información, como el tamaño del archivo o la carpeta, o la fecha y la hora en que se creó la carpeta o carpeta. En este caso, debe anexar el argumento **/b** al ejecutar el comando dir:

```console
dir /b
```

Si incluye el argumento **/b** , el comando **dir** devolverá solo los nombres de las carpetas y archivos que se encuentren en el directorio actual:

```console
Deploy
Intel
PerfLogs
Program Files
Program Files (x86)
Users
Windows
pldok.log
RHDSetup.exe
setup.doc
```

En el comando anterior, el argumento **/b** es la única información necesaria para limitar los datos devueltos a los nombres de archivo y carpeta. Esto suele ser el caso de los comandos de la línea de comandos: la mera presencia de un argumento es todo lo que se necesita para cambiar el comportamiento del comando. (Es decir, se incluye el argumento **/b** para ocultar información adicional o se excluye el argumento **/b** para mostrar la información adicional). En otras ocasiones, sin embargo, debe especificar un *valor de argumento*. Un valor de argumento es información adicional que se pasa al propio argumento. Por ejemplo, el argumento **/o** le permite especificar cómo desea que el comando dir ordene los datos devueltos. Entre otras opciones, puede usar el valor del argumento **e** para ordenar por extensión de archivo o el valor del argumento **s** para ordenar por tamaño de archivo. Por ejemplo, este comando ordena los datos devueltos por extensión de archivo. Observe cómo se incluye el valor del argumento **e** inmediatamente después del argumento **/o** :

```console
dir /oe
```

Con nuestra carpeta de ejemplo, los datos devueltos tendrán el siguiente aspecto, con los archivos ordenados alfabéticamente por extensión de archivo:

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

O bien, para ayudarle a determinar exactamente con qué estamos hablando:

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Aunque Windows PowerShell usa terminología diferente, el enfoque básico para trabajar con Windows PowerShell es el mismo que trabajar con la ventana de comandos: escriba comandos, incluya los argumentos y valores de argumento según sea necesario y, a continuación, presione Entrar para ejecutar esos comandos. Como se indicó, Windows PowerShell sí usa una terminología diferente a la que usa el shell de comandos. En Windows PowerShell, los comandos que ejecuta se conocen como *cmdlets*. A su vez, los argumentos que se pasan a un cmdlet se conocen como *parámetros*y los valores que se pasan a un parámetro se conocen como *valores de parámetro*.

Las definiciones anteriores son ligeramente simplificadas. Los cmdlets son esencialmente miniaplicaciones que solo se pueden ejecutar desde el entorno de Windows PowerShell. Sin embargo, también puede ejecutar otros comandos y aplicaciones en Windows PowerShell, incluidos la mayoría de los comandos y las aplicaciones que se pueden ejecutar desde una ventana de comandos. Por ejemplo, si desea iniciar el Bloc de notas desde Windows PowerShell, todo lo que debe hacer es escribir lo siguiente y presionar entrar:

```console
notepad.exe
```

Sin embargo, cuando se trata de administrar Skype empresarial online, la mayoría de los administradores depende de los cmdlets de Windows PowerShell para llevar a cabo tareas administrativas. En la fecha, hay muy pocos tipos de comandos o aplicaciones que se pueden usar para administrar Skype empresarial online. A veces, los cmdlets de Skype empresarial online se pueden usar sin ningún argumento adicional (como se indica, los argumentos se conocen como parámetros en Windows PowerShell). Por ejemplo, el siguiente comando llama al cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) sin ningún parámetro adicional. Por sí mismo, el comando devuelve información sobre todos los usuarios de Skype empresarial online:

```powershell
Get-CsOnlineUser
```

Sin embargo, la mayoría de los cmdlets de Skype empresarial online también aceptan parámetros (y valores de parámetros). Considere el siguiente comando:

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

Este comando consta de tres partes:

  - El cmdlet **Get-CsOnlineUser**.

  - El parámetro Identity. Tenga en cuenta que, en Windows PowerShell, los parámetros siempre están precedidos por un guión (-). Eso significa que, para este mismo cmdlet, el parámetro UnassignedUser se indicaría con esta sintaxis:
    
    ```powershell
    -UnassignedUser
    ```
    
    Esto es útil para saber, no solo porque los parámetros deben ir precedidos por un guión, sino también porque esto difiere de la ventana de comandos, donde los argumentos están precedidos con una barra diagonal (/):
    
    ```console
    /b
    ```

  - El valor de parámetro **kenmyer@litwareinc.com**.

Ese comando, por cierto, devuelve información acerca de un usuario específico: el usuario con la identidad kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Vea también


[Una introducción a Windows PowerShell y Skype Empresarial Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

