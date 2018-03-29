---
title: Actualizar el administrador de estadísticas para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumen: Leer este tema para aprender a actualizar estadísticas Manager para Skype para Business Server 2015.'
ms.openlocfilehash: e5a9dd230f16313388cbb9a51e50910979e6c79c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="45963-103">Actualizar el administrador de estadísticas para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="45963-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="45963-104">**Resumen:** Lea este tema para aprender a actualizar estadísticas Manager para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="45963-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="45963-105">Este tema describe cómo actualizar una instalación existente del Administrador de estadísticas de Skype para Business Server, una potente herramienta que le permite ver Skype para los datos de rendimiento y la salud de Business Server en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="45963-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="45963-106">Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web del Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="45963-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="45963-107">Para obtener más información acerca del Administrador de las estadísticas y las nuevas características de la versión 1.1, vea [Planear Administrador de estadísticas para Skype para Business Server 2015](plan.md) e [Implementar Administrador de estadísticas de Skype para Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="45963-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="45963-108">Para obtener información acerca de los problemas conocidos que se han corregido en la versión 1.1, vea [Problemas conocidos corregidos en la versión 1.1](upgrade.md#BKMK_Fixed).</span><span class="sxs-lookup"><span data-stu-id="45963-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="45963-109">Existen dos métodos para actualizar:</span><span class="sxs-lookup"><span data-stu-id="45963-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="45963-110">**Actualización automática**.</span><span class="sxs-lookup"><span data-stu-id="45963-110">**Automated upgrade.**</span></span> <span data-ttu-id="45963-111">Este método utiliza una secuencia de comandos automatizada.</span><span class="sxs-lookup"><span data-stu-id="45963-111">This method uses an automated script.</span></span> <span data-ttu-id="45963-112">Es el método más sencillo y debe ser aplicable a todos los escenarios de actualización.</span><span class="sxs-lookup"><span data-stu-id="45963-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="45963-113">**Actualización manual**.</span><span class="sxs-lookup"><span data-stu-id="45963-113">**Manual upgrade.**</span></span> <span data-ttu-id="45963-114">Este método se proporciona como un plan de copia de seguridad en el caso inusual que se produce un error en la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="45963-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="45963-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="45963-115">Prerequisites</span></span>

<span data-ttu-id="45963-116">Antes de realizar la actualización, asegúrese de que tiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="45963-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="45963-117">Huella digital del certificado del agente de escucha activa</span><span class="sxs-lookup"><span data-stu-id="45963-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="45963-118">Contraseña del servicio de escucha (introducida en la instalación de la escucha y de cada agente)</span><span class="sxs-lookup"><span data-stu-id="45963-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="45963-119">Configuración del certificado SSL para el sitio web</span><span class="sxs-lookup"><span data-stu-id="45963-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="45963-120">Actualización automática</span><span class="sxs-lookup"><span data-stu-id="45963-120">Automated upgrade</span></span>

<span data-ttu-id="45963-121">El script recopilará la información del certificado actual y la contraseña de escucha, desinstalará la versión anterior del producto y, a continuación, instalará la nueva versión del producto.</span><span class="sxs-lookup"><span data-stu-id="45963-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="45963-122">La instancia Redis instalada en el servidor no se tocará, de modo que los datos almacenados en la caché se conservarán durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="45963-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="45963-123">Coloque los archivos MSI para la nueva versión del agente, agente de escucha y sitio Web junto con la secuencia de comandos de actualización StatsMan.ps1 en una sola carpeta en el equipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="45963-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="45963-124">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45963-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="45963-125">Actualice el componente de escucha:</span><span class="sxs-lookup"><span data-stu-id="45963-125">Upgrade the Listener component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Listener
  ```

> [!NOTE]
> <span data-ttu-id="45963-126">La contraseña del servicio Administrador de estadísticas se mostrará en texto sin cifrar en la línea de comandos que se pasa al instalador.</span><span class="sxs-lookup"><span data-stu-id="45963-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="45963-127">Asegúrese de blindar el monitor según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="45963-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="45963-128">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="45963-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="45963-129">Responda Sí.</span><span class="sxs-lookup"><span data-stu-id="45963-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="45963-130">Si el servicio de escucha se está ejecutando, se le pedirá que cierre la aplicación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="45963-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="45963-131">Permitir que la aplicación se cierre (el oyente Gestor de estadísticas se detendrá el servicio).</span><span class="sxs-lookup"><span data-stu-id="45963-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="45963-132">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="45963-132">Continue the install process.</span></span> <span data-ttu-id="45963-133">Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="45963-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="45963-134">Si no es así, agregue los valores que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="45963-134">If not, add the values you saved before continuing.</span></span>
    
3. <span data-ttu-id="45963-135">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45963-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="45963-136">Actualice el componente del sitio web:</span><span class="sxs-lookup"><span data-stu-id="45963-136">Upgrade the Website component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Website
  ```

1. <span data-ttu-id="45963-137">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="45963-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="45963-138">Responda Sí.</span><span class="sxs-lookup"><span data-stu-id="45963-138">Answer Yes.</span></span>
    
2. <span data-ttu-id="45963-139">Si el servicio de agente se está ejecutando, se le pedirá que cierre la aplicación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="45963-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="45963-140">Permita el cierre de la aplicación (el servicio de agente StatsMan se detendrá).</span><span class="sxs-lookup"><span data-stu-id="45963-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
3. <span data-ttu-id="45963-141">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="45963-141">Continue the install process.</span></span> <span data-ttu-id="45963-142">Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="45963-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="45963-143">Si no es así, agregue los valores que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="45963-143">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="45963-144">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45963-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="45963-145">Actualice el componente de agente:</span><span class="sxs-lookup"><span data-stu-id="45963-145">Upgrade the Agent component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Agent
  ```

1. <span data-ttu-id="45963-146">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="45963-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="45963-147">Responda Sí.</span><span class="sxs-lookup"><span data-stu-id="45963-147">Answer Yes.</span></span>
    
2. <span data-ttu-id="45963-148">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="45963-148">Continue the install process.</span></span> <span data-ttu-id="45963-149">Verá que el puerto del sitio web se ha rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="45963-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="45963-150">Si no es así, agregue el valor que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="45963-150">If not, add the value you saved before continuing.</span></span>
    
3. <span data-ttu-id="45963-151">Compruebe que el sitio web funciona como se espera mediante el explorador.</span><span class="sxs-lookup"><span data-stu-id="45963-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="45963-152">La actualización del agente se puede usar con el conmutador -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="45963-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="45963-153">Esto permitirá que el proceso de instalación/desinstalación se ejecute en silencio, lo que permite que herramientas como PSExec ejecuten la actualización de forma remota en un gran número de servidores.</span><span class="sxs-lookup"><span data-stu-id="45963-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="45963-154">Actualización manual</span><span class="sxs-lookup"><span data-stu-id="45963-154">Manual upgrade</span></span>

<span data-ttu-id="45963-155">Si, por algún motivo, se produce un error durante la actualización automática, puede realizar una actualización manual siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="45963-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="45963-156">	En el equipo de escucha, desinstale la escucha, el sitio web y el agente (si se instaló en este servidor) mediante el panel de control Programas y características.  </span><span class="sxs-lookup"><span data-stu-id="45963-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="45963-157"> Mantenga Redis instalado para que los datos de la caché se conserven durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="45963-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="45963-p119">	Instale las nuevas versiones de los componentes, incluidos los valores que guardó anteriormente cuando se le pidan. Para obtener más información acerca de cómo instalar los componentes, vea [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="45963-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="45963-160">Problemas conocidos corregidos en la versión 1.1</span><span class="sxs-lookup"><span data-stu-id="45963-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="45963-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="45963-161"></span></span>

<span data-ttu-id="45963-162">En la versión 1.1 se han corregido los siguientes problemas conocidos:</span><span class="sxs-lookup"><span data-stu-id="45963-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="45963-163">Interfaz de usuario/servidor/agente - numerosos confiabilidad significativa y mejoras en el rendimiento</span><span class="sxs-lookup"><span data-stu-id="45963-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="45963-164">Interfaz de usuario: control de filtro principal ahora ordena correctamente con diferentes casos (se otorga gente piense determinados servidores no estaban en el sistema cuando eran)</span><span class="sxs-lookup"><span data-stu-id="45963-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="45963-165">Servidor: los componentes de servidor ahora se instalarán en servidores que no sean en inglés</span><span class="sxs-lookup"><span data-stu-id="45963-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="45963-166">Servidor/Agente: en algunos casos, los componentes de agente y servidor no se instalaban con errores .NET debido a una versión concreta de .NET 4.0.</span><span class="sxs-lookup"><span data-stu-id="45963-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="45963-167">Se ha solucionado este problema.</span><span class="sxs-lookup"><span data-stu-id="45963-167">This has been resolved.</span></span>
    
- <span data-ttu-id="45963-168">Agente: registro de eventos extendidos agregado para el agente de StatsMan.</span><span class="sxs-lookup"><span data-stu-id="45963-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="45963-169">El agente ya no se bloqueará cuando se instale en un servidor que no esté en la topología y esto no se registrará en el registro de eventos, junto con muchas otras posibles condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="45963-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="45963-170">Interfaz de usuario - clientes Web mediante el Explorador de Chrome vería varias solicitudes de inicio de sesión cuando utiliza un equipo de cliente no unido al mismo grupo de trabajo o dominio que el servidor Manager de estadísticas Web.</span><span class="sxs-lookup"><span data-stu-id="45963-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="45963-171">Ahora solo se requiere un único inicio de sesión por cada sesión.</span><span class="sxs-lookup"><span data-stu-id="45963-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="45963-172">Para más información</span><span class="sxs-lookup"><span data-stu-id="45963-172">For more information</span></span>
<span data-ttu-id="45963-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="45963-173"></span></span>

<span data-ttu-id="45963-174">Para obtener más información, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45963-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="45963-175">Plan para el Gestor de estadísticas de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="45963-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="45963-176">Implementar el administrador estadísticas de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="45963-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="45963-177">Solucionar problemas de administrador de estadísticas de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="45963-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="45963-178">Skype para blog Business Manager de estadísticas de servidor</span><span class="sxs-lookup"><span data-stu-id="45963-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

