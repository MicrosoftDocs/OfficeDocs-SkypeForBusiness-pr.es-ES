---
title: Implementar el complemento VDI para Lync con Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: En este tema se describen los procedimientos de implementación para usar Skype empresarial mientras se conecta a un escritorio virtual remoto.
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288757"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a><span data-ttu-id="5ded9-103">Implementar el complemento VDI para Lync con Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5ded9-103">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>
 
<span data-ttu-id="5ded9-104">En este tema se describen los procedimientos de implementación para usar Skype empresarial mientras se conecta a un escritorio virtual remoto.</span><span class="sxs-lookup"><span data-stu-id="5ded9-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> <span data-ttu-id="5ded9-105">Las consideraciones de planeación están en el [plan de Skype empresarial en entornos de VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span><span class="sxs-lookup"><span data-stu-id="5ded9-105">Planning considerations are at [Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md).</span></span>
  
<span data-ttu-id="5ded9-106">El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados.</span><span class="sxs-lookup"><span data-stu-id="5ded9-106">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="5ded9-107">Sus usuarios se encuentran en equipos Windows locales y utilizan clientes en un escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="5ded9-107">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="5ded9-108">Usar Skype empresarial en una conexión como esta requiere software de complemento VDI adicional.</span><span class="sxs-lookup"><span data-stu-id="5ded9-108">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="5ded9-109">Hay dos soluciones disponibles para el componente de complemento VDI: una ofrecida por Microsoft y la otra ofrecida por Citrix.</span><span class="sxs-lookup"><span data-stu-id="5ded9-109">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="5ded9-110">Microsoft recomienda usar la nueva solución de paquete de optimización en tiempo real de HDX en implementaciones nuevas, pero continuará con el complemento de VDI original de Lync durante el resto de su ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5ded9-110">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="5ded9-111">Este tema proporciona detalles sobre cómo implementar el complemento Microsoft Lync VDI, que solo se admite en Windows 7 y Windows 8 o Windows Server 2008, y solo admite clientes de Lync 2013 o Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="5ded9-111">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business clients.</span></span> <span data-ttu-id="5ded9-112">No hay planes de actualizar este complemento, pero el [paquete de optimización en tiempo real de Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) se actualizará según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5ded9-112">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="5ded9-113">Prepare su entorno para el complemento Lync VDI</span><span class="sxs-lookup"><span data-stu-id="5ded9-113">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="5ded9-114"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="5ded9-114"></span></span>

1. <span data-ttu-id="5ded9-115">En Skype empresarial Server, asegúrese de que EnableMediaRedirection se establece en TRUE para todos los usuarios del complemento VDI para Lync.</span><span class="sxs-lookup"><span data-stu-id="5ded9-115">In Skype for Business Server, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="5ded9-116">Para obtener más información, consulte los temas de ayuda para el cmdlet [New-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) y el cmdlet [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5ded9-116">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="5ded9-117">En el servidor del centro de datos, instale el cliente de Skype empresarial en todos los escritorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="5ded9-117">On the data center server, install the Skype for Business client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="5ded9-118">En los equipos locales, instale el complemento VDI de Lync.</span><span class="sxs-lookup"><span data-stu-id="5ded9-118">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="5ded9-119">Ahora, los usuarios deberían conectar un dispositivo como un auricular o una cámara web a sus equipos locales.</span><span class="sxs-lookup"><span data-stu-id="5ded9-119">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="5ded9-120">Configure los parámetros de conexión a Escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="5ded9-120">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="5ded9-121"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="5ded9-121"></span></span>

<span data-ttu-id="5ded9-122">Para preparar la conexión a escritorio remoto para el complemento VDI de Lync, siga estos pasos en el equipo local:</span><span class="sxs-lookup"><span data-stu-id="5ded9-122">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="5ded9-123">Si el equipo local está ejecutando Windows 8, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="5ded9-123">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="5ded9-124">Si el equipo local ejecuta Windows 7 con SP1, instale la versión más reciente de Windows 8 del [cliente de servicios de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="5ded9-124">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="5ded9-125">Inicie el cliente de Servicios de Escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a Escritorio remoto**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-125">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="5ded9-126">Haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-126">Click **Options**.</span></span>
    
4. <span data-ttu-id="5ded9-127">Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ded9-127">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
   - <span data-ttu-id="5ded9-128">En **Reproducción de audio remoto**, seleccione **Reproducir en este equipo**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-128">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
   - <span data-ttu-id="5ded9-129">En **Grabación de audio remoto**, seleccione **No grabar**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-129">Under **Remote audio recording**, select **Do not record**.</span></span>
    
   - <span data-ttu-id="5ded9-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-130">Click **OK**.</span></span>
    
5. <span data-ttu-id="5ded9-131">Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-131">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="5ded9-132">Haga clic en la pestaña **General**. En **Equipo**, escriba el nombre del escritorio virtual y haga clic en **Conectar**. </span><span class="sxs-lookup"><span data-stu-id="5ded9-132">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="5ded9-133">Inicie sesión en Skype Empresarial y úselo en el escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="5ded9-133">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="5ded9-134"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="5ded9-134"></span></span>

<span data-ttu-id="5ded9-135">Después de habilitar el complemento VDI para Lync, el usuario sigue estos pasos al iniciar sesión en Skype empresarial en el escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="5ded9-135">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business on the virtual desktop.</span></span>
  
1. <span data-ttu-id="5ded9-136">El usuario escribe sus credenciales en el cliente de Skype empresarial que se ejecuta en el escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="5ded9-136">The user types his or her credentials in to the Skype for Business client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="5ded9-137">Una vez que Skype empresarial detecta el complemento VDI para Lync, Skype empresarial solicita al usuario que vuelva a escribir las credenciales.</span><span class="sxs-lookup"><span data-stu-id="5ded9-137">After Skype for Business detects the Lync VDI plug-in, Skype for Business prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="5ded9-138">En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para no tener que escribir las credenciales en inicios de sesión posteriores.</span><span class="sxs-lookup"><span data-stu-id="5ded9-138">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="5ded9-139">Skype empresarial comienza a emparejarse con el complemento VDI de Lync.</span><span class="sxs-lookup"><span data-stu-id="5ded9-139">Skype for Business begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="5ded9-140">Mientras eso sucede, el cliente muestra dos iconos en la barra de estado de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="5ded9-140">While that happens, the client displays two icons in the Skype for Business status bar.</span></span> <span data-ttu-id="5ded9-141">El icono de la esquina inferior izquierda indica que no hay dispositivos de audio disponibles, y el icono parpadeante en la esquina inferior derecha indica que el emparejamiento de VDI está en curso: a.</span><span class="sxs-lookup"><span data-stu-id="5ded9-141">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress: a.</span></span> <span data-ttu-id="5ded9-142">Después de que el emparejamiento de VDI se haya realizado correctamente, los iconos cambian para indicar el dispositivo de audio que se usará para las llamadas y el éxito del emparejamiento de VDI: b.</span><span class="sxs-lookup"><span data-stu-id="5ded9-142">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success: b.</span></span> <span data-ttu-id="5ded9-143">Ahora, el usuario puede ver su presencia en dispositivos compatibles con Skype empresarial que están conectados al equipo local, y realizar y contestar llamadas de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="5ded9-143">The user can now see his or her presence on Skype for Business compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="5ded9-144">Solucione problemas del complemento Lync VDI</span><span class="sxs-lookup"><span data-stu-id="5ded9-144">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="5ded9-145"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="5ded9-145"></span></span>

<span data-ttu-id="5ded9-146">Consulte las siguientes secciones si experimenta algún problema después de instalar el complemento Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="5ded9-146">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="5ded9-147">Problemas con la instalación del complemento Lync VDI </span><span class="sxs-lookup"><span data-stu-id="5ded9-147">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="5ded9-148">Si hay problemas con la instalación del complemento de VDI para Lync, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ded9-148">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="5ded9-149">Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.</span><span class="sxs-lookup"><span data-stu-id="5ded9-149">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="5ded9-150">Asegúrese de que la protección contra la escritura está desactivada.</span><span class="sxs-lookup"><span data-stu-id="5ded9-150">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="5ded9-151">Consulte la documentación del fabricante del dispositivo para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5ded9-151">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="5ded9-152">Resolución de problemas con el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="5ded9-152">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="5ded9-153">Cuando se produce un error en el complemento VDI de Lync, el icono de emparejamiento en la esquina inferior derecha se muestra como una "X" de color rojo, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="5ded9-153">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="5ded9-154">A continuación se describen algunas posibles razones de los errores, así como las acciones que puede llevar a cabo para solucionar el problema. </span><span class="sxs-lookup"><span data-stu-id="5ded9-154">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="5ded9-155">**El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**</span><span class="sxs-lookup"><span data-stu-id="5ded9-155">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="5ded9-156">El usuario debe cerrar la sesión de Skype empresarial e iniciarla de nuevo con las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="5ded9-156">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="5ded9-157">Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ded9-157">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="5ded9-158">**Se está ejecutando otra instancia del cliente de escritorio remoto.**</span><span class="sxs-lookup"><span data-stu-id="5ded9-158">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="5ded9-159">Si usan conexión a escritorio remoto en Windows, los usuarios deben hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ded9-159">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="5ded9-160">Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-160">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="5ded9-161">Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="5ded9-161">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="5ded9-162">Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**. </span><span class="sxs-lookup"><span data-stu-id="5ded9-162">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="5ded9-163">Inicie una nueva sesión de escritorio remoto e intente establecer la conexión de nuevo. </span><span class="sxs-lookup"><span data-stu-id="5ded9-163">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="5ded9-164">**Los archivos necesarios no se han instalado correctamente.**</span><span class="sxs-lookup"><span data-stu-id="5ded9-164">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="5ded9-165">Una vez instalado el complemento en el equipo local, asegúrese de que los siguientes archivos estén presentes en el directorio C:\Archivos de programa\Microsoft Office\Office15 (o la letra de la unidad que corresponda):</span><span class="sxs-lookup"><span data-stu-id="5ded9-165">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="5ded9-166">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="5ded9-166">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="5ded9-167">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="5ded9-167">UcVdi.dll</span></span>
    
- <span data-ttu-id="5ded9-168">**El cliente de Skype empresarial se está ejecutando en el equipo local.**</span><span class="sxs-lookup"><span data-stu-id="5ded9-168">**The Skype for Business client is running on the local computer.**</span></span>
    
    <span data-ttu-id="5ded9-169">Para usar el complemento VDI para Lync, un cliente de Skype empresarial no debe estar ejecutándose en el equipo local; de lo contrario, se producirá un error de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="5ded9-169">To use the Lync VDI plug-in, a Skype for Business client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="5ded9-170">Como práctica recomendada, el usuario no debe instalar un cliente de Skype empresarial en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="5ded9-170">As a best practice, the user should not install a Skype for Business client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5ded9-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ded9-171">See also</span></span>
<span data-ttu-id="5ded9-172"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="5ded9-172"></span></span>

[<span data-ttu-id="5ded9-173">Plan for Skype for Business in VDI environments</span><span class="sxs-lookup"><span data-stu-id="5ded9-173">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
