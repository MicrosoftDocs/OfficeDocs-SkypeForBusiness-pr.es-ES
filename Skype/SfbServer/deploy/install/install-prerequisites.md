---
title: Instalar requisitos previos para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Summary: Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="f6818-104">Instalar requisitos previos para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6818-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f6818-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6818-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="f6818-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="f6818-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="f6818-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span><span class="sxs-lookup"><span data-stu-id="f6818-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="f6818-108">The requirements are based on the role the server will fulfill in the topology.</span><span class="sxs-lookup"><span data-stu-id="f6818-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="f6818-109">You can do steps 1 through 5 in any order.</span><span class="sxs-lookup"><span data-stu-id="f6818-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="f6818-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span><span class="sxs-lookup"><span data-stu-id="f6818-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="f6818-111">Installing prerequisites is step 1 of 8.</span><span class="sxs-lookup"><span data-stu-id="f6818-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="f6818-113">Configurar Windows Server</span><span class="sxs-lookup"><span data-stu-id="f6818-113">Setup Windows Server</span></span>

<span data-ttu-id="f6818-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span><span class="sxs-lookup"><span data-stu-id="f6818-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="f6818-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6818-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="f6818-p105">Este procedimiento utiliza Windows Server 2012 R2. Es posible que el procedimiento sea un poco diferente si usa una versión de Windows Server distinta.</span><span class="sxs-lookup"><span data-stu-id="f6818-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f6818-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f6818-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="f6818-120">Vea los pasos del vídeo para **instalar los requisitos previos**:</span><span class="sxs-lookup"><span data-stu-id="f6818-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="f6818-121">Instalar las características y los roles necesarios para los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="f6818-121">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="f6818-122">Abra el Administrador de servidores y haga clic en **Agregar roles y características**.</span><span class="sxs-lookup"><span data-stu-id="f6818-122">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="f6818-123">Lea la página **Antes de empezar** para conocer la instalación de los roles y las características de Windows Server y, luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6818-123">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="f6818-124">Seleccione **Instalación basada en características o en roles** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6818-124">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="f6818-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span><span class="sxs-lookup"><span data-stu-id="f6818-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="f6818-126">Seleccione el rol **Servidor web (IIS)**. Cuando se abra la ventana de características necesarias, haga clic en **Agregar características** y, luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6818-126">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f6818-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6818-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="f6818-128">Here's an abbreviated list:</span><span class="sxs-lookup"><span data-stu-id="f6818-128">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="f6818-129">.NET Framework Features</span><span class="sxs-lookup"><span data-stu-id="f6818-129">.NET Framework Features</span></span>
    
   - <span data-ttu-id="f6818-130">Servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="f6818-130">WCF Services</span></span>
    
   - <span data-ttu-id="f6818-131">Activación HTTP</span><span class="sxs-lookup"><span data-stu-id="f6818-131">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f6818-p107">La activación HTTP necesita características adicionales. Haga clic en **Agregar características** en el cuadro de diálogo de advertencia que se abre al seleccionar Activación HTTP.</span><span class="sxs-lookup"><span data-stu-id="f6818-p107">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="f6818-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span><span class="sxs-lookup"><span data-stu-id="f6818-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="f6818-135">Herramientas de administración remota del servidor</span><span class="sxs-lookup"><span data-stu-id="f6818-135">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="f6818-136">Herramientas de administración de roles</span><span class="sxs-lookup"><span data-stu-id="f6818-136">Role Administration Tools</span></span>
    
   - <span data-ttu-id="f6818-137">AD DS</span><span class="sxs-lookup"><span data-stu-id="f6818-137">AD DS</span></span> 
    
   - <span data-ttu-id="f6818-138">AD LDS</span><span class="sxs-lookup"><span data-stu-id="f6818-138">AD LDS</span></span>
    
   - <span data-ttu-id="f6818-139">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="f6818-139">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="f6818-140">Haga clic en **Siguiente** para continuar con el asistente.</span><span class="sxs-lookup"><span data-stu-id="f6818-140">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="f6818-141">Lea las notas sobre el **Rol de servidor web (IIS)** y, luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6818-141">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="f6818-142">Seleccione los siguientes **Servicios de rol de servidor web (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="f6818-142">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="f6818-143">Características HTTP comunes</span><span class="sxs-lookup"><span data-stu-id="f6818-143">Common HTTP Features</span></span>
    
   - <span data-ttu-id="f6818-144">Documento predeterminado</span><span class="sxs-lookup"><span data-stu-id="f6818-144">Default Document</span></span>
    
   - <span data-ttu-id="f6818-145">Examen de directorios</span><span class="sxs-lookup"><span data-stu-id="f6818-145">Directory Browsing</span></span>
    
   - <span data-ttu-id="f6818-146">Errores HTTP</span><span class="sxs-lookup"><span data-stu-id="f6818-146">HTTP Errors</span></span>
    
   - <span data-ttu-id="f6818-147">Contenido estático</span><span class="sxs-lookup"><span data-stu-id="f6818-147">Static Content</span></span>
    
   - <span data-ttu-id="f6818-148">Estado y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f6818-148">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="f6818-149">Registro HTTP</span><span class="sxs-lookup"><span data-stu-id="f6818-149">HTTP Logging</span></span>
    
   - <span data-ttu-id="f6818-150">Herramientas de registro</span><span class="sxs-lookup"><span data-stu-id="f6818-150">Logging Tools</span></span>
    
   - <span data-ttu-id="f6818-151">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="f6818-151">Tracing</span></span>
    
   - <span data-ttu-id="f6818-152">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="f6818-152">Performance</span></span>
    
   - <span data-ttu-id="f6818-153">Compresión de contenido estático</span><span class="sxs-lookup"><span data-stu-id="f6818-153">Static Content Compression</span></span>
    
   - <span data-ttu-id="f6818-154">Compresión de contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="f6818-154">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="f6818-155">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f6818-155">Security</span></span>
    
   - <span data-ttu-id="f6818-156">Filtro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="f6818-156">Request Filtering</span></span>
    
   - <span data-ttu-id="f6818-157">Autenticación por asignación de certificados de clientes</span><span class="sxs-lookup"><span data-stu-id="f6818-157">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="f6818-158">Autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="f6818-158">Windows Authentication</span></span>
    
   - <span data-ttu-id="f6818-159">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f6818-159">Application Development</span></span>
    
   - <span data-ttu-id="f6818-160">Extensibilidad de .NET 3.5</span><span class="sxs-lookup"><span data-stu-id="f6818-160">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="f6818-161">Extensibilidad de .NET 4.5</span><span class="sxs-lookup"><span data-stu-id="f6818-161">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="f6818-162">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="f6818-162">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="f6818-163">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="f6818-163">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="f6818-164">Extensiones ISAPI</span><span class="sxs-lookup"><span data-stu-id="f6818-164">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="f6818-165">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="f6818-165">ISAPI Filters</span></span>
    
   - <span data-ttu-id="f6818-166">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="f6818-166">Management Tools</span></span>
    
   - <span data-ttu-id="f6818-167">Consola de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="f6818-167">IIS Management Console</span></span>
    
   - <span data-ttu-id="f6818-168">Scripts y herramientas de administración de IIS</span><span class="sxs-lookup"><span data-stu-id="f6818-168">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="f6818-169">Haga clic en **Siguiente** para continuar con el asistente.</span><span class="sxs-lookup"><span data-stu-id="f6818-169">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="f6818-170">Revise las selecciones de la instalación para asegurarse de haber seleccionado todos los requisitos y, luego, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f6818-170">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f6818-171">De forma predeterminada, Windows Server 2012 R2 no instala todos los archivos de origen de las características necesarias.</span><span class="sxs-lookup"><span data-stu-id="f6818-171">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="f6818-172">Si el servidor no está conectado a Internet, necesitará insertar el disco de Windows Server 2012 R2 y seleccionar **Especifique una ruta de acceso de origen alternativa** para instalar las características necesarias.</span><span class="sxs-lookup"><span data-stu-id="f6818-172">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="f6818-173">Los archivos de origen se encuentran en el directorio sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="f6818-173">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="f6818-174">Por ejemplo, si el disco de Windows Server 2012 R2 se encuentra en la unidad D, la ruta de acceso será `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="f6818-174">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="f6818-175">> It is important that you have the latest updates from Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f6818-175">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="f6818-176">Si no se encuentra conectado a Internet, necesitará instalar todas las actualizaciones relevantes de manera manual, así como también todos los requisitos previos de las actualizaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="f6818-176">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="f6818-177">Cuando el cuadro de diálogo indica que se ha completado la instalación, necesitará reiniciar el servidor para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="f6818-177">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="f6818-178">Ejecute **Windows Update** nuevamente para comprobar si hay actualizaciones de los roles y los servicios que se instalaron.</span><span class="sxs-lookup"><span data-stu-id="f6818-178">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="f6818-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span><span class="sxs-lookup"><span data-stu-id="f6818-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="f6818-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="f6818-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="f6818-181">The prerequisites can be installed by running the following PowerShell command.</span><span class="sxs-lookup"><span data-stu-id="f6818-181">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="f6818-182">Note that the command looks for source files in a specific order.</span><span class="sxs-lookup"><span data-stu-id="f6818-182">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="f6818-183">If you are online, the command accesses Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f6818-183">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="f6818-184">However, if you are offline, you need to make sure the source files are available to the command.</span><span class="sxs-lookup"><span data-stu-id="f6818-184">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="f6818-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6818-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="f6818-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span><span class="sxs-lookup"><span data-stu-id="f6818-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="f6818-187">Los servidores que desempeñan roles distintos del de servidor front-end (como el rol de director, chat persistente o servidor perimetral) tienen sus propios requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="f6818-187">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="f6818-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6818-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

