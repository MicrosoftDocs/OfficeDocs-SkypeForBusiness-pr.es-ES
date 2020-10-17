---
title: Cmdlets, parámetros y valores de parámetros de Windows PowerShell en Skype empresarial online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ad45c9deecf364c273ff64e939c4379d169f3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499967"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Cmdlets, parámetros y valores de parámetros de Windows PowerShell en Skype empresarial online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-05_

Si está familiarizado con la ventana de comandos que se encuentra en todas las versiones de Windows (o si está familiarizado con MS-DOS), tendrá una ventaja para aprender a usar Windows PowerShell. En la ventana de comandos, escriba un comando y presione Entrar. En respuesta, el equipo ejecuta un comando o un archivo ejecutable. Por ejemplo, para devolver información acerca de todos los archivos y carpetas del directorio actual, escriba este comando en el símbolo del sistema y, a continuación, presione ENTRAR:

```console
dir
```

A su vez, obtiene información sobre todos los archivos y carpetas del directorio actual:

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

Este es un ejemplo de un resultado cuando solo escribe el nombre de un comando o un archivo ejecutable. Sin embargo, muchos de los comandos que se ejecutan desde la ventana de comandos también aceptan *argumentos*. Los argumentos son datos adicionales de información que se pasan al comando, que modifican el comportamiento del comando. Por ejemplo, si solo deseaba ver los nombres de los archivos y la carpeta en el directorio actual, sin otra información, como el tamaño del archivo o la carpeta, o la fecha y la hora en que se creó la carpeta o carpeta. En este caso, anexaría el argumento **/b** cuando ejecutaba el comando dir:

```console
dir /b
```

Cuando se incluye el argumento **/b** , el comando **dir** sólo devuelve los nombres de las carpetas y los archivos encontrados en el directorio actual:

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

En el comando anterior, el argumento **/b** es la única información necesaria para limitar los datos devueltos a los nombres de archivo y carpeta. Suele ser el caso de los comandos de la línea de comandos: la mera presencia de un argumento es todo lo que se necesita para cambiar el comportamiento del comando. (Es decir, se incluye el argumento **/b** para ocultar información adicional o se excluye el argumento **/b** para mostrar la información adicional). En otras ocasiones, sin embargo, debe especificar un *valor de argumento*. Un valor de argumento es información adicional que se pasa al propio argumento. Por ejemplo, el argumento **/o** le permite especificar cómo desea que el comando dir ordene los datos devueltos. Entre otras opciones, puede usar el valor de argumento **e** para ordenar por extensión de archivo o por el valor del argumento **s** para ordenar por tamaño de archivo. Por ejemplo, este comando ordena los datos devueltos por extensión de archivo. Tenga en cuenta que el valor del argumento **e** se incluye inmediatamente después del argumento **/o** :

```console
dir /oe
```

Mediante nuestra carpeta de ejemplo, los datos devueltos tendrán el siguiente aspecto, con los archivos ordenados alfabéticamente por extensión de archivo:

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

O bien, para ayudarle a identificar exactamente lo que estamos hablando:

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Aunque Windows PowerShell usa terminología diferente, el enfoque básico para trabajar con Windows PowerShell es el mismo que cuando se trabaja con la ventana de comandos: los comandos se escriben, se incluyen los argumentos y los valores de argumento según sea necesario y, a continuación, se presiona Entrar para ejecutar dichos comandos. Como se indicó, Windows PowerShell usa una terminología diferente a la utilizada por el shell de comandos. En Windows PowerShell, los comandos que ejecuta se denominan *cmdlets*. A su vez, los argumentos pasados a un cmdlet se conocen como *parámetros*y los valores pasados a un parámetro se conocen como *valores de parámetro*.

Las definiciones anteriores se han simplificado en cierta medida. Los cmdlets son esencialmente Mini-aplicaciones que solo se pueden ejecutar desde el entorno de Windows PowerShell. Sin embargo, también puede ejecutar otros comandos y aplicaciones desde Windows PowerShell, incluidos la mayoría de los comandos y aplicaciones que se pueden ejecutar desde una ventana de comandos. Por ejemplo, si desea iniciar el Bloc de notas desde Windows PowerShell, todo lo que necesita hacer es escribir lo siguiente y presionar entrar:

```console
notepad.exe
```

Sin embargo, cuando se trata de administrar Skype empresarial online, la mayoría de los administradores confiarán en los cmdlets de Windows PowerShell para llevar a cabo tareas administrativas. A la vez, hay muy pocos tipos de comandos o aplicaciones que se pueden usar para administrar Skype empresarial online. A veces, los cmdlets de Skype empresarial online pueden usarse sin argumentos adicionales (como se indica, los argumentos se conocen como parámetros en Windows PowerShell). Por ejemplo, el siguiente comando llama al cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) sin ningún parámetro adicional. Por sí mismo, el comando devuelve información sobre todos los usuarios de Skype empresarial online:

```powershell
Get-CsOnlineUser
```

Sin embargo, la mayoría de los cmdlets de Skype empresarial online también aceptan parámetros (y valores de parámetro). Considere el siguiente comando:

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

Este comando consta de tres partes:

  - El cmdlet **Get-CsOnlineUser**.

  - Parámetro Identity. Tenga en cuenta que, en Windows PowerShell, los parámetros siempre están precedidos de un guión (-). Esto significa que, para este mismo cmdlet, el parámetro UnassignedUser se indicaría con esta sintaxis:
    
    ```powershell
    -UnassignedUser
    ```
    
    Esto es útil para saber, no solo porque los parámetros deben ir precedidos por un guión, sino también porque esto difiere de la ventana de comandos, donde los argumentos están precedidos mediante una barra diagonal (/):
    
    ```console
    /b
    ```

  - El valor de parámetro **kenmyer@litwareinc.com**.

Ese comando, casualmente, devuelve información sobre un usuario específico: el usuario con la identidad kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Consulte también


[Introducción a Windows PowerShell y Skype empresarial online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

