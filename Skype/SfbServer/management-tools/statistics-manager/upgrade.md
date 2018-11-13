---
title: Actualizar el Administrador de estadísticas de Skype para Business Server
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
description: 'Resumen: Lea este tema para obtener información sobre cómo actualizar las estadísticas de administrador de Skype para Business Server.'
ms.openlocfilehash: 3e63210d75b7fa89bb125e990eb1cbc7c37427d4
ms.sourcegitcommit: 8536a34cb13d40b30f84d95e6df10542ef85c36d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26292993"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="29e31-103">Actualizar el Administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="29e31-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="29e31-104">**Resumen:** Lea este tema para obtener información sobre cómo actualizar las estadísticas de administrador de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="29e31-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="29e31-105">En este tema se describe cómo actualizar una instalación existente de administrador de estadísticas de Skype para Business Server — una eficaz herramienta que le permite ver Skype para los datos de estado y rendimiento de servidor empresarial en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="29e31-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="29e31-106">Puede sondear los datos de rendimiento a través de cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio Web de estadísticas de administrador.</span><span class="sxs-lookup"><span data-stu-id="29e31-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="29e31-107">Para obtener más información acerca de las estadísticas de administrador y las nuevas características de la versión 2.0, vea [planear para el Administrador de estadísticas de Skype para Business Server](plan.md) e [Implementar el Administrador de estadísticas de Skype para Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="29e31-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="29e31-108">Existen dos métodos para actualizar:</span><span class="sxs-lookup"><span data-stu-id="29e31-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="29e31-109">**Actualización automática**.</span><span class="sxs-lookup"><span data-stu-id="29e31-109">**Automated upgrade.**</span></span> <span data-ttu-id="29e31-110">Este método usa una secuencia de comandos automatizada.</span><span class="sxs-lookup"><span data-stu-id="29e31-110">This method uses an automated script.</span></span> <span data-ttu-id="29e31-111">Es el método más sencillo y deberán ser aplicable a todos los escenarios de actualización.</span><span class="sxs-lookup"><span data-stu-id="29e31-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="29e31-112">**Actualización manual**.</span><span class="sxs-lookup"><span data-stu-id="29e31-112">**Manual upgrade.**</span></span> <span data-ttu-id="29e31-113">Este método se proporciona como un plan de copia de seguridad en el caso poco habitual que se produce un error en la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="29e31-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="29e31-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="29e31-114">Prerequisites</span></span>

<span data-ttu-id="29e31-115">Antes de realizar la actualización, asegúrese de que tiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="29e31-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="29e31-116">Huella digital del certificado del agente de escucha activa</span><span class="sxs-lookup"><span data-stu-id="29e31-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="29e31-117">Contraseña del servicio de escucha (introducida en la instalación de la escucha y de cada agente)</span><span class="sxs-lookup"><span data-stu-id="29e31-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="29e31-118">Configuración del certificado SSL para el sitio web</span><span class="sxs-lookup"><span data-stu-id="29e31-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="29e31-119">Actualización automática</span><span class="sxs-lookup"><span data-stu-id="29e31-119">Automated upgrade</span></span>

<span data-ttu-id="29e31-120">El script recopilará la información del certificado actual y la contraseña de escucha, desinstalará la versión anterior del producto y, a continuación, instalará la nueva versión del producto.</span><span class="sxs-lookup"><span data-stu-id="29e31-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="29e31-121">La instancia Redis instalada en el servidor no se tocará, de modo que los datos almacenados en la caché se conservarán durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="29e31-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="29e31-122">Coloque los archivos MSI para la nueva versión del agente, el agente de escucha y sitio Web junto con la secuencia de comandos de actualización StatsMan.ps1 en una sola carpeta en el equipo de agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="29e31-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="29e31-123">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29e31-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="29e31-124">Actualice el componente de escucha:</span><span class="sxs-lookup"><span data-stu-id="29e31-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="29e31-125">La contraseña del servicio Administrador de estadísticas se mostrará en texto no cifrado en la línea de comandos tal como se pasa para el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="29e31-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="29e31-126">Asegúrese de blindar el monitor según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="29e31-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="29e31-127">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="29e31-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="29e31-128">Responda Sí.</span><span class="sxs-lookup"><span data-stu-id="29e31-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="29e31-129">Si el servicio de escucha se está ejecutando, se le pedirá que cierre la aplicación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="29e31-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="29e31-130">Permitir que la aplicación se cierre (la escucha de las estadísticas de administrador se detendrá el servicio).</span><span class="sxs-lookup"><span data-stu-id="29e31-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="29e31-131">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="29e31-131">Continue the install process.</span></span> <span data-ttu-id="29e31-132">Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="29e31-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="29e31-133">Si no es así, agregue los valores que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="29e31-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="29e31-134">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29e31-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="29e31-135">Actualice el componente del sitio web:</span><span class="sxs-lookup"><span data-stu-id="29e31-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="29e31-136">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="29e31-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="29e31-137">Responda Sí.</span><span class="sxs-lookup"><span data-stu-id="29e31-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="29e31-138">Si el servicio de agente se está ejecutando, se le pedirá que cierre la aplicación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="29e31-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="29e31-139">Permita el cierre de la aplicación (el servicio de agente StatsMan se detendrá).</span><span class="sxs-lookup"><span data-stu-id="29e31-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="29e31-140">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="29e31-140">Continue the install process.</span></span> <span data-ttu-id="29e31-141">Verá que la contraseña de servicio y la huella digital del certificado se han rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="29e31-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="29e31-142">Si no es así, agregue los valores que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="29e31-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="29e31-143">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29e31-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="29e31-144">Actualice el componente de agente:</span><span class="sxs-lookup"><span data-stu-id="29e31-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="29e31-145">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="29e31-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="29e31-146">Responda Sí.</span><span class="sxs-lookup"><span data-stu-id="29e31-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="29e31-147">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="29e31-147">Continue the install process.</span></span> <span data-ttu-id="29e31-148">Verá que el puerto del sitio web se ha rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="29e31-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="29e31-149">Si no es así, agregue el valor que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="29e31-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="29e31-150">Compruebe que el sitio web funciona como se espera mediante el explorador.</span><span class="sxs-lookup"><span data-stu-id="29e31-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="29e31-151">La actualización del agente se puede usar con el conmutador -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="29e31-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="29e31-152">Esto permitirá que el proceso de instalación/desinstalación se ejecute en silencio, lo que permite que herramientas como PSExec ejecuten la actualización de forma remota en un gran número de servidores.</span><span class="sxs-lookup"><span data-stu-id="29e31-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="29e31-153">Actualización manual</span><span class="sxs-lookup"><span data-stu-id="29e31-153">Manual upgrade</span></span>

<span data-ttu-id="29e31-154">Si, por algún motivo, se produce un error durante la actualización automática, puede realizar una actualización manual siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="29e31-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="29e31-155">	En el equipo de escucha, desinstale la escucha, el sitio web y el agente (si se instaló en este servidor) mediante el panel de control Programas y características.  </span><span class="sxs-lookup"><span data-stu-id="29e31-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="29e31-156"> Mantenga Redis instalado para que los datos de la caché se conserven durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="29e31-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="29e31-p118">	Instale las nuevas versiones de los componentes, incluidos los valores que guardó anteriormente cuando se le pidan. Para obtener más información acerca de cómo instalar los componentes, vea [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="29e31-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="29e31-159">Para más información</span><span class="sxs-lookup"><span data-stu-id="29e31-159">For more information</span></span>
<span data-ttu-id="29e31-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="29e31-160"></span></span>

<span data-ttu-id="29e31-161">Para obtener más información, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="29e31-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="29e31-162">Plan para el Administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="29e31-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="29e31-163">Implementar el Administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="29e31-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="29e31-164">Solucionar problemas de administrador de estadísticas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="29e31-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="29e31-165">Blog del administrador de estadísticas de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="29e31-165">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)
    

