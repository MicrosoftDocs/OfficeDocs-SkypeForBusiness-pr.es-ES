---
title: Solucionar problemas del administrador de estadísticas para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Resumen: Lea este tema para solucionar problemas de implementación de Statistics Manager para Skype empresarial Server.'
ms.openlocfilehash: b85ee6593413cce0aa5b7c76901dbbc6099107fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299698"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="9d9d0-103">Solucionar problemas del administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9d9d0-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="9d9d0-104">**Resumen:** Lea este tema para solucionar problemas de implementación de Statistics Manager para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="9d9d0-105">En este tema se describe cómo solucionar problemas de la implementación del administrador de estadísticas mediante la descripción de los eventos que se pueden ver en el registro de eventos de la aplicación y las acciones apropiadas que se pueden llevar a cabo para rectificar el evento.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="9d9d0-106">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="9d9d0-107">Eventos del agente</span><span class="sxs-lookup"><span data-stu-id="9d9d0-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="9d9d0-108">Eventos de escucha</span><span class="sxs-lookup"><span data-stu-id="9d9d0-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="9d9d0-109">Problemas de sitio web</span><span class="sxs-lookup"><span data-stu-id="9d9d0-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="9d9d0-110">Eventos del agente</span><span class="sxs-lookup"><span data-stu-id="9d9d0-110">Agent events</span></span>
<span data-ttu-id="9d9d0-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="9d9d0-111"></span></span>

- <span data-ttu-id="9d9d0-112">**1000**: no se puede configurar el limitador de procesador (objeto de trabajo). Motivo desconocido</span><span class="sxs-lookup"><span data-stu-id="9d9d0-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="9d9d0-113">**1001** : no se permite la limitación del proceso en el proceso (probablemente ya esté dentro de un objeto de trabajo).</span><span class="sxs-lookup"><span data-stu-id="9d9d0-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="9d9d0-114">El agente se ejecuta en un objeto de trabajo de Windows para limitar automáticamente su superficie de memoria.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="9d9d0-115">Si el agente no se inicia y estas entradas de evento se encuentran en el registro de eventos, no se puede crear una instancia del objeto de trabajo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="9d9d0-116">Para evitar este problema, se puede quitar el límite de memoria superior cambiando un valor en el archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="9d9d0-117">Busque "MaxProcessMemoryMB" y cambie el valor a "0", como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="9d9d0-118">Si se realiza este cambio, el agente generalmente consumirá \< 100 MB de memoria, pero no se verá limitado a 300 MB como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="9d9d0-119">Si se realiza este cambio, recomendamos la supervisión minuciosa de la memoria para garantizar que el agente no consuma una gran cantidad de memoria en su equipo host.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="9d9d0-120">**2000**: error en la inicialización del cliente</span><span class="sxs-lookup"><span data-stu-id="9d9d0-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="9d9d0-121">**2001**: no se pudo establecer ninguna conexión con el servicio ni con ninguna IP de origen</span><span class="sxs-lookup"><span data-stu-id="9d9d0-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="9d9d0-122">Si el agente no puede conectarse con el equipo de escucha, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="9d9d0-123">Garantice que el servicio de escucha se esté ejecutando en el equipo de escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="9d9d0-124">Si no, asegúrese de que Redis se esté ejecutando en ese servidor y, a continuación, reinicie el servicio de escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="9d9d0-125">Compruebe el registro de eventos del administrador de estadísticas en el equipo de escucha para asegurarse de que no hay ningún problema con el servicio de escucha del administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="9d9d0-126">Use una herramienta de conectividad como telnet para comprobar la conectividad desde el equipo del agente al de escucha en el puerto correcto.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="9d9d0-127">Si no, asegúrese de que la regla de firewall entrante esté habilitada en el equipo de escucha para el tipo de red al que está conectado el equipo de escucha (privado/público/dominio).</span><span class="sxs-lookup"><span data-stu-id="9d9d0-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="9d9d0-128">Si el equipo de escucha no se une a un dominio, la red puede aparecer como pública y, en ese caso, las reglas de Firewall instaladas con statistic Manager no se aplicarán de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="9d9d0-129">**4000**: error al descargar información del servidor desde la escucha (motivo desconocido)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="9d9d0-130">**4001**: no se encuentra el servidor en la topología de escucha</span><span class="sxs-lookup"><span data-stu-id="9d9d0-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="9d9d0-131">Este error ocurrirá si el servidor se conecta correctamente al agente de escucha, pero el servidor no se agregó a la topología en la caché de la escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="9d9d0-132">Opciones de resolución:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-132">Resolution options:</span></span>
    
  - <span data-ttu-id="9d9d0-p107">	Asegúrese de que ha seguido las instrucciones para importar la topología. Consulte [Importar la topología](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="9d9d0-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="9d9d0-135">Si el agente está en un servidor que no se incluye en la topología (por ejemplo, los nodos de un clúster SQL AlwaysOn), tendrá que agregar el agente manualmente siguiendo las instrucciones de [Importar la topología](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="9d9d0-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="9d9d0-136">**4002**: contraseña de escucha no válida</span><span class="sxs-lookup"><span data-stu-id="9d9d0-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="9d9d0-137">La contraseña cifrada que el agente intenta usar no coincide con la contraseña de servicio de la escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="9d9d0-138">Desinstale el agente y vuelva a instalarlo con la contraseña de servicio correcta.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="9d9d0-139">**4003**: la huella digital del certificado no coincide</span><span class="sxs-lookup"><span data-stu-id="9d9d0-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="9d9d0-140">La huella digital del certificado proporcionado al agente durante la instalación no coincide con la huella digital en el certificado que la escucha está usando actualmente y, por lo tanto, la conexión se rechazará.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="9d9d0-141">Desinstale el agente y vuelva a instalarlo con la huella digital del certificado correcta.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="9d9d0-142">**4004**: respuesta no válida o HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="9d9d0-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="9d9d0-143">La escucha no responde con un estado esperado.  </span><span class="sxs-lookup"><span data-stu-id="9d9d0-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="9d9d0-144">Si la conexión se realiza mediante proxy, compruebe la configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="9d9d0-145">Compruebe el registro de StatsMan del equipo del agente de escucha para ver si hay problemas con su configuración.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="9d9d0-146">**4005**: no se pudo deserializar el XML</span><span class="sxs-lookup"><span data-stu-id="9d9d0-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="9d9d0-147">La información del servidor en el servidor de escucha está dañada o puede que haya un conflicto de versiones entre el agente y los equipos de escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="9d9d0-148">Asegúrese de que las versiones coincidan y compruebe si hay problemas en el registro de eventos de la escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="9d9d0-149">Eventos de escucha</span><span class="sxs-lookup"><span data-stu-id="9d9d0-149">Listener events</span></span>
<span data-ttu-id="9d9d0-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="9d9d0-150"></span></span>

- <span data-ttu-id="9d9d0-151">**10000**: error de inicio con motivo desconocido (son irrecuperables y, como resultado, el servicio se detendrá/bloqueará)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="9d9d0-152">**10001**: problema de configuración</span><span class="sxs-lookup"><span data-stu-id="9d9d0-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="9d9d0-153">En general, se produce cuando el archivo [listener_install_location]\PerfAgentListener.exe.config se ha modificado manualmente y la aplicación no puede leerlo.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="9d9d0-154">**10002**: error de inicialización de la escucha HTTP</span><span class="sxs-lookup"><span data-stu-id="9d9d0-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="9d9d0-155">Por lo general, este evento se registra cuando la ACL de dirección URL no se ha configurado correctamente durante la instalación o el certificado SSL no es válido.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="9d9d0-156">Asegúrese de que el certificado de su configuración sea válido.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="9d9d0-157">Si lo es, reinstale la escucha según las instrucciones de [Implementar el administrador de estadísticas](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="9d9d0-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="9d9d0-158">**10003**: error de Redis</span><span class="sxs-lookup"><span data-stu-id="9d9d0-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="9d9d0-159">**10004**: error de almacenamiento en caché de la infraestructura</span><span class="sxs-lookup"><span data-stu-id="9d9d0-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="9d9d0-160">**10007**: configuración (almacenada en redis)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="9d9d0-161">La escucha no pudo establecer contacto con Redis o recuperar datos bien formados de la caché y no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="9d9d0-162">Asegúrese de que el servicio Redis se haya iniciado y configurado correctamente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="9d9d0-163">**10005**: recuperación/análisis de la información del servidor</span><span class="sxs-lookup"><span data-stu-id="9d9d0-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="9d9d0-164">La información de topología en la caché de Redis no es válida.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="9d9d0-165">Primero, intente reiniciar Redis y la escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="9d9d0-166">Si el error persiste, consulte [Importar la topología](deploy.md#BKMK_ImportTopology) para volver a crear los datos de la topología.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="9d9d0-167">**10100**: interrupción del PING de Redis</span><span class="sxs-lookup"><span data-stu-id="9d9d0-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="9d9d0-168">**10101**: interrupción continuada del PING de Redis (cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="9d9d0-169">**30100**: interrupción del PING de Redis restaurada</span><span class="sxs-lookup"><span data-stu-id="9d9d0-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="9d9d0-170">Estos eventos se registran cuando la escucha no puede conectarse a Redis.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="9d9d0-171">Asegúrese de que Redis se haya iniciado y de que la conectividad de red entre la escucha y Redis esté disponible.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="9d9d0-172">**10200**: interrupción de la escritura de Redis</span><span class="sxs-lookup"><span data-stu-id="9d9d0-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="9d9d0-173">**10201**: interrupción continuada de la escritura de Redis (cada 60 segundos)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="9d9d0-174">**30100**: interrupción de la escritura de Redis resuelta</span><span class="sxs-lookup"><span data-stu-id="9d9d0-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="9d9d0-175">Estos eventos se registran cuando la escucha no puede escribir en la caché de Redis.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="9d9d0-176">Asegúrese de que Redis se haya iniciado y de que la conectividad entre la escucha y Redis esté disponible.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="9d9d0-177">**30000**: se ha iniciado correctamente</span><span class="sxs-lookup"><span data-stu-id="9d9d0-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="9d9d0-178">Se registra cada vez que se inicia la escucha.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="9d9d0-179">**22000** : se completó la inicialización del agente del administrador de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="9d9d0-180">**23000**: EventLogQueryManager se ha inicializado correctamente (primera vez o después de un error)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="9d9d0-181">**24000**: la información del servidor se ha inicializado correctamente (primera vez o después de un error)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="9d9d0-182">**25000**: la escucha vuelve a estar en línea después de un error al publicar (o primera publicación realizada correctamente)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="9d9d0-183">**5000**: inicio de la escucha sin conexión para publicar datos</span><span class="sxs-lookup"><span data-stu-id="9d9d0-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="9d9d0-184">**5001**: la escucha todavía está sin conexión durante un período de tiempo prolongado</span><span class="sxs-lookup"><span data-stu-id="9d9d0-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="9d9d0-185">Estos eventos pueden ser útiles para supervisar o comprender problemas o alertar de ellos.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="9d9d0-186">Problemas de sitio web</span><span class="sxs-lookup"><span data-stu-id="9d9d0-186">Website issues</span></span>
<span data-ttu-id="9d9d0-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="9d9d0-187"></span></span>

- <span data-ttu-id="9d9d0-188">Solicitudes de inicio de sesión repetitivas en Chrome: este es un error que se ha resuelto en la versión 1,1.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="9d9d0-189">Asegúrese de haber actualizado a la última versión de statistic Manager si está viendo solicitudes de inicio de sesión repetidas en el explorador Chrome.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="9d9d0-190">Para comprobar la versión del sitio web en el que se está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="9d9d0-191">	En el Explorador de archivos, abra (directorio predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9d9d0-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="9d9d0-192">Haga clic con el botón derecho en StatsManHubWebSite.dll y consulte sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="9d9d0-193">Si un equipo no se encuentra en la vista horizontal de KHI o en la vista Detalles de contador, asegúrese de que sea miembro de un sitio y un grupo.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="9d9d0-194">Si no lo es, no aparecerá en esas vistas.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="9d9d0-195">Para obtener información sobre cómo definir un sitio y un grupo para un servidor en la topología, vea [Importar la topología](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="9d9d0-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="9d9d0-196">La versión del producto se mostrará en los detalles de Descripción.</span><span class="sxs-lookup"><span data-stu-id="9d9d0-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="9d9d0-197">Más información</span><span class="sxs-lookup"><span data-stu-id="9d9d0-197">For more information</span></span>
<span data-ttu-id="9d9d0-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="9d9d0-198"></span></span>

<span data-ttu-id="9d9d0-199">Para obtener más información, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d9d0-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="9d9d0-200">Planear el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9d9d0-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="9d9d0-201">Implementar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9d9d0-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="9d9d0-202">Actualizar el administrador de estadísticas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9d9d0-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
