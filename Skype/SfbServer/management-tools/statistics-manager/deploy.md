---
title: Implementar el administrador de estadísticas para Skype Empresarial Server
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
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumen: lea este tema para obtener información sobre cómo implementar el Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814820"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="f3325-103">Implementar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f3325-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="f3325-104">**Resumen:** Lea este tema para obtener información sobre cómo implementar el Administrador de estadísticas para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f3325-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="f3325-105">El Administrador de estadísticas de Skype Empresarial Server es una herramienta eficaz que le permite ver datos de rendimiento y estado de Skype Empresarial Server en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="f3325-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="f3325-106">Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="f3325-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="f3325-107">Antes de intentar instalar el Administrador de estadísticas, asegúrese de que está familiarizado con los requisitos de software, redes y hardware.</span><span class="sxs-lookup"><span data-stu-id="f3325-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="f3325-108">Para obtener más información, consulte [Plan for Statistics Manager for Skype for Business Server](plan.md).</span><span class="sxs-lookup"><span data-stu-id="f3325-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3325-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="f3325-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f3325-110">El sitio web del Administrador de estadísticas se ha probado y funciona correctamente en Internet Explorer 11+, Edge 20.10240+ y Chrome 46+ (versión perennicio actual).</span><span class="sxs-lookup"><span data-stu-id="f3325-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="f3325-111">Puede encontrar el Administrador de estadísticas descargable en [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) .</span><span class="sxs-lookup"><span data-stu-id="f3325-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="f3325-112">En este tema se presentan las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="f3325-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="f3325-113">Implementar el Administrador de estadísticas</span><span class="sxs-lookup"><span data-stu-id="f3325-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="f3325-114">Solucionar problemas de implementación</span><span class="sxs-lookup"><span data-stu-id="f3325-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="f3325-115">Crear un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="f3325-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="f3325-116">Implementar el Administrador de estadísticas</span><span class="sxs-lookup"><span data-stu-id="f3325-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="f3325-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="f3325-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="f3325-118">Para implementar el Administrador de estadísticas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f3325-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="f3325-119">Prepare el equipo host de escucha instalando el sistema de almacenamiento en caché en memoria redis y asegurándose de que ha instalado los certificados adecuados.</span><span class="sxs-lookup"><span data-stu-id="f3325-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="f3325-120">Instale el servicio de escucha en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="f3325-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="f3325-121">Instale el sitio web en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="f3325-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="f3325-122">Instale un agente en cada equipo de Skype Empresarial Server que desee supervisar.</span><span class="sxs-lookup"><span data-stu-id="f3325-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="f3325-123">Importe la topología de los servidores que está supervisando.</span><span class="sxs-lookup"><span data-stu-id="f3325-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f3325-124">Redis, el servicio de escucha y el sitio web deben estar instalados en el mismo equipo host.</span><span class="sxs-lookup"><span data-stu-id="f3325-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="f3325-125">Asegúrese de que el equipo host no tenga instalado Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f3325-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="f3325-126">Preparar el equipo host de escucha</span><span class="sxs-lookup"><span data-stu-id="f3325-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="f3325-127">Para preparar el equipo host, deberá instalar el sistema de almacenamiento en caché en memoria redis y asegurarse de que hay un certificado válido en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f3325-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="f3325-128">Microsoft recomienda instalar la compilación estable más reciente de Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="f3325-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="f3325-129">La versión 2.0 del Administrador de estadísticas se probó con Redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="f3325-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="f3325-130">Descargue Redis desde el siguiente sitio: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) .</span><span class="sxs-lookup"><span data-stu-id="f3325-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="f3325-131">Los instaladores sin firma se pueden descargar desde [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="f3325-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="f3325-132">Si es necesario, los archivos binarios firmados están disponibles a través de los administradores de paquetes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) y [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="f3325-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="f3325-133">Ejecute el msi proporcionado y siga las indicaciones.</span><span class="sxs-lookup"><span data-stu-id="f3325-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="f3325-134">No active la casilla para agregar una regla de firewall.</span><span class="sxs-lookup"><span data-stu-id="f3325-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="f3325-135">El servicio de escucha requiere un certificado.</span><span class="sxs-lookup"><span data-stu-id="f3325-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="f3325-136">Microsoft recomienda encarecidamente que tenga un certificado firmado por una entidad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="f3325-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="f3325-137">Si desea usar un certificado autofirmado (por ejemplo, para realizar pruebas en un laboratorio), consulte Crear un [certificado autofirmado.](deploy.md#BKMK_SelfCert)</span><span class="sxs-lookup"><span data-stu-id="f3325-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="f3325-138">Tenga en cuenta que el agente usa la comprobación de huella digital del certificado (en lugar de la verificación en cadena).</span><span class="sxs-lookup"><span data-stu-id="f3325-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="f3325-139">No realizará la validación completa del certificado porque es posible usar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="f3325-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="f3325-140">Instalar el servicio de escucha</span><span class="sxs-lookup"><span data-stu-id="f3325-140">Install the Listener service</span></span>

<span data-ttu-id="f3325-141">Para instalar el servicio de escucha en el equipo host, ejecute el StatsManPerfAgentListener.msi y especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3325-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="f3325-142">Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f3325-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="f3325-143">En la página siguiente, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f3325-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="f3325-144">**Contraseña de servicio:** Esta es la contraseña que usarán los agentes remotos para autenticarse en el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="f3325-145">**Puerto de servicio:** Este es el número de puerto HTTPS que usará el agente de escucha para comunicarse con los agentes.</span><span class="sxs-lookup"><span data-stu-id="f3325-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="f3325-146">Durante la instalación, este puerto se permitirá a través del firewall local, se creará una ACL de dirección URL y se enlazará un certificado SSL a este puerto.</span><span class="sxs-lookup"><span data-stu-id="f3325-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="f3325-147">El valor predeterminado es 8443.</span><span class="sxs-lookup"><span data-stu-id="f3325-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="f3325-148">**Huella digital del certificado:** Esta es la huella digital del certificado que el agente de escucha usará para cifrar el protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f3325-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="f3325-149">El servicio de red debe tener acceso de lectura a la clave privada.</span><span class="sxs-lookup"><span data-stu-id="f3325-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="f3325-150">Haga clic **en el botón Seleccionar...** para elegir la huella digital.</span><span class="sxs-lookup"><span data-stu-id="f3325-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="f3325-151">Puede encontrar la huella digital del certificado mediante el Administrador de certificados o mediante el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f3325-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="f3325-152">**Instalar Dir:** Este es el directorio en el que se instalarán los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="f3325-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="f3325-153">Puede cambiarlo del valor predeterminado mediante el **botón** Examinar....</span><span class="sxs-lookup"><span data-stu-id="f3325-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="f3325-154">**Dir. de AppData:** Este es el directorio donde se almacenarán la carpeta Registros y otros datos.</span><span class="sxs-lookup"><span data-stu-id="f3325-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="f3325-155">Puede cambiarlo del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3325-155">You may change it from the default.</span></span> <span data-ttu-id="f3325-156">No se eliminará al desinstalar.</span><span class="sxs-lookup"><span data-stu-id="f3325-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="f3325-157">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f3325-157">Click **Install**.</span></span>
    
<span data-ttu-id="f3325-158">Para validar la instalación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f3325-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="f3325-159">Abra un explorador y vaya a https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="f3325-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="f3325-160">De forma predeterminada, el puerto de servicio es 8443 (a menos que haya especificado otro puerto).</span><span class="sxs-lookup"><span data-stu-id="f3325-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="f3325-161">Para asegurarse de que el agente de escucha se ha instalado correctamente, busque lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3325-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="f3325-162">Si aparece la página de comprobación de estado, la instalación de la escucha se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3325-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="f3325-163">Si el valor de KnownServerCount es 1 o superior, se establece la conexión a Redis.</span><span class="sxs-lookup"><span data-stu-id="f3325-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="f3325-164">Después de esperar unos minutos y después de instalar al menos un agente, compruebe que el contador ValuesWritten está en incremento.</span><span class="sxs-lookup"><span data-stu-id="f3325-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="f3325-165">Instalar el sitio web</span><span class="sxs-lookup"><span data-stu-id="f3325-165">Install the Website</span></span>

<span data-ttu-id="f3325-166">Instale el sitio web en el equipo host ejecutando el StatsManWebSite.msi (incluido con Skype Empresarial [Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)y especificando lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3325-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="f3325-167">Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f3325-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="f3325-168">En la página siguiente, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f3325-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="f3325-169">**Puerto de servicio:** Este es el número de puerto en el que escuchará el sitio web.</span><span class="sxs-lookup"><span data-stu-id="f3325-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="f3325-170">Puede cambiarlo más adelante mediante el enlace del administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="f3325-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="f3325-171">Durante la instalación, este puerto se permitirá a través del firewall local.</span><span class="sxs-lookup"><span data-stu-id="f3325-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="f3325-172">**Instalar Dir:** Este es el directorio donde se instalarán los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="f3325-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="f3325-173">Puede cambiarlo del valor predeterminado mediante el **botón** Examinar....</span><span class="sxs-lookup"><span data-stu-id="f3325-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="f3325-174">**Dir. de AppData:** Este es el directorio donde se almacenarán la carpeta Registros y otros datos.</span><span class="sxs-lookup"><span data-stu-id="f3325-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="f3325-175">Puede cambiarlo del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3325-175">You may change it from the default.</span></span> <span data-ttu-id="f3325-176">No se eliminará al desinstalar.</span><span class="sxs-lookup"><span data-stu-id="f3325-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="f3325-177">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f3325-177">Click **Install**.</span></span>
    
<span data-ttu-id="f3325-178">Para ver el sitio web, abra un explorador y vaya a: http://localhost ,webport \> /.</span><span class="sxs-lookup"><span data-stu-id="f3325-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="f3325-179">Para ver solo la información de estado, abra un explorador y vaya a: http://localhost: \<webport\> /healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="f3325-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="f3325-180">De forma predeterminada, el número de puerto web es 8080.</span><span class="sxs-lookup"><span data-stu-id="f3325-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="f3325-181">Puede cambiar el enlace de puerto del sitio web mediante el administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="f3325-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="f3325-182">El instalador web agrega un grupo de seguridad local, denominado StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="f3325-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="f3325-183">Puede agregar cuentas a este grupo de seguridad para conceder acceso al sitio web.</span><span class="sxs-lookup"><span data-stu-id="f3325-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="f3325-184">Instalar los agentes</span><span class="sxs-lookup"><span data-stu-id="f3325-184">Install the Agents</span></span>

<span data-ttu-id="f3325-185">Instale un agente en cada Skype Empresarial Server que desee supervisar ejecutando el StatsManPerfAgent.msi y especificando lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3325-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="f3325-186">Revise el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y, a continuación, haga clic en **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f3325-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="f3325-187">En la página siguiente, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f3325-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="f3325-188">**Contraseña de servicio:** Esta es la contraseña que usará el agente remoto para autenticarse en el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="f3325-189">**URI de servicio:** Este es el URI donde reside el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="f3325-190">Debe usar el https://name:port formato.</span><span class="sxs-lookup"><span data-stu-id="f3325-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="f3325-191">Puede usar un nombre NETBIOS o un FQDN.</span><span class="sxs-lookup"><span data-stu-id="f3325-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="f3325-192">Puede usar el nombre que también  se  especifica como el asunto o nombres alternativos de sujeto del certificado en el servicio de escucha, pero no es un requisito.</span><span class="sxs-lookup"><span data-stu-id="f3325-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="f3325-193">**Huella digital del servicio:** Esta es la huella digital del certificado SSL que está usando el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="f3325-194">El agente usará esta huella digital para autenticarse en el agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="f3325-195">(No realizará la validación completa del certificado porque es posible usar certificados autofirmados).</span><span class="sxs-lookup"><span data-stu-id="f3325-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="f3325-196">**Instalar Dir:** Este es el directorio en el que se instalarán los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="f3325-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="f3325-197">Puede cambiarlo del valor predeterminado mediante el **botón** Examinar....</span><span class="sxs-lookup"><span data-stu-id="f3325-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="f3325-198">**Dir. de AppData:** Este es el directorio donde se almacenarán la carpeta Logs y password.txt cifrado.</span><span class="sxs-lookup"><span data-stu-id="f3325-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="f3325-199">Puede cambiarlo del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3325-199">You may thanks change it from the default.</span></span> <span data-ttu-id="f3325-200">No se eliminará al desinstalar.</span><span class="sxs-lookup"><span data-stu-id="f3325-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="f3325-201">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f3325-201">Click **Install**.</span></span>
    
<span data-ttu-id="f3325-202">Si vas a instalar un agente en numerosas máquinas, probablemente quieras hacerlo en modo desatendido.</span><span class="sxs-lookup"><span data-stu-id="f3325-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="f3325-203">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f3325-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="f3325-204">Importar la topología</span><span class="sxs-lookup"><span data-stu-id="f3325-204">Import the topology</span></span>
<span data-ttu-id="f3325-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="f3325-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="f3325-206">Después de instalar y ejecutar el Administrador de estadísticas, debe importar la topología de Skype Empresarial Server para que el Administrador de estadísticas conozca el sitio, el grupo y el rol de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="f3325-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="f3325-207">Para importar la topología de Skype Empresarial Server, usará el cmdlet [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) para recuperar información sobre cada grupo de servidores en uso en su organización y, a continuación, importar esta información al Administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="f3325-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="f3325-208">Para importar la topología de Skype Empresarial Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f3325-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="f3325-209">En un host que tiene los cmdlets de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="f3325-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="f3325-210">a.</span><span class="sxs-lookup"><span data-stu-id="f3325-210">a.</span></span> <span data-ttu-id="f3325-211">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f3325-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="f3325-212">b.</span><span class="sxs-lookup"><span data-stu-id="f3325-212">b.</span></span> <span data-ttu-id="f3325-213">Copie el archivo "mypoolinfo.xml" en el servidor que ejecuta el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="f3325-214">En el host que ejecuta la escucha:</span><span class="sxs-lookup"><span data-stu-id="f3325-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="f3325-215">a.</span><span class="sxs-lookup"><span data-stu-id="f3325-215">a.</span></span> <span data-ttu-id="f3325-216">Ejecute PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3325-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="f3325-217">b.</span><span class="sxs-lookup"><span data-stu-id="f3325-217">b.</span></span> <span data-ttu-id="f3325-218">Navegue hasta el directorio en el que está instalado el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="f3325-219">El valor predeterminado es:</span><span class="sxs-lookup"><span data-stu-id="f3325-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="f3325-220">Para confirmar qué servidores se van a agregar y actualizar, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f3325-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="f3325-221">El siguiente comando le permite ver todas las opciones:</span><span class="sxs-lookup"><span data-stu-id="f3325-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="f3325-222">Para ver la información del servidor importado actualmente, ejecute el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="f3325-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="f3325-223">Si desea supervisar los servidores que no están en la topología de Skype Empresarial Server (un Exchange Server, por ejemplo), puede realizar una importación de un solo servidor en el host que ejecuta la escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="f3325-224">Para realizar una importación de servidor único, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f3325-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="f3325-225">Navegue hasta el directorio en el que está instalado el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="f3325-226">El valor predeterminado es:</span><span class="sxs-lookup"><span data-stu-id="f3325-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="f3325-227">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f3325-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="f3325-228">Solucionar problemas de implementación</span><span class="sxs-lookup"><span data-stu-id="f3325-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="f3325-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="f3325-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="f3325-230">Si no se puede iniciar un agente, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3325-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="f3325-231">¿El agente está registrado en el Administrador de estadísticas?</span><span class="sxs-lookup"><span data-stu-id="f3325-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="f3325-232">Asegúrese de que ha seguido las instrucciones para importar la topología.</span><span class="sxs-lookup"><span data-stu-id="f3325-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="f3325-233">Consulte [Importar la topología.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="f3325-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="f3325-234">Si el agente está en un servidor que no aparece en la topología (por ejemplo, los nodos de un clúster alwayson de SQL), deberá agregar el agente manualmente siguiendo las instrucciones de Importación de la [topología.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="f3325-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="f3325-235">¿Puede el agente ponerse en contacto con el agente de escucha?</span><span class="sxs-lookup"><span data-stu-id="f3325-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="f3325-236">Asegúrese de que el servicio de escucha se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f3325-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="f3325-237">Si no se está ejecutando, asegúrese de que Redis se está ejecutando y, a continuación, intente reiniciar la escucha.</span><span class="sxs-lookup"><span data-stu-id="f3325-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="f3325-238">Asegúrese de que el puerto está abierto para el servicio de escucha y de que el equipo del agente puede comunicarse con el puerto.</span><span class="sxs-lookup"><span data-stu-id="f3325-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="f3325-239">Para asegurarse de que el Administrador de estadísticas recopila datos, puede comprobar el archivo CSV de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="f3325-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="f3325-240">El siguiente comando recupera los nombres de almacenamiento de contador:</span><span class="sxs-lookup"><span data-stu-id="f3325-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="f3325-241">El siguiente comando recupera los valores de los contadores especificados:</span><span class="sxs-lookup"><span data-stu-id="f3325-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="f3325-242">Para obtener información sobre todos los eventos que puede ver en el registro de eventos de la aplicación, consulte Solucionar problemas del administrador de [estadísticas para Skype Empresarial Server.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="f3325-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="f3325-243">Crear un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="f3325-243">Create a self-signed certificate</span></span>
<span data-ttu-id="f3325-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="f3325-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="f3325-245">Microsoft recomienda encarecidamente usar un certificado firmado por una entidad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="f3325-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="f3325-246">Sin embargo, si desea usar un certificado autofirmado con fines de prueba, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3325-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="f3325-247">Desde una consola de PowerShell mientras ha iniciado sesión como administrador, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3325-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="f3325-248">Escriba  `certlm.msc` .</span><span class="sxs-lookup"><span data-stu-id="f3325-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="f3325-249">Se abrirá el Administrador de certificados para el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f3325-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="f3325-250">Vaya a **Personal** y, a continuación, **abra Certificados.**</span><span class="sxs-lookup"><span data-stu-id="f3325-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="f3325-251">Haga clic con el **botón secundario en StatsManListener: \> Todas las tareas: Administrar claves \> privadas...**</span><span class="sxs-lookup"><span data-stu-id="f3325-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="f3325-252">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f3325-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="f3325-253">En el **cuadro Escribir los nombres de objeto que desea seleccionar,** escriba lo siguiente: Servicio de red</span><span class="sxs-lookup"><span data-stu-id="f3325-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="f3325-254">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3325-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="f3325-255">En **Control total,** des marque la **casilla** Permitir.</span><span class="sxs-lookup"><span data-stu-id="f3325-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="f3325-256">(Solo se necesita acceso de lectura).</span><span class="sxs-lookup"><span data-stu-id="f3325-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="f3325-257">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3325-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="f3325-258">Más información</span><span class="sxs-lookup"><span data-stu-id="f3325-258">For more information</span></span>
<span data-ttu-id="f3325-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="f3325-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="f3325-260">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="f3325-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="f3325-261">Planear el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f3325-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="f3325-262">Actualizar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f3325-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="f3325-263">[Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md) ß</span><span class="sxs-lookup"><span data-stu-id="f3325-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
