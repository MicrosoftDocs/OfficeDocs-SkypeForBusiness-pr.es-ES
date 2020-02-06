---
title: Implementar el administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Resumen: lea este tema para obtener información sobre cómo implementar el administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: 44aad14970716f00550255855d251919a767a268
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803970"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="83dfd-103">Implementar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="83dfd-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="83dfd-104">**Resumen**: lea este tema para obtener información sobre cómo implementar el administrador de estadísticas para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="83dfd-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="83dfd-105">El administrador de estadísticas de Skype Empresarial Server es una eficaz herramienta que le permite ver los datos de mantenimiento y rendimiento de Skype Empresarial Server en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="83dfd-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="83dfd-106">Puede sondear los datos de rendimiento en cientos de servidores cada pocos segundos y ver los resultados al instante en el sitio web del administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="83dfd-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="83dfd-107">Antes de instalar el administrador de estadísticas, consulte los requisitos de software, red y hardware.</span><span class="sxs-lookup"><span data-stu-id="83dfd-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="83dfd-108">Para obtener más información, vea [Planear el administrador de estadísticas para Skype Empresarial Server](plan.md).</span><span class="sxs-lookup"><span data-stu-id="83dfd-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="83dfd-109">Si está llevando a cabo una actualización a partir de una versión anterior del administrador de estadísticas, consulte [Actualizar el administrador de estadísticas para Skype Empresarial Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="83dfd-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="83dfd-110">El sitio web del administrador de estadísticas se ha probado y funciona correctamente en Internet Explorer 11+, Microsoft Edge 20.10240+ y Chrome 46+ (versión actual con actualización automática).</span><span class="sxs-lookup"><span data-stu-id="83dfd-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="83dfd-111">Puede encontrar el archivo descargable del administrador estadísticas en [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span><span class="sxs-lookup"><span data-stu-id="83dfd-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="83dfd-112">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="83dfd-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="83dfd-113">Implementar el administrador de estadísticas</span><span class="sxs-lookup"><span data-stu-id="83dfd-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="83dfd-114">Solucionar problemas de la implementación</span><span class="sxs-lookup"><span data-stu-id="83dfd-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="83dfd-115">Crear un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="83dfd-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="83dfd-116">Implementar el administrador de estadísticas</span><span class="sxs-lookup"><span data-stu-id="83dfd-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="83dfd-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="83dfd-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="83dfd-118">Para implementar el administrador de estadísticas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="83dfd-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="83dfd-119">Prepare el equipo host de escucha instalando el sistema de almacenamiento en caché en memoria Redis y asegurándose de que están instalados los certificados adecuados.</span><span class="sxs-lookup"><span data-stu-id="83dfd-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="83dfd-120">Instale el servicio de escucha en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="83dfd-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="83dfd-121">Instale el servicio de sitio web en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="83dfd-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="83dfd-122">Instale un agente en cada equipo de Skype Empresarial Server que quiera supervisar.</span><span class="sxs-lookup"><span data-stu-id="83dfd-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="83dfd-123">Importe la topología para los servidores que va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="83dfd-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="83dfd-124">Redis, el servicio de escucha y el servicio de sitio web deben estar instalados en el mismo equipo host.</span><span class="sxs-lookup"><span data-stu-id="83dfd-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="83dfd-125">Asegúrese de que Skype Empresarial Server no está instalado en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="83dfd-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="83dfd-126">Preparar el equipo host de escucha</span><span class="sxs-lookup"><span data-stu-id="83dfd-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="83dfd-127">Para preparar el equipo host, debe instalar el sistema de almacenamiento en caché en memoria Redis y asegurarse de que el equipo cuenta con un certificado válido.</span><span class="sxs-lookup"><span data-stu-id="83dfd-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="83dfd-128">Microsoft recomienda instalar la compilación estable más reciente de Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="83dfd-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="83dfd-129">La versión 2.0 del administrador de estadísticas se ha probado con Redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="83dfd-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="83dfd-130">Descargue Redis desde el sitio: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span><span class="sxs-lookup"><span data-stu-id="83dfd-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="83dfd-131">Puede descargar instaladores sin firmar desde [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases).</span><span class="sxs-lookup"><span data-stu-id="83dfd-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="83dfd-132">Si lo necesita, hay binarios firmados disponibles a través de gestores de paquetes populares: [Nuget](https://www.nuget.org/packages/Redis-64/) y [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="83dfd-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="83dfd-133">Ejecute el msi proporcionado y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="83dfd-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="83dfd-134">No marque la casilla para agregar una regla de firewall.</span><span class="sxs-lookup"><span data-stu-id="83dfd-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="83dfd-135">El servicio de escucha requiere un certificado.</span><span class="sxs-lookup"><span data-stu-id="83dfd-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="83dfd-136">Microsoft recomienda encarecidamente usar un certificado firmado por una autoridad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="83dfd-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="83dfd-137">Si desea usar un certificado autofirmado para realizar pruebas en un entorno de laboratorio, por ejemplo, consulte [Crear un certificado autofirmado](deploy.md#BKMK_SelfCert).</span><span class="sxs-lookup"><span data-stu-id="83dfd-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="83dfd-p106">Tenga en cuenta que el agente usa verificación de certificados por huella digital (en lugar de verificación en cadena). No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados.</span><span class="sxs-lookup"><span data-stu-id="83dfd-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="83dfd-140">Instalar el servicio de escucha</span><span class="sxs-lookup"><span data-stu-id="83dfd-140">Install the Listener service</span></span>

<span data-ttu-id="83dfd-141">Para instalar el servicio de escucha en el equipo host, ejecute StatsManPerfAgentListener.msi y especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dfd-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="83dfd-142">Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**. </span><span class="sxs-lookup"><span data-stu-id="83dfd-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="83dfd-143">En la página siguiente, indique la información que se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="83dfd-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="83dfd-144">**Contraseña del servicio:** esta es la contraseña que utilizarán los agentes remotos para autenticarse en el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="83dfd-145">**Puerto de servicio**: este es el número de puerto HTTPS que el servicio de escucha usará para comunicarse con los agentes.</span><span class="sxs-lookup"><span data-stu-id="83dfd-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="83dfd-146">Durante la instalación, este puerto podrá pasar por el firewall local, se creará una ACL de URL y se vinculará un certificado SSL con este puerto.</span><span class="sxs-lookup"><span data-stu-id="83dfd-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="83dfd-147">El valor predeterminado es 8443.</span><span class="sxs-lookup"><span data-stu-id="83dfd-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="83dfd-148">**Huella digital de certificado**: esta es la huella digital de certificado que el servicio de escucha usará para cifrar el protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="83dfd-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="83dfd-149">El servicio de red debe tener acceso de lectura a la clave privada.</span><span class="sxs-lookup"><span data-stu-id="83dfd-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="83dfd-150">Haga clic en el botón **Seleccionar...** para elegir la huella digital.</span><span class="sxs-lookup"><span data-stu-id="83dfd-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="83dfd-151">Puede buscar la huella digital del certificado usando el administrador de certificados o con el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="83dfd-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```PowerShell
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="83dfd-152">**Directorio de instalación**: este es el directorio en el que se instalarán los binarios.</span><span class="sxs-lookup"><span data-stu-id="83dfd-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="83dfd-153">Puede cambiar el valor predeterminado a través del botón **Examinar...**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="83dfd-154">**Directorio de datos de aplicación**: este es el directorio en el que se almacenarán la carpeta de registros y otros datos.</span><span class="sxs-lookup"><span data-stu-id="83dfd-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="83dfd-155">Puede cambiar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="83dfd-155">You may change it from the default.</span></span> <span data-ttu-id="83dfd-156">No se eliminará ni se desinstalará.</span><span class="sxs-lookup"><span data-stu-id="83dfd-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="83dfd-157">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-157">Click **Install**.</span></span>
    
<span data-ttu-id="83dfd-158">Para validar la instalación, realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="83dfd-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="83dfd-159">Abra un explorador y vaya a https://localhost:\<service-port\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="83dfd-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="83dfd-160">De forma predeterminada, el puerto del servicio es 8443 (a no ser que especifique otro).</span><span class="sxs-lookup"><span data-stu-id="83dfd-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="83dfd-161">Para asegurarse de que el servicio de escucha se ha instalado correctamente, busque lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dfd-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="83dfd-162">Si se muestra la página de comprobación de estado, la instalación del servicio de escucha se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="83dfd-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="83dfd-163">Si el KnownServerCount es 1 o superior, se establece la conexión a Redis.</span><span class="sxs-lookup"><span data-stu-id="83dfd-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="83dfd-164">Tras esperar unos minutos y después de instalar al menos un agente, compruebe si crece el valor de ValuesWritten.</span><span class="sxs-lookup"><span data-stu-id="83dfd-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="83dfd-165">Instalar el servicio de sitio web</span><span class="sxs-lookup"><span data-stu-id="83dfd-165">Install the Website</span></span>

<span data-ttu-id="83dfd-166">Para instalar el servicio de sitio web en el equipo host, ejecute StatsManWebSite.msi (incluido en la [versión de 64 bits del administrador de estadísticas en tiempo real de Skype Empresarial Server](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) y especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dfd-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="83dfd-167">Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**. </span><span class="sxs-lookup"><span data-stu-id="83dfd-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="83dfd-168">En la página siguiente, indique la información que se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="83dfd-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="83dfd-169">**Puerto de servicio**: este es el número de puerto que escuchará el sitio web.</span><span class="sxs-lookup"><span data-stu-id="83dfd-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="83dfd-170">Puede cambiarlo posteriormente usando el enlace del administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="83dfd-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="83dfd-171">Durante la instalación, el firewall local permitirá el tráfico por este puerto.</span><span class="sxs-lookup"><span data-stu-id="83dfd-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="83dfd-172">**Directorio de instalación**: este es el directorio en el que se instalarán los binarios.</span><span class="sxs-lookup"><span data-stu-id="83dfd-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="83dfd-173">Puede cambiar el valor predeterminado a través del botón **Examinar...**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="83dfd-174">**Directorio de datos de aplicación**: este es el directorio en el que se almacenarán la carpeta de registros y otros datos.</span><span class="sxs-lookup"><span data-stu-id="83dfd-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="83dfd-175">Puede cambiar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="83dfd-175">You may change it from the default.</span></span> <span data-ttu-id="83dfd-176">No se eliminará ni se desinstalará.</span><span class="sxs-lookup"><span data-stu-id="83dfd-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="83dfd-177">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-177">Click **Install**.</span></span>
    
<span data-ttu-id="83dfd-178">Para ver el sitio web, abra un explorador y vaya a: http://localhost,webport\>/.</span><span class="sxs-lookup"><span data-stu-id="83dfd-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="83dfd-179">Para ver solo información de estado, abra un explorador y vaya a: http://localhost:\<webport\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="83dfd-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="83dfd-180">De forma predeterminada, el número de este puerto es 8080.</span><span class="sxs-lookup"><span data-stu-id="83dfd-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="83dfd-181">Puede cambiar el enlace del puerto del sitio web usando el administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="83dfd-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="83dfd-182">El instalador web agrega un grupo de seguridad local llamado StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="83dfd-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="83dfd-183">Puede agregar cuentas a este grupo de seguridad para concederles acceso al sitio web.</span><span class="sxs-lookup"><span data-stu-id="83dfd-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="83dfd-184">Instalar los agentes</span><span class="sxs-lookup"><span data-stu-id="83dfd-184">Install the Agents</span></span>

<span data-ttu-id="83dfd-185">Debe instalar un agente en cada Skype Empresarial Server que desee supervisar. Para hacerlo, ejecute el archivo StatsManPerfAgent.msi y especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dfd-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="83dfd-186">Revise el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Siguiente**. </span><span class="sxs-lookup"><span data-stu-id="83dfd-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="83dfd-187">En la página siguiente, indique la información que se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="83dfd-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="83dfd-188">**Contraseña del servicio:** esta es la contraseña que utilizará el agente remoto para autenticarse en el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="83dfd-189">**URI de servicio**: este es el URI en el que reside el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="83dfd-190">Debe usar el formato https://name:port.</span><span class="sxs-lookup"><span data-stu-id="83dfd-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="83dfd-191">Puede usar un nombre NETBIOS o un FQDN.</span><span class="sxs-lookup"><span data-stu-id="83dfd-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="83dfd-192">Puede usar el nombre que se especifica también como **Sujeto** o como **Nombres alternativos del sujeto** en el certificado del servicio de escucha, pero no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="83dfd-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="83dfd-193">**Huella digital del servicio**: esta es la huella digital del certificado SSL que usa el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="83dfd-194">El agente usará esta huella digital para autenticarse en el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="83dfd-195">(No realizará la validación de certificados completa, porque es posible utilizar certificados autofirmados).</span><span class="sxs-lookup"><span data-stu-id="83dfd-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="83dfd-196">**Directorio de instalación**: este es el directorio en el que se instalarán los binarios.</span><span class="sxs-lookup"><span data-stu-id="83dfd-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="83dfd-197">Puede cambiar el valor predeterminado a través del botón **Examinar...**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="83dfd-198">**Directorio de datos de aplicación**: este es el directorio en el que se almacenarán la carpeta de registros y el archivo password.txt cifrado.</span><span class="sxs-lookup"><span data-stu-id="83dfd-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="83dfd-199">Puede cambiar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="83dfd-199">You may thanks change it from the default.</span></span> <span data-ttu-id="83dfd-200">No se eliminará ni se desinstalará.</span><span class="sxs-lookup"><span data-stu-id="83dfd-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="83dfd-201">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-201">Click **Install**.</span></span>
    
<span data-ttu-id="83dfd-p121">Si va a instalar un agente en varios equipos, probablemente quiera hacerlo de modo desatendido. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="83dfd-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="83dfd-204">Importar la topología</span><span class="sxs-lookup"><span data-stu-id="83dfd-204">Import the topology</span></span>
<span data-ttu-id="83dfd-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="83dfd-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="83dfd-206">Una vez que el administrador de estadísticas esté instalado y en funcionamiento, debe importar la topología de Skype Empresarial Server para que el administrador de estadísticas conozca el sitio, el grupo y la función de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="83dfd-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="83dfd-207">Para importar su topología de Skype Empresarial Server, use el cmdlet [Get-CSPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) para recuperar información sobre cada grupo que usa su organización e importe esta información al administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="83dfd-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="83dfd-208">Para importar la topología de Skype Empresarial Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="83dfd-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="83dfd-209">En un host que tenga los cmdlets de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="83dfd-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="83dfd-210">a.</span><span class="sxs-lookup"><span data-stu-id="83dfd-210">a.</span></span> <span data-ttu-id="83dfd-211">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="83dfd-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="83dfd-212">b.</span><span class="sxs-lookup"><span data-stu-id="83dfd-212">b.</span></span> <span data-ttu-id="83dfd-213">Copie el archivo "mypoolinfo.xml" en el servidor que ejecuta el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="83dfd-214">En el host que ejecuta el servicio de escucha:</span><span class="sxs-lookup"><span data-stu-id="83dfd-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="83dfd-215">a.</span><span class="sxs-lookup"><span data-stu-id="83dfd-215">a.</span></span> <span data-ttu-id="83dfd-216">Ejecute PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83dfd-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="83dfd-217">b.</span><span class="sxs-lookup"><span data-stu-id="83dfd-217">b.</span></span> <span data-ttu-id="83dfd-218">Vaya hasta el directorio en el que está instalado el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="83dfd-219">El valor predeterminado es:</span><span class="sxs-lookup"><span data-stu-id="83dfd-219">The default is:</span></span> 
    
   ```PowerShell
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="83dfd-220">Para confirmar qué servidores se agregan y se actualizan, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="83dfd-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```PowerShell
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="83dfd-221">El comando siguiente le permite ver todas las opciones:</span><span class="sxs-lookup"><span data-stu-id="83dfd-221">The following command enables you to view all options:</span></span>
  
```PowerShell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="83dfd-222">Para ver la información de servidores que ha importado, ejecute el siguiente script:</span><span class="sxs-lookup"><span data-stu-id="83dfd-222">To see your currently imported server information, run the following script:</span></span> 
  
```PowerShell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="83dfd-223">Si desea supervisar servidores que no se encuentran en su topología de Skype Empresarial Server (un servidor de Exchange, por ejemplo) puede realizar la importación de un único servidor en el host que ejecuta el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="83dfd-224">Para realizar la importación de un único servidor, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="83dfd-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="83dfd-225">Vaya hasta el directorio en el que está instalado el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="83dfd-226">El valor predeterminado es:</span><span class="sxs-lookup"><span data-stu-id="83dfd-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="83dfd-227">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="83dfd-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="83dfd-228">Solucionar problemas de la implementación</span><span class="sxs-lookup"><span data-stu-id="83dfd-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="83dfd-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="83dfd-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="83dfd-230">Si no se puede iniciar un agente, verifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dfd-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="83dfd-231">¿El agente está registrado en el administrador de estadísticas?</span><span class="sxs-lookup"><span data-stu-id="83dfd-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="83dfd-p129">	Asegúrese de que ha seguido las instrucciones para importar la topología. Consulte [Importar la topología](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="83dfd-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="83dfd-234">Si el agente está en un servidor que no se incluye en la topología (por ejemplo, los nodos de un clúster SQL AlwaysOn), tendrá que agregar el agente manualmente siguiendo las instrucciones de [Importar la topología](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="83dfd-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="83dfd-235">¿El agente puede contactar con el servicio de escucha?</span><span class="sxs-lookup"><span data-stu-id="83dfd-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="83dfd-236">Asegúrese de que el servicio de escucha está en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="83dfd-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="83dfd-237">Si no lo está, compruebe que Redis está en funcionamiento y, a continuación, intente reiniciar el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="83dfd-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="83dfd-238">Asegúrese de que el puerto está abierto para el servicio de escucha y de que el equipo del agente se puede comunicar con el puerto.</span><span class="sxs-lookup"><span data-stu-id="83dfd-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="83dfd-239">Para asegurarse de que el administrador de estadísticas recopila datos, puede comprobar el archivo CSV del siguiente modo.</span><span class="sxs-lookup"><span data-stu-id="83dfd-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="83dfd-240">El siguiente comando recupera los nombres de almacenamiento de los contadores:</span><span class="sxs-lookup"><span data-stu-id="83dfd-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="83dfd-241">El siguiente comando recupera los valores de los contadores especificados:</span><span class="sxs-lookup"><span data-stu-id="83dfd-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="83dfd-242">Para obtener información sobre todos los eventos que puede ver en el registro de eventos de la aplicación, consulte [Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="83dfd-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="83dfd-243">Crear un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="83dfd-243">Create a self-signed certificate</span></span>
<span data-ttu-id="83dfd-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="83dfd-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="83dfd-245">Microsoft recomienda encarecidamente usar un certificado firmado por una autoridad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="83dfd-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="83dfd-246">Sin embargo, si desea usar un certificado autofirmado para realizar pruebas, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dfd-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="83dfd-247">Desde una consola de PowerShell en la que haya iniciado sesión como administrador, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83dfd-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```PowerShell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="83dfd-248">Escriba `certlm.msc`.</span><span class="sxs-lookup"><span data-stu-id="83dfd-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="83dfd-249">Se abrirá el administrador de certificados para el equipo local.</span><span class="sxs-lookup"><span data-stu-id="83dfd-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="83dfd-250">Vaya a **Personal** y abra **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="83dfd-251">Haga clic con el botón derecho en **StatsManListener-\>Todas las tareas-\>Administrar claves privadas…**</span><span class="sxs-lookup"><span data-stu-id="83dfd-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="83dfd-252">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="83dfd-253">En el cuadro **Escribir los nombres de objeto para seleccionar**, escriba Servicio de red.</span><span class="sxs-lookup"><span data-stu-id="83dfd-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="83dfd-254">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="83dfd-p132">En **Control total**, desmarque la casilla **Permitir**. (Solo se requiere acceso con permiso de lectura).</span><span class="sxs-lookup"><span data-stu-id="83dfd-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="83dfd-257">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="83dfd-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="83dfd-258">Más información</span><span class="sxs-lookup"><span data-stu-id="83dfd-258">For more information</span></span>
<span data-ttu-id="83dfd-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="83dfd-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="83dfd-260">Para obtener más información, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="83dfd-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="83dfd-261">Planear el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="83dfd-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="83dfd-262">Actualizar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="83dfd-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="83dfd-263">[Solucionar problemas del administrador de estadísticas para Skype Empresarial Server](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="83dfd-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
