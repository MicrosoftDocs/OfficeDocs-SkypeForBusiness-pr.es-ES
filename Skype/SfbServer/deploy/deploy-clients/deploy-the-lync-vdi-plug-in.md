---
title: Implementar el complemento Lync VDI con Skype Empresarial Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: En este tema se analizan los procedimientos de implementación para usar Skype Empresarial al conectarse a un escritorio virtual remoto.
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805940"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="863d0-103">Implementar el complemento Lync VDI con Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="863d0-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="863d0-104">En este tema se analizan los procedimientos de implementación para usar Skype Empresarial al conectarse a un escritorio virtual remoto.</span><span class="sxs-lookup"><span data-stu-id="863d0-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="863d0-105">Las consideraciones de planeación se [encuentran en Plan para Skype Empresarial en entornos VDI.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)</span><span class="sxs-lookup"><span data-stu-id="863d0-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="863d0-106">Un entorno de infraestructura de escritorio virtual (VDI) se usa en algunas organizaciones en las que los problemas de seguridad y cumplimiento son especialmente confidenciales.</span><span class="sxs-lookup"><span data-stu-id="863d0-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="863d0-107">Sus usuarios están en equipos windows locales y usan clientes en un escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="863d0-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="863d0-108">El uso de Skype Empresarial en una conexión como esta requiere software adicional de complemento VDI.</span><span class="sxs-lookup"><span data-stu-id="863d0-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="863d0-109">Hay dos soluciones disponibles para el componente de complemento VDI: una ofrecida por Microsoft y otra ofrecida por Citrix.</span><span class="sxs-lookup"><span data-stu-id="863d0-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="863d0-110">Microsoft recomienda usar la nueva solución HDX RealTime Optimization Pack en nuevas implementaciones, pero seguirá siendo compatible con el complemento VDI de Lync original durante el resto de su ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="863d0-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="863d0-111">En este tema se proporcionan detalles sobre la implementación del complemento VDI de Microsoft Lync, que solo es compatible con Windows 7 y Windows 8 o Windows Server 2008, y solo admite clientes de Lync 2013 o Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="863d0-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="863d0-112">No hay planes para actualizar este complemento, pero [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) para Skype Empresarial se actualizará según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="863d0-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="863d0-113">Preparar el entorno para el complemento Lync VDI</span><span class="sxs-lookup"><span data-stu-id="863d0-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="863d0-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="863d0-114"><a name="Prepare_vdi"> </a></span></span>

1. <span data-ttu-id="863d0-115">En Skype Empresarial Server, asegúrese de que EnableMediaRedirection está establecido en TRUE para todos los usuarios del complemento Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="863d0-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="863d0-116">Para obtener más información, consulte los temas de ayuda para el cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) y el cmdlet [Set-CsClientPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="863d0-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="863d0-117">En el servidor del centro de datos, instale el cliente de Skype Empresarial en todos los escritorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="863d0-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="863d0-118">En los equipos locales, instale el complemento Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="863d0-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="863d0-119">Ahora, los usuarios deben conectar un dispositivo como auriculares o cámara web a su equipo local.</span><span class="sxs-lookup"><span data-stu-id="863d0-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="863d0-120">Configurar las opciones de conexión a Escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="863d0-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="863d0-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="863d0-121"><a name="Prepare_vdi"> </a></span></span>

<span data-ttu-id="863d0-122">Para preparar la conexión a Escritorio remoto para el complemento Lync VDI, siga estos pasos en el equipo local:</span><span class="sxs-lookup"><span data-stu-id="863d0-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="863d0-123">Si el equipo local ejecuta Windows 8, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="863d0-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="863d0-124">Si el equipo local ejecuta Windows 7 con SP1, instale la versión más reciente de Windows 8 del cliente de [Servicios de Escritorio remoto.](https://go.microsoft.com/fwlink/p/?LinkId=268032)</span><span class="sxs-lookup"><span data-stu-id="863d0-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="863d0-125">Inicie el cliente de servicios de escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a escritorio remoto**.</span><span class="sxs-lookup"><span data-stu-id="863d0-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="863d0-126">Haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="863d0-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="863d0-127">Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="863d0-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="863d0-128">En **Reproducción de audio remota**, seleccione **Reproducir en este equipo**.</span><span class="sxs-lookup"><span data-stu-id="863d0-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="863d0-129">En **Grabación de audio remota**, seleccione **No grabar**.</span><span class="sxs-lookup"><span data-stu-id="863d0-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="863d0-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="863d0-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="863d0-131">Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.</span><span class="sxs-lookup"><span data-stu-id="863d0-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="863d0-132">Haga clic en **la pestaña** General. En **Equipo,** escriba el nombre del escritorio virtual y, a continuación, haga clic **en Conectar.**</span><span class="sxs-lookup"><span data-stu-id="863d0-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="863d0-133">Iniciar sesión y usar Skype Empresarial en el escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="863d0-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="863d0-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="863d0-134"><a name="SfB_signin"> </a></span></span>

<span data-ttu-id="863d0-135">Una vez habilitado el complemento Lync VDI, el usuario sigue estos pasos al iniciar sesión en Skype Empresarial en el escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="863d0-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="863d0-136">El usuario debe usar sus credenciales en el cliente de Skype Empresarial que se ejecuta en el escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="863d0-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="863d0-137">Después de que Skype Empresarial detecte el complemento Lync VDI, Skype Empresarial pide al usuario que vuelva a escribir las credenciales.</span><span class="sxs-lookup"><span data-stu-id="863d0-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="863d0-138">En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para que no tener que escribir las credenciales en inicios de sesión posteriores.</span><span class="sxs-lookup"><span data-stu-id="863d0-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="863d0-139">Skype Empresarial comienza el emparejamiento con el complemento Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="863d0-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="863d0-140">Mientras esto sucede, el cliente muestra dos iconos en la barra de estado de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="863d0-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="863d0-141">El icono de la parte inferior izquierda indica que no hay dispositivos de audio disponibles y el icono parpadeante en la parte inferior derecha indica que el emparejamiento de VDI está en curso: a.</span><span class="sxs-lookup"><span data-stu-id="863d0-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="863d0-142">Una vez que el emparejamiento de VDI se realiza correctamente, los iconos cambian para indicar el dispositivo de audio que se usará para las llamadas y el emparejamiento de VDI correcto: b.</span><span class="sxs-lookup"><span data-stu-id="863d0-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="863d0-143">Ahora, el usuario puede ver su presencia en dispositivos compatibles con Skype Empresarial que están conectados al equipo local y realizar y responder llamadas como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="863d0-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="863d0-144">Solucionar problemas del complemento Lync VDI</span><span class="sxs-lookup"><span data-stu-id="863d0-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="863d0-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="863d0-145"><a name="tshoot_VDI"> </a></span></span>

<span data-ttu-id="863d0-146">Consulte las secciones siguientes si encuentra problemas después de instalar el complemento Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="863d0-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="863d0-147">Problemas con la instalación del complemento Lync VDI</span><span class="sxs-lookup"><span data-stu-id="863d0-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="863d0-148">Si hay problemas con la instalación del complemento Lync VDI, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="863d0-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="863d0-149">Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.</span><span class="sxs-lookup"><span data-stu-id="863d0-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="863d0-150">Asegúrese de que la protección contra la escritura está desactivada.</span><span class="sxs-lookup"><span data-stu-id="863d0-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="863d0-151">Consulta la documentación del fabricante del dispositivo para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="863d0-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="863d0-152">Resolución de problemas con el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="863d0-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="863d0-153">Cuando se produce un error en el emparejamiento del complemento Lync VDI, el icono de emparejamiento de la parte inferior derecha se muestra como una "X" roja como se muestra:</span><span class="sxs-lookup"><span data-stu-id="863d0-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="863d0-154">Las siguientes son las posibles razones de los errores y las acciones que puede realizar para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="863d0-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="863d0-155">**El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**</span><span class="sxs-lookup"><span data-stu-id="863d0-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="863d0-156">El usuario debe cerrar la sesión de Skype Empresarial e iniciar sesión de nuevo con las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="863d0-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="863d0-157">Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="863d0-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="863d0-158">**Se está ejecutando otra instancia del cliente de escritorio remoto.**</span><span class="sxs-lookup"><span data-stu-id="863d0-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="863d0-159">Si usan la conexión a Escritorio remoto en Windows, los usuarios deben hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="863d0-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="863d0-160">Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="863d0-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="863d0-161">Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="863d0-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="863d0-162">Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**.</span><span class="sxs-lookup"><span data-stu-id="863d0-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="863d0-163">Inicie una nueva sesión de escritorio remoto e intente realizar la conexión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="863d0-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="863d0-164">**Los archivos necesarios no se han instalado correctamente.**</span><span class="sxs-lookup"><span data-stu-id="863d0-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="863d0-165">Después de instalar el complemento en el equipo local, compruebe que estos archivos están presentes en C:\Archivos de programa\Microsoft Office\Office15 (o la letra de unidad adecuada):</span><span class="sxs-lookup"><span data-stu-id="863d0-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="863d0-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="863d0-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="863d0-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="863d0-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="863d0-168">**El cliente de Skype Empresarial se ejecuta en el equipo local.**</span><span class="sxs-lookup"><span data-stu-id="863d0-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="863d0-169">Para usar el complemento Lync VDI, un cliente de Skype Empresarial no debe ejecutarse en el equipo local; de lo contrario, se producirá un error en el emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="863d0-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="863d0-170">Como procedimiento recomendado, el usuario no debe instalar un cliente de Skype Empresarial en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="863d0-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="863d0-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="863d0-171">See also</span></span>
<span data-ttu-id="863d0-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="863d0-172"><a name="tshoot_VDI"> </a></span></span>

[<span data-ttu-id="863d0-173">Planear Skype Empresarial en entornos VDI</span><span class="sxs-lookup"><span data-stu-id="863d0-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
