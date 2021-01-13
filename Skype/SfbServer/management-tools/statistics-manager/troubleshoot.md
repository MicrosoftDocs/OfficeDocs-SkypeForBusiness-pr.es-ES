---
title: Solucionar problemas del administrador de estadísticas para Skype Empresarial Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumen: lea este tema para solucionar problemas de implementación del Administrador de estadísticas para Skype Empresarial Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821780"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="4951b-103">Solucionar problemas del administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4951b-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="4951b-104">**Resumen:** Lea este tema para solucionar problemas de implementación del Administrador de estadísticas para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4951b-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="4951b-105">En este tema se describe cómo solucionar problemas de la implementación del Administrador de estadísticas mediante la descripción de los eventos que puede ver en el registro de eventos de la aplicación y las acciones apropiadas que puede realizar para corregir el evento.</span><span class="sxs-lookup"><span data-stu-id="4951b-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="4951b-106">En este tema se presentan las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="4951b-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="4951b-107">Eventos de agente</span><span class="sxs-lookup"><span data-stu-id="4951b-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="4951b-108">Eventos de escucha</span><span class="sxs-lookup"><span data-stu-id="4951b-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="4951b-109">Problemas del sitio web</span><span class="sxs-lookup"><span data-stu-id="4951b-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="4951b-110">Eventos de agente</span><span class="sxs-lookup"><span data-stu-id="4951b-110">Agent events</span></span>
<span data-ttu-id="4951b-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="4951b-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="4951b-112">**1000** — No se puede configurar el limitador de procesador (objeto job): motivo desconocido</span><span class="sxs-lookup"><span data-stu-id="4951b-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="4951b-113">**1001—** No se permite la limitación de procesos en el proceso (probablemente ya dentro de un objeto Job)</span><span class="sxs-lookup"><span data-stu-id="4951b-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="4951b-114">El agente se ejecuta dentro de un objeto de trabajo de Windows para limitar automáticamente su superficie de memoria.</span><span class="sxs-lookup"><span data-stu-id="4951b-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="4951b-115">Si el agente no se iniciará y estas entradas de evento están presentes en el registro de eventos, no se podrá crear una instancia del objeto job en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4951b-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="4951b-116">Para evitar esto, se puede quitar el límite de memoria superior cambiando un valor en el archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="4951b-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="4951b-117">Busque "MaxProcessMemoryMB" y cambie el valor a "0", como se muestra:</span><span class="sxs-lookup"><span data-stu-id="4951b-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="4951b-118">Si se realiza este cambio, el agente generalmente seguirá consumiendo 100 MB de memoria, pero no se limitará a la fuerza a 300 MB como es el valor \< predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4951b-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="4951b-119">Si se realiza este cambio, se recomienda supervisar estrechamente el uso de memoria para asegurarse de que el agente no consume una gran cantidad de memoria en su equipo host.</span><span class="sxs-lookup"><span data-stu-id="4951b-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="4951b-120">**2000:** Error de inicialización del cliente</span><span class="sxs-lookup"><span data-stu-id="4951b-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="4951b-121">**2001:** No se pudo realizar ninguna conexión con el servicio en ninguna IP de origen</span><span class="sxs-lookup"><span data-stu-id="4951b-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="4951b-122">Si el agente no puede conectarse al equipo de escucha, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4951b-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="4951b-123">Asegúrese de que el servicio de escucha se está ejecutando en el equipo de escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="4951b-124">Si no es así, asegúrese de que Redis se ejecuta en ese servidor y, a continuación, reinicie el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="4951b-125">Compruebe el registro de eventos del Administrador de estadísticas en el equipo de escucha para asegurarse de que no hay problemas con el servicio de escucha del administrador de estadísticas en sí.</span><span class="sxs-lookup"><span data-stu-id="4951b-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="4951b-126">Use una herramienta de conectividad como telnet para comprobar la conectividad desde el equipo del agente al servicio de escucha en el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="4951b-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="4951b-127">Si no es así, asegúrese de que la regla de firewall entrante está habilitada en el equipo de escucha para el tipo de red al que está conectado el equipo de escucha (privado/público/dominio).</span><span class="sxs-lookup"><span data-stu-id="4951b-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="4951b-128">Si el equipo de escucha no está unido a un dominio, es posible que la red aparezca como pública y, en ese caso, las reglas de firewall instaladas con el Administrador de estadísticas no se aplicarán de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4951b-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="4951b-129">**4000—** Error al descargar la información del servidor desde la escucha (motivo desconocido)</span><span class="sxs-lookup"><span data-stu-id="4951b-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="4951b-130">**4001:** Servidor no encontrado en la topología de escucha</span><span class="sxs-lookup"><span data-stu-id="4951b-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="4951b-131">Este error se producirá si el servidor se conecta correctamente a la escucha, pero el servidor no se agregó a la topología en la memoria caché del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="4951b-132">Opciones de resolución:</span><span class="sxs-lookup"><span data-stu-id="4951b-132">Resolution options:</span></span>
    
  - <span data-ttu-id="4951b-133">Asegúrese de que ha seguido las instrucciones para importar la topología.</span><span class="sxs-lookup"><span data-stu-id="4951b-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="4951b-134">Consulte [Importar la topología.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="4951b-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="4951b-135">Si el agente está en un servidor que no aparece en la topología (por ejemplo, los nodos de un clúster alwayson de SQL), deberá agregar el agente manualmente siguiendo las instrucciones de Importación de la [topología.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="4951b-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="4951b-136">**4002:** Contraseña de escucha no válida</span><span class="sxs-lookup"><span data-stu-id="4951b-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="4951b-137">La contraseña cifrada que el agente está intentando usar no coincide con la contraseña de servicio en el propio servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="4951b-138">Desinstale el agente y vuelva a instalarlo con la contraseña de servicio correcta.</span><span class="sxs-lookup"><span data-stu-id="4951b-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="4951b-139">**4003:** Error de coincidencia de huella digital de certificado</span><span class="sxs-lookup"><span data-stu-id="4951b-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="4951b-140">La huella digital del certificado que se ha dado al agente en el momento de la instalación no coincide con la huella digital del certificado que está usando actualmente el agente de escucha y, por lo tanto, se rechazará la conexión.</span><span class="sxs-lookup"><span data-stu-id="4951b-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="4951b-141">Desinstale el agente y vuelva a instalarlo con la huella digital del certificado correcta.</span><span class="sxs-lookup"><span data-stu-id="4951b-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="4951b-142">**4004—** Respuesta no válida o HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="4951b-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="4951b-143">El agente de escucha no responde con un estado esperado.</span><span class="sxs-lookup"><span data-stu-id="4951b-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="4951b-144">Si la conexión está en proxy, compruebe la configuración del proxy.</span><span class="sxs-lookup"><span data-stu-id="4951b-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="4951b-145">Compruebe si hay problemas con su configuración en el registro statsMan del equipo de escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="4951b-146">**4005:** No se pudo deserializar el XML</span><span class="sxs-lookup"><span data-stu-id="4951b-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="4951b-147">La información del servidor en el servidor de escucha está dañada o puede haber un error de coincidencia de versiones entre el agente y los equipos de escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="4951b-148">Asegúrese de que las versiones coinciden y compruebe si hay problemas en el registro de eventos de escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="4951b-149">Eventos de escucha</span><span class="sxs-lookup"><span data-stu-id="4951b-149">Listener events</span></span>
<span data-ttu-id="4951b-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="4951b-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="4951b-151">**10000:** error de inicio Motivo desconocido (estos no se pueden recuperar y el servicio se detendrá o bloqueará como resultado)</span><span class="sxs-lookup"><span data-stu-id="4951b-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="4951b-152">**10001:** problema de configuración</span><span class="sxs-lookup"><span data-stu-id="4951b-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="4951b-153">Por lo general, esto ocurrirá cuando el archivo [listener_install_location]\PerfAgentListener.exe.config se haya modificado manualmente y la aplicación no pueda leerlo.</span><span class="sxs-lookup"><span data-stu-id="4951b-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="4951b-154">**10002:** Error de inicialización de la escucha HTTP</span><span class="sxs-lookup"><span data-stu-id="4951b-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="4951b-155">Por lo general, este evento se registrará cuando la ACL de la dirección URL no se haya establecido correctamente durante la instalación o el certificado SSL no sea válido.</span><span class="sxs-lookup"><span data-stu-id="4951b-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="4951b-156">Asegúrese de que el certificado de la configuración sea válido.</span><span class="sxs-lookup"><span data-stu-id="4951b-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="4951b-157">Si es así, vuelva a instalar el agente de escucha de acuerdo con las instrucciones de [Implementar el Administrador de estadísticas.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="4951b-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="4951b-158">**10003:** Error de Redis</span><span class="sxs-lookup"><span data-stu-id="4951b-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="4951b-159">**10004:** error de infraestructura de almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="4951b-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="4951b-160">**10007:** Configuración (almacenada en redis)</span><span class="sxs-lookup"><span data-stu-id="4951b-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="4951b-161">El agente de escucha no pudo ponerse en contacto con Redis ni recuperar datos bien formados de la memoria caché y no pudo iniciarse.</span><span class="sxs-lookup"><span data-stu-id="4951b-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="4951b-162">Asegúrese de que el servicio Redis se ha iniciado y configurado correctamente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4951b-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="4951b-163">**10005:** Recuperación y análisis de información del servidor</span><span class="sxs-lookup"><span data-stu-id="4951b-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="4951b-164">La información de topología de la memoria caché de Redis no es válida.</span><span class="sxs-lookup"><span data-stu-id="4951b-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="4951b-165">En primer lugar, intente reiniciar Redis y la escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="4951b-166">Si el error persiste, consulte [Importar la topología para](deploy.md#BKMK_ImportTopology) volver a crear los datos de la topología.</span><span class="sxs-lookup"><span data-stu-id="4951b-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="4951b-167">**10100:** Interrupción del PING de Redis</span><span class="sxs-lookup"><span data-stu-id="4951b-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="4951b-168">**10101:** Interrupción continuada de PING de Redis (cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="4951b-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="4951b-169">**30100:** Interrupción del PING de Redis restaurada</span><span class="sxs-lookup"><span data-stu-id="4951b-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="4951b-170">Se registrarán cuando el agente de escucha no pueda conectarse a Redis.</span><span class="sxs-lookup"><span data-stu-id="4951b-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="4951b-171">Asegúrese de que Redis se ha iniciado y de que la conectividad de red entre la escucha y Redis está disponible.</span><span class="sxs-lookup"><span data-stu-id="4951b-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="4951b-172">**10200:** Interrupción de escritura de Redis</span><span class="sxs-lookup"><span data-stu-id="4951b-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="4951b-173">**10201:** Interrupción continuada de redis write (cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="4951b-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="4951b-174">**30100:** interrupción de redis write resuelto</span><span class="sxs-lookup"><span data-stu-id="4951b-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="4951b-175">Se registrarán cuando el agente de escucha no pueda escribir en la memoria caché de Redis.</span><span class="sxs-lookup"><span data-stu-id="4951b-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="4951b-176">Asegúrese de que Redis se ha iniciado y de que la conectividad de red entre el servicio de escucha y Redis está disponible.</span><span class="sxs-lookup"><span data-stu-id="4951b-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="4951b-177">**30000:** iniciado correctamente</span><span class="sxs-lookup"><span data-stu-id="4951b-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="4951b-178">Se registra cada vez que se inicia la escucha.</span><span class="sxs-lookup"><span data-stu-id="4951b-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="4951b-179">**22000:** la inicialización del agente del Administrador de estadísticas se ha logrado.</span><span class="sxs-lookup"><span data-stu-id="4951b-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="4951b-180">**23000—** Inicialización de EventLogQueryManager correcta (primera vez o después de un error)</span><span class="sxs-lookup"><span data-stu-id="4951b-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="4951b-181">**24000—** Inicialización de serverinfo correcta (primera vez o después de un error)</span><span class="sxs-lookup"><span data-stu-id="4951b-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="4951b-182">**25000—** La escucha vuelve a estar en línea después de no publicar (o la primera publicación correcta)</span><span class="sxs-lookup"><span data-stu-id="4951b-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="4951b-183">**5000:** Inicio del agente de escucha sin conexión para publicar datos</span><span class="sxs-lookup"><span data-stu-id="4951b-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="4951b-184">**5001:** la escucha sigue sin conexión durante un período prolongado</span><span class="sxs-lookup"><span data-stu-id="4951b-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="4951b-185">Estos eventos pueden ser útiles para supervisar, alertas y borrar problemas.</span><span class="sxs-lookup"><span data-stu-id="4951b-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="4951b-186">Problemas del sitio web</span><span class="sxs-lookup"><span data-stu-id="4951b-186">Website issues</span></span>
<span data-ttu-id="4951b-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="4951b-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="4951b-188">Mensajes de inicio de sesión repetitivos en Chrome: se trata de un error que se ha resuelto en la versión 1.1.</span><span class="sxs-lookup"><span data-stu-id="4951b-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="4951b-189">Asegúrese de que ha actualizado a la versión más reciente del Administrador de estadísticas si ve varias solicitudes de inicio de sesión en el explorador Chrome.</span><span class="sxs-lookup"><span data-stu-id="4951b-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="4951b-190">Para comprobar la versión del sitio web que está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="4951b-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="4951b-191">En el Explorador de archivos, abierto (directorio predeterminado)</span><span class="sxs-lookup"><span data-stu-id="4951b-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="4951b-192">Haga clic con el botón StatsManHubWebSite.dll y vea sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="4951b-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="4951b-193">Si no se encuentra un equipo en la vista horizontal de KHI o en la vista Detalles del contador, asegúrese de que es miembro de un sitio y un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="4951b-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="4951b-194">Si no es así, no aparecerá en esas vistas.</span><span class="sxs-lookup"><span data-stu-id="4951b-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="4951b-195">Para obtener información acerca de cómo definir un sitio y un grupo de servidores para un servidor de la topología, consulte [Importar la topología.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="4951b-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="4951b-196">La versión del producto se mostrará en los detalles de descripción.</span><span class="sxs-lookup"><span data-stu-id="4951b-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="4951b-197">Más información</span><span class="sxs-lookup"><span data-stu-id="4951b-197">For more information</span></span>
<span data-ttu-id="4951b-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="4951b-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="4951b-199">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="4951b-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="4951b-200">Planear el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4951b-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="4951b-201">Implementar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4951b-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="4951b-202">Actualizar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4951b-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
