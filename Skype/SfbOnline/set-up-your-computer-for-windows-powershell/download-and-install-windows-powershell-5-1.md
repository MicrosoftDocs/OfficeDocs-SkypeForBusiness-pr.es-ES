---
title: Descargar e instalar Windows PowerShell 5.1
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Descargue, instale y, a continuación, use Windows PowerShell 5.1 para crear una sesión remota de PowerShell que se conecte a Skype Empresarial Online.
ms.openlocfilehash: ed719a2df084c968c622a54fe145647b2d7b7aa8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120339"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="f63ab-103">Descargar e instalar Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="f63ab-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="f63ab-104">Si usa Windows 10 Anniversary Update o Windows Server 2016, ya debería tener Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="f63ab-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="f63ab-105">Esto se debe a que esta aplicación viene preinstalada con esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="f63ab-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="f63ab-106">Para determinar qué versión de Microsoft PowerShelll usa, haga lo siguiente en su equipo con Windows 7 o Windows Server 2008 R2 o Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="f63ab-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="f63ab-107">Haga **clic en** Inicio, en Todos los **programas,** en Accesorios, en **Windows PowerShell** y, a continuación, haga clic **en Windows PowerShell**. </span><span class="sxs-lookup"><span data-stu-id="f63ab-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f63ab-108">En la consola de PowerShell, escriba el comando siguiente y, después, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="f63ab-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="f63ab-109">La información similar a la siguiente debería mostrarse en la ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="f63ab-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="f63ab-110">Si el número de versión devuelto es 5.1, está ejecutando Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="f63ab-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="f63ab-111">Si el número de versión devuelto no es 5.1, tendrá que instalar Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="f63ab-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="f63ab-112">Puede descargar Windows Management Framework 5.1, que incluye Windows PowerShell 5.1, desde el [Centro de descarga de Microsoft.](https://www.microsoft.com/download/details.aspx?id=54616)</span><span class="sxs-lookup"><span data-stu-id="f63ab-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="f63ab-113">Después de comprobar que Windows PowerShell 5.1 está instalado, debe asegurarse de que PowerShell se ha configurado para ejecutar scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="f63ab-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="f63ab-114">Para ello, inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="f63ab-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="f63ab-115">En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f63ab-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="f63ab-116">Haga clic **en** Inicio , **en Todos** los programas, en **Accesorios,** en Windows PowerShell, haga clic con el botón derecho **en Windows PowerShell** y, a continuación, haga clic en Ejecutar **como administrador.**</span><span class="sxs-lookup"><span data-stu-id="f63ab-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="f63ab-117">Si aparece **el cuadro de diálogo Control de** cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="f63ab-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="f63ab-118">Si ejecuta Windows 8, complete este procedimiento en su lugar:</span><span class="sxs-lookup"><span data-stu-id="f63ab-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="f63ab-119">Acceda a la barra Accesos, haga clic **en Buscar** y, a continuación, haga clic con el botón derecho **en Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f63ab-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="f63ab-120">Puedes acceder rápidamente a la barra Accesos de cualquier equipo con Windows 8 (pantalla táctil o pantalla no táctil) manteniendo presionada la tecla Windows y presionando C.</span><span class="sxs-lookup"><span data-stu-id="f63ab-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="f63ab-121">En la barra de herramientas de la parte inferior de la pantalla, haga clic **en Ejecutar como administrador.**</span><span class="sxs-lookup"><span data-stu-id="f63ab-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="f63ab-122">Si aparece **el cuadro de diálogo Control de** cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="f63ab-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="f63ab-123">Después de ejecutar PowerShell, debe cambiar la directiva de ejecución para permitir la ejecución de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="f63ab-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="f63ab-124">En la consola de PowerShell, escriba el comando siguiente y, después, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="f63ab-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="f63ab-125">Al ejecutar el comando anterior, es posible que reciba el siguiente mensaje de error:> Set-ExecutionPolicy: Se deniega el acceso a la clave del Registro *HKEY_LOCAL_MACHINE \\ SOFTWARE Microsoft \\ \\ PowerShell \\ 1 \\ ShellIds \\ Micrsoft.PowerShell'.*</span><span class="sxs-lookup"><span data-stu-id="f63ab-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="f63ab-126">Este mensaje de error suele producirse si no ejecuta PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="f63ab-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="f63ab-127">Cierre la sesión de PowerShell e inicie una nueva sesión como administrador.</span><span class="sxs-lookup"><span data-stu-id="f63ab-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="f63ab-128">Para comprobar que la directiva de ejecución se ha configurado correctamente, escriba lo siguiente en el símbolo del sistema de PowerShell y, después, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="f63ab-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="f63ab-129">Si vuelve a obtener el siguiente valor, todo se ha configurado correctamente:</span><span class="sxs-lookup"><span data-stu-id="f63ab-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="f63ab-130">Si actualmente no está ejecutando Windows PowerShell 5.1, también tendrá que descargar e instalar Windows Management Framework 5.1 desde el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f63ab-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="f63ab-131">Este es un paquete de instalación que incluye Windows PowerShell 5.1 y Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="f63ab-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="f63ab-132">Este paquete de instalación puede ser necesario si, por ejemplo, ejecuta Windows 7 SP1 y aún no se ha actualizado a Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="f63ab-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="f63ab-133">Si ejecuta Windows Server 2016 o Windows 10 Anniversary Update, no es necesario instalar Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="f63ab-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="f63ab-134">Windows PowerShell 5.1 viene preinstalado en esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="f63ab-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="f63ab-135">Antes de instalar Windows Management Framework 5.1:</span><span class="sxs-lookup"><span data-stu-id="f63ab-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="f63ab-136">Asegúrese de que ha descargado la versión correcta del paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="f63ab-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="f63ab-137">Si ejecuta la versión de 64 bits de Windows 7 SP1, descargue el archivo Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="f63ab-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="f63ab-138">Si ejecuta la versión de 32 bits de Windows 7, descargue el archivo Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="f63ab-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="f63ab-139">Si ejecuta Windows 7 en el equipo, asegúrese de que ha instalado Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="f63ab-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="f63ab-140">Si no está seguro de qué versión de Windows está ejecutando o no está seguro de si ha instalado Windows 7 Service Pack 1, haga clic en Inicio **,** haga clic con el botón derecho en Equipo y, a continuación, haga clic en **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="f63ab-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="f63ab-141">Esta información se mostrará en el cuadro de diálogo Sistema.</span><span class="sxs-lookup"><span data-stu-id="f63ab-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="f63ab-142">Para instalar Windows Management Framework 5.1, complete el procedimiento en Instalar [y configurar WMF 5.1.](/powershell/scripting/wmf/setup/install-configure)</span><span class="sxs-lookup"><span data-stu-id="f63ab-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="f63ab-143">Después de reiniciar el equipo, compruebe que Windows PowerShell puede iniciarse y que la aplicación se puede ejecutar con credenciales administrativas.</span><span class="sxs-lookup"><span data-stu-id="f63ab-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="f63ab-144">Para ello:</span><span class="sxs-lookup"><span data-stu-id="f63ab-144">To do this:</span></span>
  
1. <span data-ttu-id="f63ab-145">Haga **clic en** Inicio, haga clic **en Todos** los programas, en Accesorios, haga clic en **Windows PowerShell,** haga clic con el botón derecho en **Windows PowerShell y,** a continuación, haga clic en Ejecutar **como administrador.**</span><span class="sxs-lookup"><span data-stu-id="f63ab-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="f63ab-146">Si aparece el cuadro de diálogo Control de cuentas de usuario, haga clic en **Sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="f63ab-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="f63ab-147">Cuando aparezca la consola de PowerShell, deberá comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="f63ab-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="f63ab-148">Para comprobar que el servicio se está ejecutando, escriba el siguiente comando en el símbolo del sistema de PowerShell y, después, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="f63ab-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="f63ab-149">La información sobre el servicio WinRM se mostrará en pantalla:</span><span class="sxs-lookup"><span data-stu-id="f63ab-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="f63ab-150">Si el estado del servicio no es igual a "En ejecución", inicie el servicio WinRM escribiendo el siguiente comando y presionando ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="f63ab-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="f63ab-151">Una vez que se haya iniciado el servicio, ejecute el siguiente comando para asegurarse de que WinRM usa la autenticación básica:</span><span class="sxs-lookup"><span data-stu-id="f63ab-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="f63ab-152">Se mostrará en pantalla información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f63ab-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="f63ab-153">Si la autenticación básica se ha establecido en true, está listo para usar PowerShell para conectarse a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="f63ab-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="f63ab-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f63ab-154">Related topics</span></span>
[<span data-ttu-id="f63ab-155">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f63ab-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
