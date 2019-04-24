---
title: Descargue e instale Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Descargar, instalar y, a continuación, use Windows PowerShell 5.1 para crear una sesión remota de PowerShell que se conecta a Skype para profesionales en línea.
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198072"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="b7428-103">Descargue e instale Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="b7428-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="b7428-104">Si está utilizando Windows 10 aniversario Update o Windows Server 2016, ya debe tener Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="b7428-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="b7428-105">Que es debido a que esta aplicación viene preinstalada con los sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="b7428-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="b7428-106">Para determinar qué versión de Microsoft PowerShelll usa, realice lo siguiente en el equipo de Windows Server 2008 R2 o Windows Server 2012 o Windows 7:</span><span class="sxs-lookup"><span data-stu-id="b7428-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="b7428-107">Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**y, a continuación, haga clic en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b7428-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b7428-108">En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="b7428-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="b7428-109">A continuación, se debe mostrar información similar a la siguiente en la ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="b7428-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="b7428-110">Si el número de versión devuelto es 5.1, a continuación, ejecuta Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="b7428-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="b7428-111">Si el número de versión devuelto no es 5.1, necesitará instalar Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="b7428-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="b7428-112">Windows Management Framework 5.1, que incluye Windows PowerShell 5.1, puede descargar desde el [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="b7428-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="b7428-113">Una vez haya comprobado que está instalado Windows PowerShell 5.1, debe asegurarse de que PowerShell se ha configurado para la ejecución de secuencias de comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="b7428-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="b7428-114">Para ello, inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="b7428-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="b7428-115">En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7428-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="b7428-116">Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b7428-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="b7428-117">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="b7428-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="b7428-118">Si ejecuta Windows 8, complete este procedimiento en su lugar:</span><span class="sxs-lookup"><span data-stu-id="b7428-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="b7428-119">Obtener acceso a la barra de accesos, haga clic en **Buscar**y, a continuación, haga clic en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b7428-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="b7428-120">Puede tener acceso rápidamente a la barra de accesos en cualquier equipo de Windows 8 (pantalla táctil o sin pantalla táctil) manteniendo presionada la tecla de Windows y presionando C.</span><span class="sxs-lookup"><span data-stu-id="b7428-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="b7428-121">En la barra de herramientas en la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b7428-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="b7428-122">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="b7428-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="b7428-123">Después de que se está ejecutando PowerShell, debe cambiar la directiva de ejecución para permitir la ejecución de secuencias de comandos remotos.</span><span class="sxs-lookup"><span data-stu-id="b7428-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="b7428-124">En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="b7428-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="b7428-125">Cuando se ejecuta el comando anterior, es posible que reciba el siguiente mensaje de error: > *Set-ExecutionPolicy: acceso a la clave del registro ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' ha sido denegado.*</span><span class="sxs-lookup"><span data-stu-id="b7428-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="b7428-126">Normalmente, este mensaje de error se produce si no se está ejecutando PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="b7428-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="b7428-127">Cierre la sesión de PowerShell e iniciar una sesión de nuevo como administrador.</span><span class="sxs-lookup"><span data-stu-id="b7428-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="b7428-128">Para comprobar que se ha configurado correctamente la directiva de ejecución, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="b7428-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="b7428-129">Si se obtiene el siguiente valor, a continuación, todo lo que se ha configurado correctamente:</span><span class="sxs-lookup"><span data-stu-id="b7428-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="b7428-130">Si no se está ejecutando actualmente Windows PowerShell 5.1, también debe descargar e instalar Windows Management Framework 5.1 desde Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="b7428-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="b7428-131">Se trata de un paquete de instalación que incluye Windows PowerShell 5.1 y administración remota de Windows (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="b7428-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="b7428-132">Este paquete de instalación puede ser necesario si, por ejemplo, está ejecutando Windows 7 SP1 y aún no ha actualizado a Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="b7428-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="b7428-133">Si ejecuta Windows Server 2016, o una actualización de Windows 10 aniversario, no debería haber necesidad de instalar Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="b7428-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="b7428-134">Windows PowerShell 5.1 viene preinstalado en dichos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="b7428-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="b7428-135">Antes de instalar Windows Management Framework 5.1:</span><span class="sxs-lookup"><span data-stu-id="b7428-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="b7428-136">Asegúrese de que ha descargado la versión correcta del paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="b7428-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="b7428-137">Si está ejecutando la versión de 64 bits de Windows 7 SP1, descargue el archivo Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="b7428-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="b7428-138">Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="b7428-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="b7428-139">Si ejecuta Windows 7 en su equipo, asegúrese de que ha instalado Service Pack 1 de Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b7428-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="b7428-140">Si no está seguro de qué versión de Windows está ejecutando o no está seguro de si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic en **equipo**y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b7428-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="b7428-141">Esta información se notificará en el cuadro de diálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7428-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="b7428-142">Para instalar Windows Management Framework 5.1, complete el procedimiento de [instalación y configuración de WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span><span class="sxs-lookup"><span data-stu-id="b7428-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span></span>
  
<span data-ttu-id="b7428-143">Una vez se haya reiniciado el equipo, compruebe que puede iniciar Windows PowerShell y que la aplicación se puede ejecutar bajo credenciales administrativas.</span><span class="sxs-lookup"><span data-stu-id="b7428-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="b7428-144">Para hacer esto:</span><span class="sxs-lookup"><span data-stu-id="b7428-144">To do this:</span></span>
  
1. <span data-ttu-id="b7428-145">Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Accesorios**, haga clic en **Windows PowerShell**, haga clic en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="b7428-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="b7428-146">Si el Control de cuentas de usuario aparece el cuadro de diálogo, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="b7428-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="b7428-147">Cuando aparezca la consola de PowerShell, a continuación, debe comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7428-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="b7428-148">Para comprobar que se está ejecutando el servicio, escriba el siguiente comando en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="b7428-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="b7428-149">A continuación, se mostrará información sobre el servicio WinRM en pantalla:</span><span class="sxs-lookup"><span data-stu-id="b7428-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="b7428-150">Si el servicio de estado no es igual a "Ejecutar", inicie el servicio WinRM por escribiendo el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="b7428-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="b7428-151">Una vez que haya iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM usa la autenticación básica:</span><span class="sxs-lookup"><span data-stu-id="b7428-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="b7428-152">Se mostrará en la pantalla información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7428-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="b7428-153">Si la autenticación básica se ha establecido en true, a continuación, estará listo usar PowerShell para conectarse a Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="b7428-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="b7428-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b7428-154">Related topics</span></span>
[<span data-ttu-id="b7428-155">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7428-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
