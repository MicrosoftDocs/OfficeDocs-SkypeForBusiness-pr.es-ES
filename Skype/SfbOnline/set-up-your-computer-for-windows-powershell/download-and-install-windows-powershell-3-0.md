---
title: Descargue e instale Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Descargar, instalar y, a continuación, use Windows PowerShell 3.0 para crear una sesión remota de PowerShell que se conecta a Skype para profesionales en línea.
ms.openlocfilehash: 6679e9749efd6ee09a7c26f383b1b411caadb43e
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19493996"
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="1d554-103">Descargue e instale Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="1d554-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="1d554-104">Si está utilizando Windows 8.1, Windows 8, Windows Server 2012 R2 o Windows Server 2012, ya debe tener Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1d554-104">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0.</span></span> <span data-ttu-id="1d554-105">Que es debido a que esta aplicación viene preinstalada con los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="1d554-105">That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="1d554-106">Si ejecuta Windows 7 o Windows Server 2008 R2, es posible que también esté ejecutando Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1d554-106">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0.</span></span> <span data-ttu-id="1d554-107">Sin embargo, también es posible que puede es posible que esté ejecutando versión 2.0 en su lugar, la versión que se incluía originalmente con estos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="1d554-107">However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems.</span></span> <span data-ttu-id="1d554-108">Para determinar qué versión de Microsoft PowerShelll usa, realice lo siguiente en el equipo con Windows 7 o Windows Server 2008 R2:</span><span class="sxs-lookup"><span data-stu-id="1d554-108">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="1d554-109">Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**y, a continuación, haga clic en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1d554-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1d554-110">En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1d554-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="1d554-111">A continuación, se debe mostrar información similar a la siguiente en la ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="1d554-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="1d554-112">Si el número de versión devuelto es 3.0, a continuación, ejecuta Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1d554-112">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="1d554-113">Si el número de versión devuelto no es 3.0, necesitará instalar Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1d554-113">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="1d554-114">Puede descargar Windows Management Framework 3.0, que incluye Windows PowerShell 3.0, desde el [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span><span class="sxs-lookup"><span data-stu-id="1d554-114">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="1d554-115">Una vez haya comprobado que Windows PowerShell 3.0 está instalado, debe asegurarse de que PowerShell se ha configurado para la ejecución de secuencias de comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="1d554-115">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="1d554-116">Para ello, inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="1d554-116">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="1d554-117">En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d554-117">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="1d554-118">Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1d554-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1d554-119">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="1d554-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1d554-120">Si ejecuta Windows 8, complete este procedimiento en su lugar:</span><span class="sxs-lookup"><span data-stu-id="1d554-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="1d554-121">Obtener acceso a la barra de accesos, haga clic en **Buscar**y, a continuación, haga clic en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1d554-121">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="1d554-122">Puede tener acceso rápidamente a la barra de accesos en cualquier equipo de Windows 8 (pantalla táctil o sin pantalla táctil) manteniendo presionada la tecla de Windows y presionando C.</span><span class="sxs-lookup"><span data-stu-id="1d554-122">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="1d554-123">En la barra de herramientas en la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1d554-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="1d554-124">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="1d554-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1d554-125">Después de que se está ejecutando PowerShell, debe cambiar la directiva de ejecución para permitir la ejecución de secuencias de comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="1d554-125">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="1d554-126">En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1d554-126">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="1d554-127">Cuando se ejecuta el comando anterior, es posible que reciba el siguiente mensaje de error: > *Set-ExecutionPolicy: acceso a la clave del registro ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' ha sido denegado.*</span><span class="sxs-lookup"><span data-stu-id="1d554-127">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="1d554-128">Normalmente, este mensaje de error se produce si no se está ejecutando PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="1d554-128">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="1d554-129">Cierre la sesión de PowerShell e iniciar una sesión de nuevo como administrador.</span><span class="sxs-lookup"><span data-stu-id="1d554-129">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="1d554-130">Para comprobar que se ha configurado correctamente la directiva de ejecución, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1d554-130">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="1d554-131">Si se obtiene el siguiente valor, a continuación, todo lo que se ha configurado correctamente:</span><span class="sxs-lookup"><span data-stu-id="1d554-131">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="1d554-132">Si no se está ejecutando actualmente Windows PowerShell 3.0, también debe descargar e instalar Windows Management Framework 3.0 desde Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="1d554-132">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="1d554-133">Se trata de un paquete de instalación que incluye Windows PowerShell 3.0 y administración remota de Windows (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="1d554-133">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="1d554-134">Este paquete de instalación puede ser necesario si ejecuta Windows 7 y aún no ha actualizado a Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1d554-134">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="1d554-135">Si ejecuta Windows Server 2012, Windows Server 2012 R2, Windows 8 o Windows 8.1, no debería haber necesidad de instalar Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1d554-135">If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="1d554-136">Windows PowerShell 3.0 viene preinstalado en dichos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="1d554-136">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="1d554-137">Antes de instalar Windows Management Framework 3.0:</span><span class="sxs-lookup"><span data-stu-id="1d554-137">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="1d554-138">Asegúrese de que ha descargado la versión correcta del paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="1d554-138">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="1d554-139">Si está ejecutando la versión de 64 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x64.msu.</span><span class="sxs-lookup"><span data-stu-id="1d554-139">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="1d554-140">Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x86.msu.</span><span class="sxs-lookup"><span data-stu-id="1d554-140">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="1d554-141">Si ejecuta Windows 7 en su equipo, asegúrese de que ha instalado Service Pack 1 de Windows 7.</span><span class="sxs-lookup"><span data-stu-id="1d554-141">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="1d554-142">Si no está seguro de qué versión de Windows está ejecutando o no está seguro de si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic en **equipo**y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1d554-142">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="1d554-143">Esta información se notificará en el cuadro de diálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1d554-143">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="1d554-144">Para instalar Windows Management Framework 3.0, complete el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="1d554-144">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="1d554-145">Haga doble clic en el. En el archivo de instalación MSU ( **Windows6.1-KB2506143-x64.msu** o **Windows6.1-KB2506143-x86.msu**).</span><span class="sxs-lookup"><span data-stu-id="1d554-145">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="1d554-146">En el Asistente de descargar e instalar actualizaciones, en la página **Lea estos términos de licencia (1 de 1)** , haga clic en ****.</span><span class="sxs-lookup"><span data-stu-id="1d554-146">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="1d554-147">Una vez finalizada la instalación, haga clic en **Reiniciar ahora** para reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="1d554-147">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="1d554-148">Una vez se haya reiniciado el equipo, compruebe que puede iniciar Windows PowerShell y que la aplicación se puede ejecutar bajo credenciales administrativas.</span><span class="sxs-lookup"><span data-stu-id="1d554-148">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="1d554-149">Para hacer esto:</span><span class="sxs-lookup"><span data-stu-id="1d554-149">To do this:</span></span>
  
1. <span data-ttu-id="1d554-150">Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1d554-150">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1d554-151">Si el Control de cuentas de usuario aparece el cuadro de diálogo, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="1d554-151">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1d554-152">Cuando aparezca la consola de PowerShell, a continuación, debe comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="1d554-152">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="1d554-153">Para comprobar que se está ejecutando el servicio, escriba el siguiente comando en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1d554-153">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="1d554-154">A continuación, se mostrará información sobre el servicio WinRM en pantalla:</span><span class="sxs-lookup"><span data-stu-id="1d554-154">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="1d554-155">Si el servicio de estado no es igual a "Ejecutar", inicie el servicio WinRM por escribiendo el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1d554-155">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="1d554-156">Una vez que haya iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM usa la autenticación básica:</span><span class="sxs-lookup"><span data-stu-id="1d554-156">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="1d554-157">Se mostrará en la pantalla información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d554-157">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="1d554-158">Si la autenticación básica se ha establecido en true, a continuación, estará listo usar PowerShell para conectarse a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="1d554-158">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="1d554-159">See also</span><span class="sxs-lookup"><span data-stu-id="1d554-159">Related topics</span></span>
[<span data-ttu-id="1d554-160">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d554-160">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 