---
title: Actualizar el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Resumen: lea este tema para obtener información sobre cómo actualizar el Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821770"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="e6c72-103">Actualizar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e6c72-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="e6c72-104">**Resumen:** Lea este tema para obtener información sobre cómo actualizar el Administrador de estadísticas para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6c72-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="e6c72-105">En este tema se describe cómo actualizar una instalación existente del Administrador de estadísticas para Skype Empresarial Server, una herramienta eficaz que le permite ver datos de rendimiento y estado de Skype Empresarial Server en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="e6c72-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="e6c72-106">Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="e6c72-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="e6c72-107">Para obtener más información sobre el Administrador de estadísticas y las nuevas características de la versión 2.0, vea [Plan for Statistics Manager for Skype for Business Server](plan.md) and Deploy [Statistics Manager for Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="e6c72-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="e6c72-108">Existen dos métodos para actualizar:</span><span class="sxs-lookup"><span data-stu-id="e6c72-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="e6c72-109">**Actualización automatizada.**</span><span class="sxs-lookup"><span data-stu-id="e6c72-109">**Automated upgrade.**</span></span> <span data-ttu-id="e6c72-110">Este método usa un script automatizado.</span><span class="sxs-lookup"><span data-stu-id="e6c72-110">This method uses an automated script.</span></span> <span data-ttu-id="e6c72-111">Es el método más sencillo y debe aplicarse a todos los escenarios de actualización.</span><span class="sxs-lookup"><span data-stu-id="e6c72-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="e6c72-112">**Actualización manual.**</span><span class="sxs-lookup"><span data-stu-id="e6c72-112">**Manual upgrade.**</span></span> <span data-ttu-id="e6c72-113">Este método se proporciona como un plan de copia de seguridad en el caso inusual de que se produce un error en la actualización automatizada.</span><span class="sxs-lookup"><span data-stu-id="e6c72-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="e6c72-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e6c72-114">Prerequisites</span></span>

<span data-ttu-id="e6c72-115">Antes de actualizar, asegúrese de que tiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e6c72-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="e6c72-116">Huella digital del certificado de escucha activa</span><span class="sxs-lookup"><span data-stu-id="e6c72-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="e6c72-117">Contraseña del servicio de escucha (especificada al instalar el agente de escucha y todos los agentes)</span><span class="sxs-lookup"><span data-stu-id="e6c72-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="e6c72-118">Configuración del certificado SSL para el sitio web</span><span class="sxs-lookup"><span data-stu-id="e6c72-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="e6c72-119">Actualización automatizada</span><span class="sxs-lookup"><span data-stu-id="e6c72-119">Automated upgrade</span></span>

<span data-ttu-id="e6c72-120">El script recopilará la información del certificado actual y la contraseña de escucha, desinstalará la versión anterior del producto y, a continuación, instalará la nueva versión del producto.</span><span class="sxs-lookup"><span data-stu-id="e6c72-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="e6c72-121">La instancia redis instalada en el servidor no se tocará, por lo que los datos almacenados en la memoria caché se conservarán durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="e6c72-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="e6c72-122">Coloque los archivos MSI para la nueva versión del agente, el agente de escucha y el sitio web junto con el script Update-StatsMan.ps1 en una sola carpeta en el equipo de escucha.</span><span class="sxs-lookup"><span data-stu-id="e6c72-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="e6c72-123">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6c72-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="e6c72-124">Actualice el componente de escucha:</span><span class="sxs-lookup"><span data-stu-id="e6c72-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="e6c72-125">La contraseña del servicio administrador de estadísticas se mostrará en texto no especificado en la línea de comandos mientras se pasa al instalador.</span><span class="sxs-lookup"><span data-stu-id="e6c72-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="e6c72-126">Asegúrate de blindar el monitor según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e6c72-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="e6c72-127">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="e6c72-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="e6c72-128">Respuesta Sí.</span><span class="sxs-lookup"><span data-stu-id="e6c72-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="e6c72-129">Si el servicio de escucha se está ejecutando, se le pedirá que cierre la aplicación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6c72-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="e6c72-130">Permitir que se cierre la aplicación (se detendrán el servicio de escucha del Administrador de estadísticas).</span><span class="sxs-lookup"><span data-stu-id="e6c72-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="e6c72-131">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="e6c72-131">Continue the install process.</span></span> <span data-ttu-id="e6c72-132">Debe observar que la contraseña de servicio y la huella digital del certificado están rellenadas previamente.</span><span class="sxs-lookup"><span data-stu-id="e6c72-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="e6c72-133">Si no es así, agregue los valores que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6c72-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="e6c72-134">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6c72-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="e6c72-135">Actualice el componente de sitio web:</span><span class="sxs-lookup"><span data-stu-id="e6c72-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="e6c72-136">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="e6c72-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="e6c72-137">Respuesta Sí.</span><span class="sxs-lookup"><span data-stu-id="e6c72-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="e6c72-138">Si el servicio de agente se está ejecutando, se le pedirá que cierre la aplicación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6c72-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="e6c72-139">Permitir que se cierre la aplicación (se detendrán el servicio de agente StatsMan).</span><span class="sxs-lookup"><span data-stu-id="e6c72-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="e6c72-140">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="e6c72-140">Continue the install process.</span></span> <span data-ttu-id="e6c72-141">Debe observar que la contraseña de servicio y la huella digital del certificado están rellenadas previamente.</span><span class="sxs-lookup"><span data-stu-id="e6c72-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="e6c72-142">Si no es así, agregue los valores que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6c72-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="e6c72-143">Abra una ventana administrativa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6c72-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="e6c72-144">Actualice el componente de agente:</span><span class="sxs-lookup"><span data-stu-id="e6c72-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="e6c72-145">Al ejecutar el script, se le pedirá que desinstale la versión anterior del producto.</span><span class="sxs-lookup"><span data-stu-id="e6c72-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="e6c72-146">Respuesta Sí.</span><span class="sxs-lookup"><span data-stu-id="e6c72-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="e6c72-147">Continúe el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="e6c72-147">Continue the install process.</span></span> <span data-ttu-id="e6c72-148">Debe observar que el puerto del sitio web está rellenado previamente.</span><span class="sxs-lookup"><span data-stu-id="e6c72-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="e6c72-149">Si no es así, agregue el valor que guardó antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6c72-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="e6c72-150">Compruebe que el sitio web funciona según lo esperado con el explorador.</span><span class="sxs-lookup"><span data-stu-id="e6c72-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e6c72-151">La actualización del agente se puede usar con el modificador -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="e6c72-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="e6c72-152">Esto permitirá que el proceso de desinstalación/instalación se ejecute en modo silencioso, lo que permite que herramientas como PSExec ejecuten la actualización de forma remota en un gran número de servidores.</span><span class="sxs-lookup"><span data-stu-id="e6c72-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="e6c72-153">Actualización manual</span><span class="sxs-lookup"><span data-stu-id="e6c72-153">Manual upgrade</span></span>

<span data-ttu-id="e6c72-154">Si, por algún motivo, se produce un error en la actualización automatizada, siempre puede realizar una actualización manual de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e6c72-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="e6c72-155">En el equipo de escucha, desinstale el agente de escucha, el sitio web y el agente (si se instaló en este servidor) a través del panel de control Programas y características.</span><span class="sxs-lookup"><span data-stu-id="e6c72-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="e6c72-156">Mantenga Redis instalado para que los datos de la memoria caché se mantengan a lo largo del proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="e6c72-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="e6c72-157">Instale las nuevas versiones de los componentes, incluidos los valores que guardó anteriormente cuando se le soliciten.</span><span class="sxs-lookup"><span data-stu-id="e6c72-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="e6c72-158">Para obtener más información acerca de la instalación de componentes, vea [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="e6c72-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="e6c72-159">Más información</span><span class="sxs-lookup"><span data-stu-id="e6c72-159">For more information</span></span>
<span data-ttu-id="e6c72-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="e6c72-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="e6c72-161">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="e6c72-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="e6c72-162">Planear el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e6c72-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="e6c72-163">Implementar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e6c72-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="e6c72-164">Solucionar problemas del administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e6c72-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
