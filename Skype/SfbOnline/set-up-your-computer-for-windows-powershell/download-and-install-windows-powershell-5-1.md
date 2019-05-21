---
title: Descargar e instalar Windows PowerShell 5,1
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
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Descargue, instale y use Windows PowerShell 5,1 para crear una sesión remota de PowerShell que se conecte a Skype empresarial online.
ms.openlocfilehash: 42c466d476b95228674b8a58cdeafca785496f4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285118"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="49589-103">Descargar e instalar Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="49589-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="49589-104">Si está usando la actualización de aniversario de Windows 10 o Windows Server 2016, ya tiene Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="49589-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="49589-105">Esto se debe a que esta aplicación viene preinstalada con esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="49589-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="49589-106">Para determinar qué versión de Microsoft PowerShell está usando, haga lo siguiente en su equipo con Windows 7 o Windows Server 2008 R2 o Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="49589-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="49589-107">Haga clic en **Inicio**, en **todos los programas**, en **accesorios**, en **Windows PowerShell**y, por último, en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="49589-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="49589-108">En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="49589-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="49589-109">A continuación, debe mostrarse información similar a la siguiente en la ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="49589-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="49589-110">Si el número de versión devuelto es 5,1, quiere decir que está ejecutando Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="49589-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="49589-111">Si el número de versión devuelto no es 5,1, tendrá que instalar Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="49589-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="49589-112">Puede descargar Windows Management Framework 5,1, que incluye Windows PowerShell 5,1, desde el [centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="49589-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="49589-113">Después de comprobar que Windows PowerShell 5,1 está instalado, debe asegurarse de que PowerShell se ha configurado para ejecutar scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="49589-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="49589-114">Para ello, inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="49589-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="49589-115">En Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49589-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="49589-116">Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell**y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="49589-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="49589-117">Si aparece el cuadro de diálogo **control de cuentas de usuario** , haga clic en **sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="49589-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="49589-118">Si está ejecutando Windows 8, realice este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="49589-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="49589-119">Acceda a la barra de accesos, haga clic en **Buscar**y luego haga clic con el botón derecho en **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="49589-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="49589-120">Puede acceder rápidamente a la barra de accesos en cualquier equipo con Windows 8 (pantalla táctil o pantalla no táctil) si mantiene presionada la tecla Windows y presiona C.</span><span class="sxs-lookup"><span data-stu-id="49589-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="49589-121">En la barra de herramientas de la parte inferior de la pantalla, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="49589-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="49589-122">Si aparece el cuadro de diálogo **control de cuentas de usuario** , haga clic en **sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="49589-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="49589-123">Una vez que PowerShell se esté ejecutando, debe cambiar la Directiva de ejecución para permitir la ejecución de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="49589-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="49589-124">En la consola de PowerShell, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="49589-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="49589-125">Al ejecutar el comando anterior, es posible que reciba el siguiente mensaje de error: > *Set-ExecutionPolicy: obtener acceso al registro\\key'HKEY_LOCAL_MACHINE\\software\\Microsoft\\PowerShell\\1 ShellIds\\Micrsoft. PowerShell ' se* ha denegado.</span><span class="sxs-lookup"><span data-stu-id="49589-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="49589-126">Este mensaje de error suele ocurrir si no ejecuta PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="49589-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="49589-127">Cierre la sesión de PowerShell y comience una nueva sesión como administrador.</span><span class="sxs-lookup"><span data-stu-id="49589-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="49589-128">Para comprobar que la Directiva de ejecución se ha configurado correctamente, escriba lo siguiente en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="49589-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="49589-129">Si obtiene el siguiente valor, todo se ha configurado correctamente:</span><span class="sxs-lookup"><span data-stu-id="49589-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="49589-130">Si actualmente no ejecuta Windows PowerShell 5,1, también tendrá que descargar e instalar Windows Management Framework 5,1 desde el centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="49589-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="49589-131">Este es un paquete de instalación que incluye Windows PowerShell 5,1 y Windows Remote Management (WinRM) 3,0.</span><span class="sxs-lookup"><span data-stu-id="49589-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="49589-132">Este paquete de instalación podría ser necesario si, por ejemplo, se ejecuta Windows 7 SP1 y aún no se ha actualizado a Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="49589-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="49589-133">Si está ejecutando Windows Server 2016 o la actualización de aniversario de Windows 10, no es necesario instalar Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="49589-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="49589-134">Windows PowerShell 5,1 viene preinstalado en esos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="49589-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="49589-135">Antes de instalar Windows Management Framework 5,1:</span><span class="sxs-lookup"><span data-stu-id="49589-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="49589-136">Asegúrese de haber descargado la versión correcta del paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="49589-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="49589-137">Si está ejecutando la versión de 64 bits de Windows 7 SP1, descargue el archivo Win7AndW2K8R2-KB3191566-x64. ZIP.</span><span class="sxs-lookup"><span data-stu-id="49589-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="49589-138">Si está ejecutando la versión de 32 bits de Windows 7, descargue el archivo Win7-KB3191566-x86. ZIP.</span><span class="sxs-lookup"><span data-stu-id="49589-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="49589-139">Si está ejecutando Windows 7 en su equipo, asegúrese de haber instalado Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="49589-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="49589-140">Si no está seguro de qué versión de Windows está ejecutando o si no está seguro de si ha instalado el Service Pack 1 de Windows 7, haga clic en **Inicio**, haga clic con el botón secundario en **equipo**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="49589-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="49589-141">Esta información se notificará en el cuadro de diálogo sistema.</span><span class="sxs-lookup"><span data-stu-id="49589-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="49589-142">Para instalar Windows Management Framework 5,1, complete el procedimiento de [instalación y configuración de WMF 5,1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span><span class="sxs-lookup"><span data-stu-id="49589-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span></span>
  
<span data-ttu-id="49589-143">Después de reiniciar el equipo, compruebe que Windows PowerShell puede iniciarse y que la aplicación se puede ejecutar con credenciales administrativas.</span><span class="sxs-lookup"><span data-stu-id="49589-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="49589-144">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49589-144">To do this:</span></span>
  
1. <span data-ttu-id="49589-145">Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, **Windows PowerShell**, haga clic con el botón derecho en **Windows PowerShell** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="49589-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="49589-146">Si aparece el cuadro de diálogo control de cuentas de usuario, haga clic en **sí** para comprobar que desea ejecutar PowerShell con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="49589-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="49589-147">Cuando aparezca la consola de PowerShell, debe comprobar que el servicio WinRM se está ejecutando y se ha configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="49589-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="49589-148">Para comprobar que el servicio se está ejecutando, escriba el siguiente comando en el símbolo del sistema de PowerShell y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="49589-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="49589-149">Aparecerá la información sobre el servicio WinRM en la pantalla:</span><span class="sxs-lookup"><span data-stu-id="49589-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="49589-150">Si el estado del servicio no es "en ejecución", inicie el servicio WinRM escribiendo el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="49589-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="49589-151">Después de que el servicio se haya iniciado, ejecute el siguiente comando para asegurarse de que WinRM esté usando la autenticación básica:</span><span class="sxs-lookup"><span data-stu-id="49589-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="49589-152">En la pantalla se mostrará información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="49589-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="49589-153">Si la autenticación básica se ha establecido en true, está listo para usar PowerShell para conectarse a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="49589-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="49589-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="49589-154">Related topics</span></span>
[<span data-ttu-id="49589-155">Configurar el equipo para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49589-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
