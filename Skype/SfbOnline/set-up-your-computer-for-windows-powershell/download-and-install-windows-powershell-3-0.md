---
title: Descargar e instalar Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
description: "Descargar, instalar y, a continuación, utilice 3.0 de Windows PowerShell para crear una sesión de PowerShell remoto que se conecta a Skype para los negocios en línea."
ms.openlocfilehash: 28f4db7492c233f5cfa16137d77ed8e0dc4a6572
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="480ff-103">Descargar e instalar Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="480ff-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="480ff-104">Si utilizas Windows 8.1, Windows 8, Windows Server 2012 R2 o Windows Server 2012, ya debe tener 3.0 de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="480ff-104">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0.</span></span> <span data-ttu-id="480ff-105">Eso es porque esta aplicación viene preinstalada con esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="480ff-105">That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="480ff-106">Si está ejecutando Windows 7 o Windows Server 2008 R2, es posible que también esté ejecutando 3.0 de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="480ff-106">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0.</span></span> <span data-ttu-id="480ff-107">Sin embargo, también es posible que se puede ejecutar la versión 2.0 en su lugar, la versión que se incluía originalmente con esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="480ff-107">However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems.</span></span> <span data-ttu-id="480ff-108">Para determinar qué versión de Microsoft PowerShelll usa, realice lo siguiente en el equipo de Windows 7 o Windows Server 2008 R2:</span><span class="sxs-lookup"><span data-stu-id="480ff-108">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="480ff-109">Haga clic en **Inicio**, seleccione **Todos los programas**, **Accesorios**, **Windows PowerShell**y, a continuación, haga clic en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="480ff-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="480ff-110">En la consola de PowerShell, escriba el comando siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="480ff-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="480ff-111">A continuación, se debe mostrar la información similar al siguiente en la ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="480ff-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="480ff-112">Si el número de versión devuelto es 3.0, significa que está ejecutando Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="480ff-112">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="480ff-113">Si el número de versión devuelto no es 3.0, necesitará instalar Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="480ff-113">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="480ff-114">Windows Management Framework 3.0, que incluye Windows PowerShell 3.0, se puede descargar desde el [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span><span class="sxs-lookup"><span data-stu-id="480ff-114">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="480ff-115">Después de comprobar que está instalado Windows PowerShell 3.0, debe asegurarse de que PowerShell se ha configurado para ejecutar secuencias de comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="480ff-115">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="480ff-116">Para ello, iniciar PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="480ff-116">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="480ff-117">En Windows 7, Windows Server 2008 R2, Windows Server 2012 o 2012 R2 de Windows Server, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="480ff-117">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="480ff-118">Haga clic en **Inicio**, seleccione **Todos los programas**, **Accesorios**, haga clic en **Windows PowerShell**, haga **De Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="480ff-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="480ff-119">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="480ff-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="480ff-120">Si está ejecutando Windows 8, realice este procedimiento en su lugar:</span><span class="sxs-lookup"><span data-stu-id="480ff-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="480ff-121">Tener acceso a la barra de encantos, haga clic en **Buscar**y, a continuación, haga clic en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="480ff-121">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="480ff-122">Se puede acceder rápidamente a la barra de encantos en cualquier equipo Windows 8 (pantalla táctil o sin pantalla táctil) manteniendo presionada la tecla Windows y presionando C.</span><span class="sxs-lookup"><span data-stu-id="480ff-122">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="480ff-123">En la barra de herramientas en la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="480ff-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="480ff-124">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="480ff-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="480ff-125">Después de PowerShell se ejecuta, debe cambiar la directiva de ejecución para permitir la ejecución de secuencias de comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="480ff-125">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="480ff-126">En la consola de PowerShell, escriba el comando siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="480ff-126">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
<span data-ttu-id="480ff-127">Para comprobar que se ha configurado correctamente la directiva de ejecución, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="480ff-127">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="480ff-128">Si se obtendrá el valor siguiente, a continuación, todo lo que se ha configurado correctamente:</span><span class="sxs-lookup"><span data-stu-id="480ff-128">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="480ff-129">Si no se está ejecutando actualmente Windows PowerShell 3.0, también deberá descargar e instalar Windows Management Framework 3.0 desde Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="480ff-129">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="480ff-130">Se trata de un paquete de instalación que incluye 3.0 de Windows PowerShell y administración remota de Windows (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="480ff-130">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="480ff-131">Este paquete de instalación puede ser necesario si ejecutan Windows 7 y aún no ha actualizado a Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="480ff-131">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="480ff-132">Si está ejecutando Windows Server 2012, 2012 R2 de Windows Server, Windows 8 o Windows 8.1, no deben ser necesidad de instalar Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="480ff-132">If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="480ff-133">3.0 de Windows PowerShell viene preinstalado en esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="480ff-133">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="480ff-134">Antes de instalar Windows Management Framework 3.0:</span><span class="sxs-lookup"><span data-stu-id="480ff-134">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="480ff-135">Asegúrese de que ha descargado la versión correcta del paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="480ff-135">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="480ff-136">Si está ejecutando la versión de 64 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x64.msu.</span><span class="sxs-lookup"><span data-stu-id="480ff-136">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="480ff-137">Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Windows6.1-KB2506143-x86.msu.</span><span class="sxs-lookup"><span data-stu-id="480ff-137">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="480ff-138">Si está ejecutando Windows 7 en su equipo, asegúrese de que ha instalado el Service Pack 1 de Windows 7.</span><span class="sxs-lookup"><span data-stu-id="480ff-138">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="480ff-139">Si no está seguro de qué versión de Windows está ejecutando o no está seguro si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic en **equipo**y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="480ff-139">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="480ff-140">Esta información se registrará en el cuadro de diálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="480ff-140">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="480ff-141">Para instalar Windows Management Framework 3.0, siga el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="480ff-141">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="480ff-142">Haga doble clic en el. Archivo de instalación de MSU ( **archivo Windows6.1-KB2506143-x86.msu**o **Windows6.1-KB2506143-x64.msu** ).</span><span class="sxs-lookup"><span data-stu-id="480ff-142">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="480ff-143">En el Asistente de descargar e instalar actualizaciones, en la página **Lea los términos de licencia (1 de 1)** , haga clic en ****.</span><span class="sxs-lookup"><span data-stu-id="480ff-143">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="480ff-144">Cuando la instalación esté completa, haga clic en **Reiniciar ahora** para reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="480ff-144">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="480ff-145">Una vez reiniciado el equipo, compruebe que puede iniciar Windows PowerShell y que la aplicación se puede ejecutar con credenciales administrativas.</span><span class="sxs-lookup"><span data-stu-id="480ff-145">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="480ff-146">Para hacer esto:</span><span class="sxs-lookup"><span data-stu-id="480ff-146">To do this:</span></span>
  
1. <span data-ttu-id="480ff-147">Haga clic en **Inicio**, seleccione **Todos los programas**, **Accesorios**, haga clic en **Windows PowerShell**, haga **De Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="480ff-147">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="480ff-148">Si el Control de cuenta de usuario aparecerá el cuadro de diálogo, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="480ff-148">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="480ff-149">Cuando aparezca la consola de PowerShell, a continuación, debe comprobar que el servicio WinRM se está ejecutando y que se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="480ff-149">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="480ff-150">Para comprobar que el servicio se está ejecutando, escriba el comando siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="480ff-150">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="480ff-151">A continuación, se mostrará información sobre el servicio WinRM en pantalla:</span><span class="sxs-lookup"><span data-stu-id="480ff-151">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="480ff-152">Si el servicio de estado no es igual a "Ejecutar", escriba el comando siguiente y presione ENTRAR para iniciar el servicio de WinRM:</span><span class="sxs-lookup"><span data-stu-id="480ff-152">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="480ff-153">Una vez iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM está utilizando autenticación básica:</span><span class="sxs-lookup"><span data-stu-id="480ff-153">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="480ff-154">Se mostrará información similar a la siguiente pantalla:</span><span class="sxs-lookup"><span data-stu-id="480ff-154">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="480ff-155">Si la autenticación básica se ha establecido en true, y esté listo para usar PowerShell para conectar con Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="480ff-155">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="480ff-156">See also</span><span class="sxs-lookup"><span data-stu-id="480ff-156">Related topics</span></span>
[<span data-ttu-id="480ff-157">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="480ff-157">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

## <a name="feedback"></a><span data-ttu-id="480ff-158">¿Comentarios?</span><span class="sxs-lookup"><span data-stu-id="480ff-158">Feedback?</span></span>
<span data-ttu-id="480ff-159">Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="480ff-159">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>