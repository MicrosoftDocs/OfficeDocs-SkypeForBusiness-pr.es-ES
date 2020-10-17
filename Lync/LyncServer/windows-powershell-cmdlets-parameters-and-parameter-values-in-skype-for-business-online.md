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
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="eb688-102">Cmdlets, parámetros y valores de parámetros de Windows PowerShell en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="eb688-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb688-103">_**Última modificación del tema:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="eb688-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="eb688-104">Si está familiarizado con la ventana de comandos que se encuentra en todas las versiones de Windows (o si está familiarizado con MS-DOS), tendrá una ventaja para aprender a usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb688-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="eb688-105">En la ventana de comandos, escriba un comando y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="eb688-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="eb688-106">En respuesta, el equipo ejecuta un comando o un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="eb688-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="eb688-107">Por ejemplo, para devolver información acerca de todos los archivos y carpetas del directorio actual, escriba este comando en el símbolo del sistema y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="eb688-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="eb688-108">A su vez, obtiene información sobre todos los archivos y carpetas del directorio actual:</span><span class="sxs-lookup"><span data-stu-id="eb688-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="eb688-109">Este es un ejemplo de un resultado cuando solo escribe el nombre de un comando o un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="eb688-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="eb688-110">Sin embargo, muchos de los comandos que se ejecutan desde la ventana de comandos también aceptan *argumentos*.</span><span class="sxs-lookup"><span data-stu-id="eb688-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="eb688-111">Los argumentos son datos adicionales de información que se pasan al comando, que modifican el comportamiento del comando.</span><span class="sxs-lookup"><span data-stu-id="eb688-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="eb688-112">Por ejemplo, si solo deseaba ver los nombres de los archivos y la carpeta en el directorio actual, sin otra información, como el tamaño del archivo o la carpeta, o la fecha y la hora en que se creó la carpeta o carpeta.</span><span class="sxs-lookup"><span data-stu-id="eb688-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="eb688-113">En este caso, anexaría el argumento **/b** cuando ejecutaba el comando dir:</span><span class="sxs-lookup"><span data-stu-id="eb688-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="eb688-114">Cuando se incluye el argumento **/b** , el comando **dir** sólo devuelve los nombres de las carpetas y los archivos encontrados en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="eb688-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="eb688-115">En el comando anterior, el argumento **/b** es la única información necesaria para limitar los datos devueltos a los nombres de archivo y carpeta.</span><span class="sxs-lookup"><span data-stu-id="eb688-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="eb688-116">Suele ser el caso de los comandos de la línea de comandos: la mera presencia de un argumento es todo lo que se necesita para cambiar el comportamiento del comando.</span><span class="sxs-lookup"><span data-stu-id="eb688-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="eb688-117">(Es decir, se incluye el argumento **/b** para ocultar información adicional o se excluye el argumento **/b** para mostrar la información adicional). En otras ocasiones, sin embargo, debe especificar un *valor de argumento*.</span><span class="sxs-lookup"><span data-stu-id="eb688-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="eb688-118">Un valor de argumento es información adicional que se pasa al propio argumento.</span><span class="sxs-lookup"><span data-stu-id="eb688-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="eb688-119">Por ejemplo, el argumento **/o** le permite especificar cómo desea que el comando dir ordene los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="eb688-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="eb688-120">Entre otras opciones, puede usar el valor de argumento **e** para ordenar por extensión de archivo o por el valor del argumento **s** para ordenar por tamaño de archivo.</span><span class="sxs-lookup"><span data-stu-id="eb688-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="eb688-121">Por ejemplo, este comando ordena los datos devueltos por extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="eb688-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="eb688-122">Tenga en cuenta que el valor del argumento **e** se incluye inmediatamente después del argumento **/o** :</span><span class="sxs-lookup"><span data-stu-id="eb688-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="eb688-123">Mediante nuestra carpeta de ejemplo, los datos devueltos tendrán el siguiente aspecto, con los archivos ordenados alfabéticamente por extensión de archivo:</span><span class="sxs-lookup"><span data-stu-id="eb688-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="eb688-124">O bien, para ayudarle a identificar exactamente lo que estamos hablando:</span><span class="sxs-lookup"><span data-stu-id="eb688-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="eb688-125">Aunque Windows PowerShell usa terminología diferente, el enfoque básico para trabajar con Windows PowerShell es el mismo que cuando se trabaja con la ventana de comandos: los comandos se escriben, se incluyen los argumentos y los valores de argumento según sea necesario y, a continuación, se presiona Entrar para ejecutar dichos comandos.</span><span class="sxs-lookup"><span data-stu-id="eb688-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="eb688-126">Como se indicó, Windows PowerShell usa una terminología diferente a la utilizada por el shell de comandos.</span><span class="sxs-lookup"><span data-stu-id="eb688-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="eb688-127">En Windows PowerShell, los comandos que ejecuta se denominan *cmdlets*.</span><span class="sxs-lookup"><span data-stu-id="eb688-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="eb688-128">A su vez, los argumentos pasados a un cmdlet se conocen como *parámetros*y los valores pasados a un parámetro se conocen como *valores de parámetro*.</span><span class="sxs-lookup"><span data-stu-id="eb688-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="eb688-129">Las definiciones anteriores se han simplificado en cierta medida.</span><span class="sxs-lookup"><span data-stu-id="eb688-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="eb688-130">Los cmdlets son esencialmente Mini-aplicaciones que solo se pueden ejecutar desde el entorno de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb688-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="eb688-131">Sin embargo, también puede ejecutar otros comandos y aplicaciones desde Windows PowerShell, incluidos la mayoría de los comandos y aplicaciones que se pueden ejecutar desde una ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="eb688-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="eb688-132">Por ejemplo, si desea iniciar el Bloc de notas desde Windows PowerShell, todo lo que necesita hacer es escribir lo siguiente y presionar entrar:</span><span class="sxs-lookup"><span data-stu-id="eb688-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="eb688-133">Sin embargo, cuando se trata de administrar Skype empresarial online, la mayoría de los administradores confiarán en los cmdlets de Windows PowerShell para llevar a cabo tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="eb688-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="eb688-134">A la vez, hay muy pocos tipos de comandos o aplicaciones que se pueden usar para administrar Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="eb688-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="eb688-135">A veces, los cmdlets de Skype empresarial online pueden usarse sin argumentos adicionales (como se indica, los argumentos se conocen como parámetros en Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="eb688-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="eb688-136">Por ejemplo, el siguiente comando llama al cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="eb688-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="eb688-137">Por sí mismo, el comando devuelve información sobre todos los usuarios de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="eb688-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="eb688-138">Sin embargo, la mayoría de los cmdlets de Skype empresarial online también aceptan parámetros (y valores de parámetro).</span><span class="sxs-lookup"><span data-stu-id="eb688-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="eb688-139">Considere el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="eb688-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="eb688-140">Este comando consta de tres partes:</span><span class="sxs-lookup"><span data-stu-id="eb688-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="eb688-141">El cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="eb688-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="eb688-142">Parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="eb688-142">The Identity parameter.</span></span> <span data-ttu-id="eb688-143">Tenga en cuenta que, en Windows PowerShell, los parámetros siempre están precedidos de un guión (-).</span><span class="sxs-lookup"><span data-stu-id="eb688-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="eb688-144">Esto significa que, para este mismo cmdlet, el parámetro UnassignedUser se indicaría con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="eb688-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="eb688-145">Esto es útil para saber, no solo porque los parámetros deben ir precedidos por un guión, sino también porque esto difiere de la ventana de comandos, donde los argumentos están precedidos mediante una barra diagonal (/):</span><span class="sxs-lookup"><span data-stu-id="eb688-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="eb688-146">El valor de parámetro **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="eb688-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="eb688-147">Ese comando, casualmente, devuelve información sobre un usuario específico: el usuario con la identidad kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="eb688-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="eb688-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb688-148">See Also</span></span>


<span data-ttu-id="eb688-149">[Introducción a Windows PowerShell y Skype empresarial online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb688-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

