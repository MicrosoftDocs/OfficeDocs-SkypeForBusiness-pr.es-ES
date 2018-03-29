---
title: Implementar el complemento Lync VDI con Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Este tema describen los procedimientos de implementación para utilizar Skype para el negocio al conectarse a un escritorio virtual remoto.
ms.openlocfilehash: a8f95903f3c06fd953b8d97ba829d4f23e8d72b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a><span data-ttu-id="f01eb-103">Implementar el complemento Lync VDI con Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="f01eb-103">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f01eb-104">Este tema describen los procedimientos de implementación para utilizar Skype para el negocio al conectarse a un escritorio virtual remoto.</span><span class="sxs-lookup"><span data-stu-id="f01eb-104">This topic discusses deployment procedures for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="f01eb-105">El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados.</span><span class="sxs-lookup"><span data-stu-id="f01eb-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="f01eb-106">Sus usuarios se encuentran en equipos Windows locales y utilizan clientes en un escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f01eb-106">Their users are on local Windows computers and using clients on a virtual desktop.</span></span> <span data-ttu-id="f01eb-107">Usando Skype para el negocio en una conexión que requiere software adicional de Plug-in de VDI.</span><span class="sxs-lookup"><span data-stu-id="f01eb-107">Using Skype for Business on a connection like that requires additional VDI plug-in software.</span></span>
  
<span data-ttu-id="f01eb-108">Existen dos soluciones disponibles para el componente de complemento de VDI - uno ofrecidos por Microsoft y otro ofrecido por Citrix.</span><span class="sxs-lookup"><span data-stu-id="f01eb-108">There are two solutions available for the VDI plug-in component - one offered by Microsoft and one offered by Citrix.</span></span> <span data-ttu-id="f01eb-109">Microsoft recomienda el uso de la nueva solución HDX RealTime Optimization Pack en nuevas implementaciones, pero seguirá siendo compatible con el complemento de VDI Lync original para el resto de su ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="f01eb-109">Microsoft recommends using the new HDX RealTime Optimization Pack solution in new deployments but will continue to support the original Lync VDI Plug-in for the remainder of its lifecycle.</span></span> 
  
<span data-ttu-id="f01eb-110">Este tema proporciona detalles sobre la implementación de Microsoft Lync VDI Plug-in, que sólo se admite en Windows 7 y Windows 8 o Windows Server 2008 y sólo es compatible con Lync 2013 o Skype para clientes de negocios 2015.</span><span class="sxs-lookup"><span data-stu-id="f01eb-110">This topic provides details on deploying the Microsoft Lync VDI plug-in, which is only supported on Windows 7 and Windows 8 or Windows Server 2008, and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="f01eb-111">No hay planes para actualizar este complemento, pero el [Paquete de optimización de Citrix HDX en tiempo real](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) de Skype para empresas se actualizarán según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f01eb-111">There are no plans to update this plugin, but the [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business will be updated as needed.</span></span>
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a><span data-ttu-id="f01eb-112">Prepare su entorno para el complemento Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f01eb-112">Prepare your environment for the Lync VDI plug-in</span></span>
<span data-ttu-id="f01eb-113"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f01eb-113"></span></span>

1. <span data-ttu-id="f01eb-114">En Skype para Business Server 2015, asegúrese de que EnableMediaRedirection está establecido en TRUE para todos los usuarios de Plug-in de Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f01eb-114">In Skype for Business Server 2015, ensure that EnableMediaRedirection is set to TRUE for all Lync VDI plug-in users.</span></span> <span data-ttu-id="f01eb-115">Para obtener más información, vea los temas de ayuda para el cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) y el cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f01eb-115">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet.</span></span>
    
2. <span data-ttu-id="f01eb-116">En el servidor de centro de datos, instale el Skype para cliente de negocios 2015 en todos los escritorios virtuales.</span><span class="sxs-lookup"><span data-stu-id="f01eb-116">On the data center server, install the Skype for Business 2015 client on all virtual desktops.</span></span>
    
3. <span data-ttu-id="f01eb-117">En los equipos locales, instale el plug-in de VDI Lync.</span><span class="sxs-lookup"><span data-stu-id="f01eb-117">On the local computers, install the Lync VDI plug-in.</span></span>
    
    <span data-ttu-id="f01eb-118">Ahora, los usuarios deberían conectar un dispositivo como un auricular o una cámara web a sus equipos locales.</span><span class="sxs-lookup"><span data-stu-id="f01eb-118">Users should now connect a device like a headset or webcam to their local computer.</span></span>
    
## <a name="configure-remote-desktop-connection-settings"></a><span data-ttu-id="f01eb-119">Configure los parámetros de conexión a Escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="f01eb-119">Configure Remote Desktop Connection settings</span></span>
<span data-ttu-id="f01eb-120"><a name="Prepare_vdi"> </a></span><span class="sxs-lookup"><span data-stu-id="f01eb-120"></span></span>

<span data-ttu-id="f01eb-121">Para preparar la VDI Lync complemento conexión a Escritorio remoto, siga estos pasos en el equipo local:</span><span class="sxs-lookup"><span data-stu-id="f01eb-121">To prepare Remote Desktop Connection for the Lync VDI plug-in, follow these steps on the local computer:</span></span>
  
1. <span data-ttu-id="f01eb-122">Si el equipo local ejecuta Windows 8, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="f01eb-122">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="f01eb-123">Si el equipo local ejecuta Windows 7 con SP1, instale la versión 8 de Windows más reciente del [cliente de servicios de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span><span class="sxs-lookup"><span data-stu-id="f01eb-123">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the [Remote Desktop Services client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span>
    
2. <span data-ttu-id="f01eb-124">Inicie el cliente de Servicios de Escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a Escritorio remoto**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-124">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>
    
3. <span data-ttu-id="f01eb-125">Haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-125">Click **Options**.</span></span>
    
4. <span data-ttu-id="f01eb-126">Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f01eb-126">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
  - <span data-ttu-id="f01eb-127">En **Reproducción de audio remoto**, seleccione **Reproducir en este equipo**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-127">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
  - <span data-ttu-id="f01eb-128">En **Grabación de audio remoto**, seleccione **No grabar**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-128">Under **Remote audio recording**, select **Do not record**.</span></span>
    
  - <span data-ttu-id="f01eb-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-129">Click **OK**.</span></span>
    
5. <span data-ttu-id="f01eb-130">Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-130">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>
    
6. <span data-ttu-id="f01eb-131">Haga clic en la pestaña **General**. En **Equipo**, escriba el nombre del escritorio virtual y haga clic en **Conectar**. </span><span class="sxs-lookup"><span data-stu-id="f01eb-131">Click the **General** tab. In **Computer**, type the name of the virtual desktop, and then click **Connect**.</span></span> 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a><span data-ttu-id="f01eb-132">Inicie sesión en Skype Empresarial y úselo en el escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="f01eb-132">Sign in and use Skype for Business on the virtual desktop</span></span>
<span data-ttu-id="f01eb-133"><a name="SfB_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="f01eb-133"></span></span>

<span data-ttu-id="f01eb-134">Después de habilitar el complemento de VDI Lync, el usuario sigue estos pasos al iniciar sesión en Skype para el año 2015 de negocio en el escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f01eb-134">After the Lync VDI plug-in is enabled, the user follows these steps when signing in to Skype for Business 2015 on the virtual desktop.</span></span>
  
1. <span data-ttu-id="f01eb-135">El usuario escribe sus credenciales en para el Skype para 2015 de negocio cliente que se ejecuta en el escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f01eb-135">The user types his or her credentials in to the Skype for Business 2015 client running on the virtual desktop.</span></span>
    
2. <span data-ttu-id="f01eb-136">Una vez Skype para negocios 2015 detecta el plug-in de VDI Lync, Skype para negocios 2015 pide al usuario que vuelva a escribir las credenciales.</span><span class="sxs-lookup"><span data-stu-id="f01eb-136">After Skype for Business 2015 detects the Lync VDI plug-in, Skype for Business 2015 prompts the user to re-enter the credentials.</span></span> <span data-ttu-id="f01eb-137">En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para no tener que escribir las credenciales en inicios de sesión posteriores.</span><span class="sxs-lookup"><span data-stu-id="f01eb-137">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>
    
3. <span data-ttu-id="f01eb-138">Skype para negocios 2015 comienza el emparejamiento con el plug-in de VDI de Lync.</span><span class="sxs-lookup"><span data-stu-id="f01eb-138">Skype for Business 2015 begins pairing with the Lync VDI plug-in.</span></span> <span data-ttu-id="f01eb-139">Mientras Eso sucede, el cliente muestra dos iconos en el Skype para negocios 2015 barra de estado.</span><span class="sxs-lookup"><span data-stu-id="f01eb-139">While that happens, the client displays two icons in the Skype for Business 2015 status bar.</span></span> <span data-ttu-id="f01eb-140">El icono que aparece en la parte inferior izquierda indica que no hay dispositivos de audio disponibles y el icono intermitente en la parte inferior derecha, que el emparejamiento de VDI está en curso:</span><span class="sxs-lookup"><span data-stu-id="f01eb-140">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that VDI pairing is in progress:</span></span>
    4. <span data-ttu-id="f01eb-141">Una vez realizado el emparejamiento de VDI, los iconos cambian para indicar el dispositivo de audio que se utilizará para las llamadas y el emparejamiento de VDI:</span><span class="sxs-lookup"><span data-stu-id="f01eb-141">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    5. <span data-ttu-id="f01eb-142">Ahora el usuario puede ver su presencia en Skype para negocios 2015 dispositivos compatibles que están conectados al equipo local y colocarán y responder a las llamadas como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="f01eb-142">The user can now see his or her presence on Skype for Business 2015 compatible devices that are connected to the local computer, and place and answer calls as usual.</span></span>
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a><span data-ttu-id="f01eb-143">Solucione problemas del complemento Lync VDI</span><span class="sxs-lookup"><span data-stu-id="f01eb-143">Troubleshoot the Lync VDI plug-in</span></span>
<span data-ttu-id="f01eb-144"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f01eb-144"></span></span>

<span data-ttu-id="f01eb-145">Consulte las siguientes secciones si experimenta algún problema después de instalar el complemento Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="f01eb-145">Refer to the following sections if you encounter issues after installing the Lync VDI plug-in.</span></span>
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a><span data-ttu-id="f01eb-146">Problemas con la instalación del complemento Lync VDI </span><span class="sxs-lookup"><span data-stu-id="f01eb-146">Issues with installing the Lync VDI Plug-in</span></span>

<span data-ttu-id="f01eb-147">Si hay problemas al instalar el complemento de VDI Lync, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f01eb-147">If there are issues with installing the Lync VDI plug-in, check the following:</span></span>
  
- <span data-ttu-id="f01eb-148">Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.</span><span class="sxs-lookup"><span data-stu-id="f01eb-148">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>
    
- <span data-ttu-id="f01eb-149">Asegúrese de que la protección contra la escritura está desactivada.</span><span class="sxs-lookup"><span data-stu-id="f01eb-149">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="f01eb-150">Consulte la documentación del fabricante de su dispositivo para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f01eb-150">Refer to your device manufacturer's documentation for instructions.</span></span>
    
### <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="f01eb-151">Resolución de problemas con el emparejamiento</span><span class="sxs-lookup"><span data-stu-id="f01eb-151">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="f01eb-152">Cuando Lync VDI complemento sincronización falla, el icono de emparejamiento en el inferior derecho se muestra como una "X" roja como se muestra:</span><span class="sxs-lookup"><span data-stu-id="f01eb-152">When Lync VDI plug-in pairing fails, the pairing icon in the lower right displays as a red "X" as shown:</span></span> 
  
<span data-ttu-id="f01eb-153">A continuación se describen algunas posibles razones de los errores, así como las acciones que puede llevar a cabo para solucionar el problema. </span><span class="sxs-lookup"><span data-stu-id="f01eb-153">The following are possible reasons for failures and the actions you can take to correct the problem.</span></span> 
  
- <span data-ttu-id="f01eb-154">**El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**</span><span class="sxs-lookup"><span data-stu-id="f01eb-154">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="f01eb-155">El usuario debe cerrar la sesión de Skype para empresas y vuelve a identificarte con las credenciales correctas.</span><span class="sxs-lookup"><span data-stu-id="f01eb-155">The user should sign out of Skype for Business and sign in again with the correct credentials.</span></span> <span data-ttu-id="f01eb-156">Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="f01eb-156">The pairing dialog box will reappear and show whether pairing is successful.</span></span>
    
- <span data-ttu-id="f01eb-157">**Se está ejecutando otra instancia del cliente de escritorio remoto.**</span><span class="sxs-lookup"><span data-stu-id="f01eb-157">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="f01eb-158">Si están usando conexión a Escritorio remoto en Windows, los usuarios deberían hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f01eb-158">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
1. <span data-ttu-id="f01eb-159">Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-159">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
2. <span data-ttu-id="f01eb-160">Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="f01eb-160">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
3. <span data-ttu-id="f01eb-161">Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**. </span><span class="sxs-lookup"><span data-stu-id="f01eb-161">Highlight each **mstsc.exe** process and then click **End Process**.</span></span> 
    
4. <span data-ttu-id="f01eb-162">Inicie una nueva sesión de escritorio remoto e intente establecer la conexión de nuevo. </span><span class="sxs-lookup"><span data-stu-id="f01eb-162">Start a new remote desktop session and try connecting again.</span></span> 
    
- <span data-ttu-id="f01eb-163">**Los archivos necesarios no se han instalado correctamente.**</span><span class="sxs-lookup"><span data-stu-id="f01eb-163">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="f01eb-164">Una vez instalado el complemento en el equipo local, asegúrese de que los siguientes archivos estén presentes en el directorio C:\Archivos de programa\Microsoft Office\Office15 (o la letra de la unidad que corresponda):</span><span class="sxs-lookup"><span data-stu-id="f01eb-164">After the plug-in is installed on the local computer, check to make sure that these files are present under C:\Program Files\Microsoft Office\Office15 (or the appropriate drive letter):</span></span>
    
  - <span data-ttu-id="f01eb-165">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="f01eb-165">LyncVdiPlugin.dll</span></span>
    
  - <span data-ttu-id="f01eb-166">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="f01eb-166">UcVdi.dll</span></span>
    
- <span data-ttu-id="f01eb-167">**El Skype para 2015 de negocio cliente está ejecutando en el equipo local.**</span><span class="sxs-lookup"><span data-stu-id="f01eb-167">**The Skype for Business 2015 client is running on the local computer.**</span></span>
    
    <span data-ttu-id="f01eb-168">Para utilizar el complemento, que un Skype para cliente de negocios 2015 no debe ejecutarse en el equipo local de VDI Lync, emparejamiento de lo contrario se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="f01eb-168">To use the Lync VDI plug-in, a Skype for Business 2015 client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="f01eb-169">Como práctica recomendada, el usuario no debe instalar un Skype para 2015 de negocio cliente en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f01eb-169">As a best practice, the user should not install a Skype for Business 2015 client on the local computer.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f01eb-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="f01eb-170">See also</span></span>
<span data-ttu-id="f01eb-171"><a name="tshoot_VDI"> </a></span><span class="sxs-lookup"><span data-stu-id="f01eb-171"></span></span>

#### 

[<span data-ttu-id="f01eb-172">Plan de Skype para el negocio en entornos de VDI</span><span class="sxs-lookup"><span data-stu-id="f01eb-172">Plan for Skype for Business in VDI environments</span></span>](../../plan-your-deployment/clients-and-devices/vdi-environments.md)

