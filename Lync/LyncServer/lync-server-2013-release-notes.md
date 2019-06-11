---
title: 'Lync Server 2013: Notas de la versión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="b5e2c-102">Notas de la versión de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5e2c-103">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="b5e2c-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="b5e2c-104">Bienvenido a las notas de la versión de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="b5e2c-105">Consulte este archivo para obtener información sobre los problemas conocidos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="b5e2c-106">Acerca de este documento</span><span class="sxs-lookup"><span data-stu-id="b5e2c-106">About this document</span></span>

<span data-ttu-id="b5e2c-107">Este documento contiene información importante que debe conocer antes de implementar y usar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="b5e2c-108">Para obtener más información sobre Lync Server 2013, consulte la documentación de [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="b5e2c-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="b5e2c-109">Este documento contiene las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="b5e2c-110">Cliente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-110">Lync 2013 client</span></span>

  - <span data-ttu-id="b5e2c-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="b5e2c-111">Lync Server</span></span>

  - <span data-ttu-id="b5e2c-112">Instalación</span><span class="sxs-lookup"><span data-stu-id="b5e2c-112">Installation</span></span>

  - <span data-ttu-id="b5e2c-113">Movilidad</span><span class="sxs-lookup"><span data-stu-id="b5e2c-113">Mobility</span></span>

  - <span data-ttu-id="b5e2c-114">Conferencias</span><span class="sxs-lookup"><span data-stu-id="b5e2c-114">Conferencing</span></span>

  - <span data-ttu-id="b5e2c-115">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="b5e2c-115">Enterprise Voice</span></span>

  - <span data-ttu-id="b5e2c-116">Presencia</span><span class="sxs-lookup"><span data-stu-id="b5e2c-116">Presence</span></span>

  - <span data-ttu-id="b5e2c-117">Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="b5e2c-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="b5e2c-118">Panel de control de Lync Server, Generador de topologías y Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="b5e2c-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="b5e2c-119">Local</span><span class="sxs-lookup"><span data-stu-id="b5e2c-119">Localization</span></span>

  - <span data-ttu-id="b5e2c-120">Tratados</span><span class="sxs-lookup"><span data-stu-id="b5e2c-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="b5e2c-121">Cliente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="b5e2c-122">La transferencia de un archivo en un mensaje instantáneo da error si el archivo está abierto en otra aplicación</span><span class="sxs-lookup"><span data-stu-id="b5e2c-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="b5e2c-123">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-123">**Issue:**</span></span>

<span data-ttu-id="b5e2c-124">Si intenta transferir un archivo, como un documento de Word, incluyendo en un mensaje instantáneo a otro usuario de Lync, la transferencia parecerá que se realizará correctamente, pero es posible que no se pueda transferir el archivo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="b5e2c-125">Se mostrará un icono para el tipo de archivo en el cliente de Lync, pero el destinatario no podrá abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="b5e2c-126">No se muestra ningún mensaje de error para informarle que la transferencia no se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="b5e2c-127">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-127">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-128">Para evitar este problema, cierre el archivo abierto o la aplicación que lo tiene abierto antes de intentar transferir el archivo en un mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="b5e2c-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="b5e2c-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="b5e2c-130">Si se produce un error en la replicación de datos del servicio de almacenamiento de Lync Server, los administradores deberán comprobar los contadores de rendimiento de los elementos de cola del servicio de almacenamiento obsoleto</span><span class="sxs-lookup"><span data-stu-id="b5e2c-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="b5e2c-131">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-131">**Issue:**</span></span>

<span data-ttu-id="b5e2c-132">El servicio de almacenamiento de Lync Server usa Windows fabric para la replicación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="b5e2c-133">Si se eliminan datos en un servidor front-end principal, pero se produce un error en la eliminación en un servidor de front-end secundario (por ejemplo, si hay un apagado inesperado o un error en el servidor front-end), los datos se pueden dejar atrás y "huérfanos".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="b5e2c-134">Los datos huérfanos pueden hacer que el rendimiento se degrade y desperdicie espacio en la unidad.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="b5e2c-135">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-135">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-136">Para solucionar este problema, si se generan los eventos\_LYSS\_dB\_Space\_use error (ID = 32058) y\_LYSS\_dB\_Space\_use Critical (ID = 32059) en el registro de eventos, los administradores deben comprobar la contador de rendimiento en el servidor front-end en **LS: LYSS-API de servicio de almacenamiento** con el nombre **LYSS-número actual de elementos de cola obsoletos del servicio de almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="b5e2c-137">Si este contador de rendimiento tiene un valor alto (por ejemplo, mayor que 50000), el administrador debe ejecutar la herramienta CleanuUpStorageServiceData. exe del kit de recursos de Lync Server 2013, que eliminará todos los datos huérfanos del grupo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="b5e2c-138">Para obtener más información sobre la herramienta, consulte la documentación del kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="b5e2c-139">Cada vez que se cambie la configuración de la dirección IP de un servidor o grupo, es necesario reiniciar los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="b5e2c-140">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-140">**Issue:**</span></span>

<span data-ttu-id="b5e2c-141">Cuando se cambia la configuración de la dirección IP en una implementación de Lync Server 2013, por ejemplo, al cambiar de IPv4 a pila dual o de pila doble a IPv6, no todos los componentes del servidor recogen el cambio de configuración hasta que se reinicien los servicios.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="b5e2c-142">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-142">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-143">Para solucionar este problema, reinicie los servicios de Lync Server después de cambiar la configuración de la dirección IP de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="b5e2c-144">Para ello, ejecute los siguientes cmdlets en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="b5e2c-145">El cmdlet de la transacción sintética de las conferencias de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="b5e2c-146">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-146">**Issue:**</span></span>

<span data-ttu-id="b5e2c-147">El cmdlet **Test-CsDialInConferencing** de la transacción sintética de conferencias de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="b5e2c-148">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-148">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-149">El uso del cmdlet de transacciones sintéticas de las conferencias de acceso telefónico local **prueba-CsDialInConferencing** es compatible solamente internamente con una empresa.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="b5e2c-150">Los administradores pueden continuar usando el cmdlet en el shell de administración de Lync Server para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="b5e2c-151">Si es necesario, una empresa también puede desarrollar un paquete de administración privado para ejecutar el cmdlet de forma interna.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="b5e2c-152">El servicio de registro centralizado se detiene si el tráfico de red se interrumpe cuando los archivos de registro se copian en un recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="b5e2c-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="b5e2c-153">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-153">**Issue:**</span></span>

<span data-ttu-id="b5e2c-154">Cuando el servicio de registro centralizado está configurado para usar una ruta de acceso de red (el valor del parámetro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** es una ruta de acceso UNC válida), los archivos de registro en caché se copian en el recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="b5e2c-155">Si se produce una interrupción en el tráfico de red mientras se copian los archivos, se producirá una excepción que hará que el servicio de registro centralizado se detenga.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="b5e2c-156">El servicio está configurado para reiniciarse automáticamente hasta tres veces, de modo que el servicio se recupere de las tres primeras excepciones.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="b5e2c-157">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-157">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-158">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-158">There is no workaround for this issue.</span></span> <span data-ttu-id="b5e2c-159">Para identificar el problema, supervise el registro de eventos para el identificador de evento 7031 del "Administrador de control de servicios" que registra cuando el servicio "agente de servicios de registro centralizado de Lync Server" ha finalizado inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="b5e2c-160">Si esto sucede más de tres veces, reinicie el servicio de forma manual con el cmdlet **Start-CsWindowService** .</span><span class="sxs-lookup"><span data-stu-id="b5e2c-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="b5e2c-161">Los elementos de la cola del servicio de almacenamiento necesitan importarse manualmente</span><span class="sxs-lookup"><span data-stu-id="b5e2c-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="b5e2c-162">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-162">**Issue:**</span></span>

<span data-ttu-id="b5e2c-163">Lync Server 2013 almacena datos sobre las conferencias y la mensajería instantánea, como los mensajes archivados y la grabación de detalles de llamadas (CDR), en una base de datos en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="b5e2c-164">Los datos se almacenan en la base de datos mientras se procesan antes de enviarse al destino previsto.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="b5e2c-165">Para mejorar el rendimiento, Lync Server 2013 exporta periódicamente los elementos de cola de la base de datos local que no se procesan durante un período de tiempo prolongado y los guarda en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="b5e2c-166">Si el almacén de archivos no está disponible, los elementos se almacenan en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="b5e2c-167">Se produce la misma operación para evitar la pérdida de datos durante la conmutación por error de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="b5e2c-168">Durante la operación de exportación, el servicio de almacenamiento de Lync Server registra cada una de las fases en el registro de eventos con los identificadores de evento de 32075 (inicio completo), 32076 (vaciado completo), 32082 (se inicia el nivel de mantenimiento), 32083 (volcado de nivel de mantenimiento se ha completado), 32089 (vaciado debido a rellenando la base de datos).</span><span class="sxs-lookup"><span data-stu-id="b5e2c-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="b5e2c-169">Estos datos no se volverán a importar automáticamente al sistema para ser procesados y enviados a su destino final (SQL Server o Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="b5e2c-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="b5e2c-170">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-170">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-171">Para importar los datos en el sistema, los administradores deberán usar la herramienta ImportStorageServiceData del kit de recursos de Lync Server, que agregará los datos al sistema para ser procesados y enviados a su destino final.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="b5e2c-172">Se producirá un error en las búsquedas en la libreta de direcciones web de libreta de direcciones si el valor predeterminado de UseNormalizationRules cambia a false.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="b5e2c-173">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-173">**Issue:**</span></span>

<span data-ttu-id="b5e2c-174">Si el valor predeterminado de UseNormalizationRules se cambia a false, las búsquedas en la libreta de direcciones web no se realizarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="b5e2c-175">Una vez que se cambie el valor predeterminado, los usuarios del cliente de Lync no podrán usar la consulta Web de la libreta de direcciones de Lync para buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="b5e2c-176">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-176">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-177">Si el valor predeterminado de UseNormalizationRules se establece en false para que los usuarios puedan usar números de teléfono definidos en los servicios de dominio de Active Directory sin Lync Server 2013 aplicando reglas de normalización, haga lo siguiente para solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="b5e2c-178">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b5e2c-179">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="b5e2c-180">Si su implementación solo incluye servidores de Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de UseNormalizationRules y IgnoreGenericRules a true:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="b5e2c-181">Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Lync Server 2013 en la topología:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="b5e2c-182">Espere a que se produzca la replicación de CMS en todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="b5e2c-183">Modifique el archivo de reglas de normalización de teléfonos de su implementación para borrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="b5e2c-184">El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="b5e2c-185">Si el archivo no está presente, cree un archivo vacío denominado "regla de\_\_normalización\_\_de número de teléfono de la empresa. txt".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="b5e2c-186">Espere unos minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="b5e2c-187">Ejecute el siguiente cmdlet en cada grupo de servidores de Lync Server 2013 de su implementación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="b5e2c-188">El evento de error del servidor de la libreta de direcciones 21054 se genera una vez al día para cada grupo de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="b5e2c-189">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-189">**Issue:**</span></span>

<span data-ttu-id="b5e2c-190">El servidor de la libreta de direcciones de Lync Server 2013 generará el evento de error 21054 una vez al día al realizar el mantenimiento diario.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="b5e2c-191">El error también se genera cada vez que un administrador ejecuta el cmdlet **Update-csAddressBook** , incluso cuando la actualización se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="b5e2c-192">Sin embargo, este evento de error puede ignorarse con seguridad cuando la actualización se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="b5e2c-193">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-193">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-194">Cuando encuentre este evento de error, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="b5e2c-195">Si el cmdlet informa de que no hay objetos no indizados ni abandonados, se puede ignorar el evento de error 21054.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="b5e2c-196">Además, el indicador de mantenimiento de clave (KHI) "los usuarios de la libreta de direcciones correctamente indizados" deberían estar desactivados en System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="b5e2c-197">Las solicitudes pueden fallar cuando se configura IPv6 en un grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="b5e2c-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="b5e2c-198">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-198">**Issue:**</span></span>

<span data-ttu-id="b5e2c-199">Cuando se configura IPv6 en un grupo Edge, algunas solicitudes al grupo perimetral pueden fallar.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="b5e2c-200">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-200">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-201">Para solucionar este problema, no configure un grupo perimetral con IPv6.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="b5e2c-202">El cmdlet Invoke-csPoolFailback puede fallar durante la conmutación por recuperación del grupo</span><span class="sxs-lookup"><span data-stu-id="b5e2c-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="b5e2c-203">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-203">**Issue:**</span></span>

<span data-ttu-id="b5e2c-204">Al intentar devolver un grupo por error, el cmdlet **Invoke-csPoolFailback** puede dar el error "no se pudo completar el proceso de hidratación tras un intento repetido".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="b5e2c-205">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-205">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-206">Para solucionar este problema, ejecute el cmdlet de nuevo y espere hasta que el cmdlet se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="b5e2c-207">Tenga en cuenta que el proceso de conmutación por recuperación puede demorar varios minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="b5e2c-208">Una agrupación con usuarios de 20.000 puede tardar hasta 60 minutos.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="b5e2c-209">Se pueden perder datos al agregar un servidor front-end a un grupo ya establecido: híbrido, Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="b5e2c-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="b5e2c-210">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-210">**Issue:**</span></span>

<span data-ttu-id="b5e2c-211">Puede encontrarse este problema en un entorno en el que un grupo tiene más de un servidor front-end y se puede reiniciar uno de los servidores front-end o agregar un nuevo servidor front-end que no fuera parte del grupo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="b5e2c-212">Los usuarios cuyos datos se estén archivados pueden experimentar pérdida de datos hasta que se haya establecido una distribución estable del archivado de datos para el grupo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="b5e2c-213">Este período de pérdida potencial de datos se limita a 15 minutos para las conversaciones entre personas y 30 minutos para las conferencias.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="b5e2c-214">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-214">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-215">Al realizar el mantenimiento, en lugar de iniciar servidores front-end en el grupo uno por uno, debe realizar la conmutación por error del grupo a otro grupo y, a continuación, realizar tareas de mantenimiento en los servidores.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="b5e2c-216">También puede hacer que el servicio no esté disponible antes de realizar tareas de mantenimiento y, a continuación, restaurar la disponibilidad cuando el mantenimiento se haya completado.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="b5e2c-217">Los administradores no pueden obtener el recuento de licencias mediante el cmdlet Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="b5e2c-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="b5e2c-218">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-218">**Issue:**</span></span>

<span data-ttu-id="b5e2c-219">Los administradores no pueden obtener un uso preciso de licencias de cliente mediante el cmdlet **Get-CsClientAccessLicense** .</span><span class="sxs-lookup"><span data-stu-id="b5e2c-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="b5e2c-220">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-220">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-221">Para comprobar el tipo de licencia de servidor, puede ejecutar el cmdlet **Get-CsService** para recuperar los nombres de dominio completos (FDQNs) de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="b5e2c-222">Si el FQDN del servidor front-end es el mismo que el FQDN de la base de datos back-end, la licencia es una licencia Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="b5e2c-223">De lo contrario, la licencia es una licencia de Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="b5e2c-224">El número de licencias de cliente no se ha notificado de forma precisa</span><span class="sxs-lookup"><span data-stu-id="b5e2c-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="b5e2c-225">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-225">**Issue:**</span></span>

<span data-ttu-id="b5e2c-226">Al determinar los recuentos de licencias de los clientes, es posible que se produzcan las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="b5e2c-227">**Recuento de licencias inexacto para usuarios móviles**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="b5e2c-228">El recuento de licencias se basa en el número de direcciones IP únicas para los usuarios basados en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="b5e2c-229">El recuento de licencias se limitará de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="b5e2c-230">Las licencias se sobrescribirán si la dirección IP del usuario cambia durante las sesiones de Lync.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="b5e2c-231">Esto puede ocurrir cuando un usuario se conecta a Lync Server desde más de una ubicación con un cliente de escritorio.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="b5e2c-232">Las licencias se recontarán si un usuario se conecta a un cliente móvil, ya que no se puede determinar la dirección IP para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="b5e2c-233">**Las licencias se cuentan dos veces para llamadas de red telefónica conmutada (RTC) a clientes de Lync, llamadas de cliente de Lync a líneas RTC y llamadas de Lync a líneas RTC**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="b5e2c-234">En los siguientes escenarios, se contarán dos licencias adicionales en lugar de una porque tanto el número de teléfono como el usuario de Lync se tienen en cuenta para determinar el número de licencias que se usan.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="b5e2c-235">Para obtener datos de licencias precisos, quite manualmente las licencias generadas por un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="b5e2c-236">Una llamada telefónica RTC a Lync</span><span class="sxs-lookup"><span data-stu-id="b5e2c-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="b5e2c-237">Una llamada de Lync a una línea RTC</span><span class="sxs-lookup"><span data-stu-id="b5e2c-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="b5e2c-238">Una llamada RTC a Lync y, a continuación, Lync reenvía la llamada a una línea RTC.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="b5e2c-239">Se contará con una de las líneas RTC.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="b5e2c-240">**No se contará una licencia para un teléfono de Lync conectado**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="b5e2c-241">Cuando un usuario usa un teléfono certificado por Lync, si el teléfono inicia sesión y se mantiene conectado, lo cual conserva su estado de inicio de sesión, el teléfono no se contará como si estuviera usando una licencia si la consulta de licencias se produce después de que el teléfono haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="b5e2c-242">**Licencias contadas para teléfonos RTC que se unen a conferencias**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="b5e2c-243">Cuando un usuario se une a una conferencia con un teléfono RTC, se contará con una licencia de forma inexacta para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="b5e2c-244">Sin embargo, no se necesita ninguna licencia para unirse a una conferencia con un teléfono PSTN.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="b5e2c-245">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-245">**Workaround:**</span></span>

1.  <span data-ttu-id="b5e2c-246">**Recuento de licencias inexacto para usuarios móviles**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="b5e2c-247">Puede identificar manualmente las direcciones IP que pertenecen al mismo dispositivo y, a continuación, quitar una de ellas en el recuento de licencias.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="b5e2c-248">No hay ninguna solución alternativa para este problema con los dispositivos móviles que se conectan con el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="b5e2c-249">**Las licencias se cuentan dos veces para las llamadas RTC al cliente de Lync, las llamadas del cliente de Lync a las líneas RTC y las llamadas de Lync a las líneas RTC**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="b5e2c-250">Tendrá que identificar manualmente el número de teléfono RTC y quitar el recuento de licencias generado para él.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="b5e2c-251">**No se contará una licencia para un teléfono de Lync que ha iniciado sesión**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="b5e2c-252">Puede configurar el teléfono de Lync para cerrar sesión y, a continuación, volver a iniciar sesión, a intervalos regulares, como cada 3 meses.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="b5e2c-253">**Licencias contadas para teléfonos RTC que se unen a conferencias**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="b5e2c-254">Puede identificar manualmente el número de teléfono RTC que se usa para unirse a la Conferencia y quitar la licencia generada por el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="b5e2c-255">El panel de control de Lync Server deja de funcionar en un entorno de VMware después de actualizar a Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="b5e2c-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="b5e2c-256">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-256">**Issue:**</span></span>

<span data-ttu-id="b5e2c-257">Si usa el panel de control de Lync Server en un entorno de VMware, es posible que el panel de control de Lync Server deje de funcionar después de actualizar Microsoft Silverlight a la versión 5.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="b5e2c-258">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-258">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-259">Para solucionar este problema, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b5e2c-260">Desinstale Silverlight 5 e instale Silverlight 4 desde [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span><span class="sxs-lookup"><span data-stu-id="b5e2c-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="b5e2c-261">Obtener acceso al panel de control de Lync Server desde un equipo que no es un equipo virtual de VMware.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="b5e2c-262">Para ello, puede iniciar el panel de control de Lync Server en el menú **Inicio** de Windows en el servidor, si las herramientas de administración de Lync Server están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="b5e2c-263">También puede obtener acceso al panel de control de Lync Server mediante un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="b5e2c-264">La dirección URL será similar a https://\<Front\_-\_end\>Pool FQDN/CSCP.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="b5e2c-265">La información de usuario del servicio de libreta de direcciones no se actualiza después de que se modifique el nombre completo del usuario en Active Directory</span><span class="sxs-lookup"><span data-stu-id="b5e2c-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="b5e2c-266">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-266">**Issue:**</span></span>

<span data-ttu-id="b5e2c-267">Si se cambia el nombre completo de un usuario (también conocido como DN) en servicios de dominio de Active Directory, los cambios adicionales no se actualizarán en el servicio de libreta de direcciones (ABS).</span><span class="sxs-lookup"><span data-stu-id="b5e2c-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="b5e2c-268">Esto no afecta al inicio de sesión ni a la presencia del usuario, pero evitará la comunicación para el usuario si también cambia la dirección SIP, ya que las búsquedas devolverán una dirección SIP obsoleta.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="b5e2c-269">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-269">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-270">Para solucionar este problema, no cambie el nombre completo de un usuario.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="b5e2c-271">Si revierte el nombre completo para el usuario al valor anterior, las actualizaciones se reflejarán en el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="b5e2c-272">Instalación</span><span class="sxs-lookup"><span data-stu-id="b5e2c-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="b5e2c-273">El uso de caracteres que no sean ASCII puede dar lugar a que no se inicie Lync Server</span><span class="sxs-lookup"><span data-stu-id="b5e2c-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="b5e2c-274">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-274">**Issue:**</span></span>

<span data-ttu-id="b5e2c-275">El programa de instalación fallará si el nombre de la carpeta de destino incluye caracteres que no son ASCII (incluidos Unicode, juego de caracteres de doble byte (DBCS), UTF-8 y UTF-16).</span><span class="sxs-lookup"><span data-stu-id="b5e2c-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="b5e2c-276">Además, es posible que el programa de instalación se complete correctamente, pero el servidor no se iniciará si alguno de los caracteres que no son ASCII está contenido en alguno de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="b5e2c-277">Nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="b5e2c-277">Computer name</span></span>

  - <span data-ttu-id="b5e2c-278">Nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="b5e2c-278">Domain name</span></span>

  - <span data-ttu-id="b5e2c-279">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="b5e2c-279">User name</span></span>

  - <span data-ttu-id="b5e2c-280">URI del SIP del usuario</span><span class="sxs-lookup"><span data-stu-id="b5e2c-280">User SIP URI</span></span>

  - <span data-ttu-id="b5e2c-281">Nombre de la cuenta de servicio</span><span class="sxs-lookup"><span data-stu-id="b5e2c-281">Service account name</span></span>

<span data-ttu-id="b5e2c-282">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-282">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-283">Use solo caracteres ASCII en el nombre de la carpeta de destino, el nombre del equipo, el nombre de dominio, el nombre de usuario, el URI SIP del usuario y los nombres de cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="b5e2c-284">El Hotfix para "el montón de daños se produce cuando un módulo llama al método InsertEntityBody en IIS 7,5" debe estar instalado antes de instalar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="b5e2c-285">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-285">**Issue:**</span></span>

<span data-ttu-id="b5e2c-286">El Hotfix de "el montón de daños se produce cuando un módulo llama al método InsertEntityBody en IIS[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)7,5" (), que se describe en el[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)artículo 264886 () de Microsoft Knowledge base, debe instalarse antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="b5e2c-287">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-287">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-288">Descargue e instale el Hotfix desde el centro de descarga de [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="b5e2c-289">Lync Server 2013 no se puede instalar en la versión de RTM del sistema operativo ITA de Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b5e2c-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="b5e2c-290">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-290">**Issue:**</span></span>

<span data-ttu-id="b5e2c-291">Error en la instalación de Lync Server 2013 en Windows Server 2012 de ITA debido a errores en la instalación de Windows fabric.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="b5e2c-292">Error en la instalación de Windows fabric porque las trazas de tejido se crean con el formato de hora HH: MM: SS.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="b5e2c-293">Sin embargo, en ITA Windows Server, el formato de hora es HH. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="b5e2c-294">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-294">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-295">Para solucionar este problema, actualice el registro del sistema antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="b5e2c-296">La clave del registro que necesita actualizarse es: usuarios\_\\HKEY. \\STimeFormat\\predeterminado del panel\\de control.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="b5e2c-297">Cambie el valor de sTimeFormat a HH: mm: SS usando la interfaz de línea de comandos de Windows PowerShell de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="b5e2c-298">Inicie Windows PowerShell y ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="b5e2c-299">Para ver el valor actual, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="b5e2c-300">Anote el valor actual de sTimeFormat para que se pueda restaurar una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="b5e2c-301">Para establecer en nuevo valor, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="b5e2c-302">Después de instalar Lync Server 2013 correctamente, restaure el valor original de la sTimeFormat ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="b5e2c-303">Set-ItemProperty $a-Name sTimeFormat "<valor que se anota en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="b5e2c-304">encima de> "</span><span class="sxs-lookup"><span data-stu-id="b5e2c-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="b5e2c-305">Movilidad</span><span class="sxs-lookup"><span data-stu-id="b5e2c-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="b5e2c-306">Problemas para clientes móviles durante el proceso de conmutación por error del servidor</span><span class="sxs-lookup"><span data-stu-id="b5e2c-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="b5e2c-307">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-307">**Issue:**</span></span>

<span data-ttu-id="b5e2c-308">Cuando se produce un error en Lync Server y comienza el proceso de conmutación por error, los siguientes problemas pueden afectar a los usuarios de clientes móviles:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="b5e2c-309">No hay ninguna llamada o señal de Lync entrante durante un máximo de 10 minutos después de que se inicie la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="b5e2c-310">No se aceptan solicitudes entrantes de chat</span><span class="sxs-lookup"><span data-stu-id="b5e2c-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="b5e2c-311">No se pueden unir reuniones si el servidor con error es el servidor principal para el usuario</span><span class="sxs-lookup"><span data-stu-id="b5e2c-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="b5e2c-312">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-312">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-313">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-313">There is no workaround for this issue.</span></span> <span data-ttu-id="b5e2c-314">La funcionalidad normal se restaurará una vez que se complete el proceso de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="b5e2c-315">Si un usuario móvil rechaza una llamada entrante desde otro extremo de Lync, la llamada se muestra como una conversión perdida en clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="b5e2c-316">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-316">**Issue:**</span></span>

<span data-ttu-id="b5e2c-317">Si un usuario móvil rechaza una llamada entrante y la llamada se originó desde otro extremo de Lync, la llamada se muestra como una conversación perdida en el cliente móvil de Lync, en lugar de una llamada en la lista de llamadas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="b5e2c-318">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-318">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-319">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="b5e2c-320">Es posible que el cliente móvil no muestre el nombre para mostrar de un contacto federado al buscar contactos</span><span class="sxs-lookup"><span data-stu-id="b5e2c-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="b5e2c-321">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-321">**Issue:**</span></span>

<span data-ttu-id="b5e2c-322">Es posible que el nombre para mostrar de los contactos federados no se muestre en algunos escenarios, como cuando se busca un contacto federado en la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="b5e2c-323">Esto puede ocurrir cuando no hay una suscripción de presencia activa para el contacto desde el cliente móvil de Lync.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="b5e2c-324">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-324">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-325">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="b5e2c-326">En el cliente móvil, falta la información de la invitación y la marca de hora de una conversación perdida que es una invitación a una conferencia</span><span class="sxs-lookup"><span data-stu-id="b5e2c-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="b5e2c-327">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-327">**Issue:**</span></span>

<span data-ttu-id="b5e2c-328">En el cliente móvil, cuando una conversación perdida es una invitación a una conferencia, la información de la invitación y la marca de hora no se encuentra en el mensaje de conversación perdido.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="b5e2c-329">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-329">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-330">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="b5e2c-331">Los usuarios de clientes móviles que hacen llamadas mediante VoIP no pueden abandonar el correo de voz para los usuarios cuyo correo de voz esté configurado en Exchange 2010 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="b5e2c-332">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-332">**Issue:**</span></span>

<span data-ttu-id="b5e2c-333">Si un usuario de un cliente móvil usa VoIP para realizar llamadas, el usuario no podrá dejar mensajes de correo de voz para los usuarios configurados para usar el correo de voz en Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="b5e2c-334">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-334">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-335">Para solucionar este problema, use Exchange 2010 con SP1 o una versión posterior de Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="b5e2c-336">Al usar Block con URL para la configuración de versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto</span><span class="sxs-lookup"><span data-stu-id="b5e2c-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="b5e2c-337">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-337">**Issue:**</span></span>

<span data-ttu-id="b5e2c-338">Cuando se usa **Block with URL** para la configuración de la versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto cuando la versión del cliente no es compatible.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="b5e2c-339">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-339">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-340">Para evitar este problema, configure la versión del cliente para que use **Block** en lugar de **Block with URL**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="b5e2c-341">Conferencias</span><span class="sxs-lookup"><span data-stu-id="b5e2c-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="b5e2c-342">El software antivirus que se ejecuta en los servidores front-end de Lync Server 2013 puede provocar reciclado del dominio de la aplicación, que interrumpe temporalmente el servicio para Lync Web App 2013, Lync Mobile 2010 y clientes de Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="b5e2c-343">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-343">**Issue:**</span></span>

<span data-ttu-id="b5e2c-344">El software antivirus puede desencadenar el reinicio del dominio de la aplicación, lo que puede dar como resultado aplicaciones de cliente de Lync Mobility Service 2013 y comunicaciones unificadas (UC) web API (Lync Web App 2013, Lync Mobile 2010 y Lync Mobile 2013) para perder su estado.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="b5e2c-345">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-345">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-346">Para evitar este problema, excluya las carpetas que contienen los componentes Web y .NET Framework de la detección de virus.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="b5e2c-347">Para obtener más información, consulte el artículo 312592 de Microsoft Knowledge base, "error PRB: el reinicio de la aplicación aleatoria con ' la aplicación se está reiniciando" en ASP.NET [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span><span class="sxs-lookup"><span data-stu-id="b5e2c-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="b5e2c-348">Se deben excluir las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="b5e2c-349">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX ext</span><span class="sxs-lookup"><span data-stu-id="b5e2c-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="b5e2c-350">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX int</span><span class="sxs-lookup"><span data-stu-id="b5e2c-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="b5e2c-351">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\de Ucwa int</span><span class="sxs-lookup"><span data-stu-id="b5e2c-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="b5e2c-352">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\de Ucwa ext</span><span class="sxs-lookup"><span data-stu-id="b5e2c-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="b5e2c-353">% WINDIR%\\Microsoft.net\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="b5e2c-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="b5e2c-354">Los controles ActiveX o la compatibilidad de XMLHTTP nativa deben estar habilitados en Windows Internet Explorer para unirse correctamente a las conferencias</span><span class="sxs-lookup"><span data-stu-id="b5e2c-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="b5e2c-355">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-355">**Issue:**</span></span>

<span data-ttu-id="b5e2c-356">Si un usuario ha deshabilitado los controles ActiveX y la compatibilidad con XMLHTTP nativa en la configuración del explorador de Internet de Windows Internet Explorer, el usuario no podrá unirse a una reunión si Internet Explorer está seleccionado como el explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="b5e2c-357">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-357">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-358">Habilite los controles ActiveX o la "compatibilidad con XMLHTTP nativo" en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="b5e2c-359">El servicio de conferencias web de Lync Server no puede recuperarse desde el modo crítico</span><span class="sxs-lookup"><span data-stu-id="b5e2c-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="b5e2c-360">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-360">**Issue:**</span></span>

<span data-ttu-id="b5e2c-361">Si se activa el modo crítico para el archivado, en caso de que se produzcan errores en el sistema, se iniciará el modo crítico y las conferencias dejarán de funcionar para los participantes.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="b5e2c-362">Una vez que el administrador soluciona los errores del sistema (como corregir un problema de la base de datos), el servicio Conferencia de datos no se recupera automáticamente y el administrador debe reiniciar manualmente el servicio de conferencia para que se reanude la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="b5e2c-363">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-363">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-364">Un administrador debe reiniciar manualmente el servicio de conferencia después de que se haya corregido el error del sistema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="b5e2c-365">El servicio de conferencias por Internet omite el proxy HTTP para servidores externos de Office Web App</span><span class="sxs-lookup"><span data-stu-id="b5e2c-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="b5e2c-366">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-366">**Issue:**</span></span>

<span data-ttu-id="b5e2c-367">Si ha implementado un servidor de Office Web Apps externo al servicio de conferencias web (es decir, un servidor que no está en la red corporativa interna) en Internet, la red perimetral y el servicio de conferencias web requiere un proxy HTTP para conectarse a este, el Se producirá un error en la detección de Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="b5e2c-368">El servicio de conferencias por Internet pasa por alto la configuración de proxy HTTP, según se define en el generador de topologías para la configuración de Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="b5e2c-369">Como resultado, el cliente de Lync no podrá compartir Microsoft PowerPoint 2010 con otros participantes de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="b5e2c-370">Si está instalando Lync Server local y también configura Office Web Apps Server local en la red interna, no se requiere una configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="b5e2c-371">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-371">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-372">La única solución alternativa es no tener una configuración de implementación que requiera el uso de proxy HTTP para comunicarse con un servidor externo de Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="b5e2c-373">No se admite Agregar vídeo a una conferencia de proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="b5e2c-374">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-374">**Issue:**</span></span>

<span data-ttu-id="b5e2c-375">No se puede Agregar un vídeo si el usuario se une a una conferencia de proveedor de servicios de audioconferencia para el audio.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="b5e2c-376">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-376">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-377">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="b5e2c-378">Topologías con IPv6 habilitada fuerce la actualización automática del complemento Silverlight Web App Silverlight para garantizar que la funcionalidad de pantalla compartida pueda funcionar desde Lync Web App</span><span class="sxs-lookup"><span data-stu-id="b5e2c-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="b5e2c-379">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-379">**Issue:**</span></span>

<span data-ttu-id="b5e2c-380">Cuando una topología está configurada con IPv6 habilitado, los usuarios no pueden compartir su pantalla desde el cliente de Lync Web App si ya está instalada una versión anterior del complemento de uso compartido de pantalla.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="b5e2c-381">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-381">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-382">Para forzar una actualización a la versión más reciente del complemento de uso compartido de la pantalla al unirse a una reunión a través de Lync Web App, modifique el valor de **MinSupportedBuildVersion** de "4.0.7457.0" a "4.0.7577.380" en los dos archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="b5e2c-383">% ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\póngase\\en\\contacto con\\los\\complementos de cliente int ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="b5e2c-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="b5e2c-384">% ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\\\\\plug and ext Plug\\and ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="b5e2c-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="b5e2c-385">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="b5e2c-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="b5e2c-386">En algunos casos, es posible que un cliente de Lync que se ejecuta en un equipo configurado para usar IPv4 e IPv6 Dual Stack no admita capacidades basadas en la subred IP del equipo, como E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b5e2c-387">La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b5e2c-388">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-388">**Issue:**</span></span>

<span data-ttu-id="b5e2c-389">Cuando un cliente de Lync se ejecuta en un equipo que está habilitado para IPv4 e IPv6 Dual Stack y en función de la resolución DNS del servidor proxy, el cliente puede usar la dirección IPv6 del equipo para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="b5e2c-390">Después de hacerlo, el cliente de Lync solo admitirá las capacidades admitidas para IPv6, que excluye E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="b5e2c-391">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-391">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-392">Para solucionar este problema, deshabilite la compatibilidad de IPv6 en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="b5e2c-393">Si la telefonía IP empresarial no está configurada para un usuario, el usuario tendrá que usar el formato E164 para llamar desde una conferencia.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="b5e2c-394">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-394">**Issue:**</span></span>

<span data-ttu-id="b5e2c-395">Si la telefonía IP empresarial no está configurada para un usuario, ese usuario tendrá que usar el formato E164 para llamar correctamente desde una conferencia.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="b5e2c-396">Si no se usa el formato E164, el usuario no podrá llamar desde la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="b5e2c-397">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-397">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-398">Para evitar este problema, los usuarios que no tengan habilitada la telefonía IP empresarial deben llamar desde una conferencia usando números en formato E164.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="b5e2c-399">Presencia</span><span class="sxs-lookup"><span data-stu-id="b5e2c-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="b5e2c-400">Si un usuario ha seleccionado "bloquear todas las invitaciones y comunicaciones" mientras el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechazará cuando deba</span><span class="sxs-lookup"><span data-stu-id="b5e2c-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="b5e2c-401">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-401">**Issue:**</span></span>

<span data-ttu-id="b5e2c-402">Si un usuario ha seleccionado "bloquear todas las invitaciones y comunicaciones" mientras el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechazará cuando deba.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="b5e2c-403">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-403">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-404">Para evitar este problema, puede desactivar el almacén de contactos unificado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="b5e2c-405">Para ello, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="b5e2c-406">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="b5e2c-407">Los usuarios de Office Communications Server 2007 R2 alojados localmente no pueden ver el estado de presencia de los usuarios de Skype empresarial online en implementaciones híbridas: híbrida</span><span class="sxs-lookup"><span data-stu-id="b5e2c-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="b5e2c-408">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-408">**Issue:**</span></span>

<span data-ttu-id="b5e2c-409">El problema puede ocurrir en una implementación híbrida cuando usa un director de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="b5e2c-410">El estado de presencia de los usuarios alojados en Skype empresarial online se muestra como una presencia desconocida para los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="b5e2c-411">Además, los usuarios alojados en Skype empresarial online no pueden ver el estado de presencia de los usuarios locales de Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="b5e2c-412">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-412">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-413">Para evitar parcialmente este problema, cambie el servidor principal (msRTCSIP-presencehomeserver) de los usuarios de Skype empresarial online para que apunten a un grupo local de Lync Server 2013 en lugar del Director de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="b5e2c-414">Puede modificar esta configuración en el servidor front-end local.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="b5e2c-415">Esta solución alternativa mostrará correctamente el estado de presencia de los usuarios alojados en Office Communications Server 2007 R2 a usuarios de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="b5e2c-416">Aplicación de grupo de respuesta, aplicación de estacionamiento de llamadas y recogida de llamada grupal</span><span class="sxs-lookup"><span data-stu-id="b5e2c-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="b5e2c-417">Una persona que llama puede oír un segundo de música en espera durante el establecimiento de una llamada con la parte receptora</span><span class="sxs-lookup"><span data-stu-id="b5e2c-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b5e2c-418">La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b5e2c-419">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-419">**Issue:**</span></span>

<span data-ttu-id="b5e2c-420">Cuando se recupera una llamada a través de la recogida de llamadas grupales, es posible que la persona que llama escuche un segundo de la música en espera durante el establecimiento de la llamada con el ampliador de la fiesta.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="b5e2c-421">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-421">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-422">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="b5e2c-423">Un agente de grupo de respuesta puede iniciar sesión y cerrar sesión en una consola del agente de 2010 de Lync Server para Lync Server 2010 solo grupos de agentes formales</span><span class="sxs-lookup"><span data-stu-id="b5e2c-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="b5e2c-424">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-424">**Issue:**</span></span>

<span data-ttu-id="b5e2c-425">Un agente de grupo de respuesta de Lync Server 2013 puede iniciar sesión y cerrar sesión a través de una consola del agente de Lync Server 2010 para Lync Server 2010 solo grupos de agente formal.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="b5e2c-426">En la consola del agente de Lync Server 2010, los usuarios solo pueden ver el grupo de respuesta de Lync Server 2010 al que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="b5e2c-427">No pueden ver ninguno de los grupos de respuesta de Lync Server 2013 a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="b5e2c-428">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-428">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-429">Si el agente de grupo de respuesta es un usuario de Lync Server 2013 y parte de un grupo de agentes formales de Lync Server 2013, el usuario debe tener acceso a la consola del agente de Lync Server 2013 directamente a través de un vínculo Web en un explorador para iniciar y cerrar sesión en los grupos de agentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="b5e2c-430">Un agente de grupo de respuesta 2010 de Lync Server no puede realizar llamadas en nombre de un grupo de respuesta de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5e2c-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="b5e2c-431">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-431">**Issue:**</span></span>

<span data-ttu-id="b5e2c-432">Un usuario de Lync Server 2010 que es un agente de un grupo de respuesta de Lync Server 2013 no puede realizar una llamada en nombre del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="b5e2c-433">El grupo de respuesta de Lync Server 2013 no estará disponible en el cliente de Lync para realizar una llamada.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="b5e2c-434">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-434">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-435">Para solucionar este problema, debe mover el usuario de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="b5e2c-436">Quitar un grupo de respuesta de Lync Server 2010 después de migrarlo a Lync Server 2013 evitará que el grupo de respuesta acepte llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="b5e2c-437">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-437">**Issue:**</span></span>

<span data-ttu-id="b5e2c-438">Si un grupo de respuesta migrado de Lync Server 2010 a Lync Server 2013 se quita de Lync Server 2010 a través del panel de control de Lync Server o del shell de administración de Lync Server, el grupo de respuesta de Lync Server 2013 dejará de recibir las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="b5e2c-439">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-439">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-440">Para solucionar este problema, no quite los grupos de respuesta de Lync Server 2010 que se hayan migrado de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="b5e2c-441">Si el grupo de respuesta ya se ha quitado, debe volver a implementarlo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="b5e2c-442">Cuando un nuevo flujo de trabajo administrado se establece como inactivo cuando se crea, se producirá un error en la implementación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="b5e2c-443">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-443">**Issue:**</span></span>

<span data-ttu-id="b5e2c-444">Cuando se establece un nuevo flujo de trabajo administrado como inactivo cuando se crea, se producirá un error en la implementación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="b5e2c-445">Este problema se produce cuando el flujo de trabajo se establece como inactivo cuando se crea, pero no afecta a un flujo de trabajo que se modifica para establecerlo en inactivo una vez que se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="b5e2c-446">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-446">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-447">Al crear e implementar un flujo de trabajo, establezca el flujo de trabajo como activo y, a continuación, impleméntelo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="b5e2c-448">Una vez que el flujo de trabajo se ha implementado correctamente, el flujo de trabajo se puede editar y establecer en inactivo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="b5e2c-449">Al quitar un grupo de respuesta del grupo de propietarios evitará que el grupo de respuesta del grupo de copias de seguridad acepte llamadas entrantes durante la conmutación por error si el grupo de respuesta se ha importado al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="b5e2c-450">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-450">**Issue:**</span></span>

<span data-ttu-id="b5e2c-451">Si un grupo de respuesta que pertenece al grupo principal se ha importado al grupo de copia de seguridad sin sobrescribir el propietario y el grupo de respuesta se quita del grupo de propietarios, el grupo de respuesta del grupo de copia de seguridad no aceptará ninguna llamada entrante durante la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="b5e2c-452">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-452">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-453">Tendrá que volver a implementar el grupo de respuesta en el grupo primario.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="b5e2c-454">Después, tendrá que exportar la configuración del grupo de respuesta del grupo principal e importarla de nuevo al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="b5e2c-455">También puede volver a crear el grupo de respuesta en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="b5e2c-456">En este caso, el grupo de copia de seguridad será el grupo de propietarios del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="b5e2c-457">No se puede recuperar una llamada estacionada desde la aplicación de estacionamiento de llamadas si la solicitud de recuperación se realiza en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="b5e2c-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="b5e2c-458">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-458">**Issue:**</span></span>

<span data-ttu-id="b5e2c-459">Cuando se cumplan las condiciones siguientes, se producirá un error en una solicitud de recuperación para una llamada en aparcada:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="b5e2c-460">Un agente forma parte de un grupo de respuesta anónimo</span><span class="sxs-lookup"><span data-stu-id="b5e2c-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="b5e2c-461">El agente intenta recuperar una llamada estacionada desde la aplicación de estacionamiento de llamadas a través del grupo de respuesta anónima</span><span class="sxs-lookup"><span data-stu-id="b5e2c-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="b5e2c-462">El agente intenta recuperar la llamada marcando el número de órbita a través de la opción llamar en nombre o a través de la misma opción en el cliente del operador de Lync.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="b5e2c-463">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-463">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-464">No hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="b5e2c-465">La llamada estacionada debe recuperarse sin hacerlo en nombre de un grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="b5e2c-466">Panel de control de Lync Server, Generador de topologías y Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="b5e2c-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="b5e2c-467">Limitaciones de la herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="b5e2c-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b5e2c-468">La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b5e2c-469">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-469">**Issue:**</span></span>

<span data-ttu-id="b5e2c-470">La herramienta de planeación tiene las siguientes limitaciones al planear la implementación:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="b5e2c-471">Hay un máximo de 10 sitios centrales admitidos</span><span class="sxs-lookup"><span data-stu-id="b5e2c-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="b5e2c-472">Cada sitio central puede tener un máximo de 14 sitios de sucursales</span><span class="sxs-lookup"><span data-stu-id="b5e2c-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="b5e2c-473">Cada sitio central puede tener un máximo de 240.000 usuarios</span><span class="sxs-lookup"><span data-stu-id="b5e2c-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="b5e2c-474">Además, la herramienta de planeación no incluye los valores de los siguientes en el cálculo de la topología recomendada:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="b5e2c-475">El número de usuarios alojados en línea</span><span class="sxs-lookup"><span data-stu-id="b5e2c-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="b5e2c-476">El porcentaje de usuarios que están habilitados para la Federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="b5e2c-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="b5e2c-477">Porcentaje de usuarios que usan Lync Web App</span><span class="sxs-lookup"><span data-stu-id="b5e2c-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="b5e2c-478">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-478">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-479">No hay ninguna solución para estos problemas.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-479">There is no workaround for these issues.</span></span> <span data-ttu-id="b5e2c-480">Para obtener más información sobre la herramienta de planeación, consulte [diseño de la topología de Lync Server 2013 mediante la herramienta de planeación](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="b5e2c-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="b5e2c-481">Es posible que la herramienta de planeación no use las direcciones IP definidas previamente para la red perimetral al actualizar las opciones</span><span class="sxs-lookup"><span data-stu-id="b5e2c-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="b5e2c-482">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-482">**Issue:**</span></span>

<span data-ttu-id="b5e2c-483">Después de completar el diseño con la herramienta de planeación, si realiza cambios en las opciones de red perimetral, se pueden agregar direcciones IP adicionales al diseño en lugar de actualizar las direcciones IP existentes.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="b5e2c-484">Esto puede ocurrir si está viendo los detalles del diagrama de red perimetral, seleccione **haga clic aquí para actualizar las opciones**y, a continuación, en el cuadro de diálogo Opciones de configuración, seleccione red perimetral, seleccione **deseo usar los mismos FQDN y direcciones IP, pero puertos diferentes para los servicios perimetrales en mi servidor perimetral**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="b5e2c-485">Aplicar los cambios puede dar lugar a que se agreguen nuevas direcciones IP y servidores perimetrales al diseño.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="b5e2c-486">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-486">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-487">En este momento no hay ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="b5e2c-488">En el panel de control de Lync Server, "mover todos los usuarios al grupo" puede no funcionar según lo esperado</span><span class="sxs-lookup"><span data-stu-id="b5e2c-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="b5e2c-489">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-489">**Issue:**</span></span>

<span data-ttu-id="b5e2c-490">Cuando se usa el panel de control de Lync Server para mover todos los usuarios de un grupo a otro en un entorno complejo de Active Directory, como uno con varios controladores de dominio y dominios primarios y secundarios, se puede devolver un mensaje de error que indica "el usuario especificado es no es un usuario heredado, usa el cmdlet Move-CsUser en su lugar. "</span><span class="sxs-lookup"><span data-stu-id="b5e2c-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="b5e2c-491">Este es el resultado de tiempos de replicación más largos en entornos complejos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="b5e2c-492">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-492">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-493">Para solucionar este problema, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b5e2c-494">Use filtros en el panel de control de Lync Server para buscar usuarios heredados, selecciónelos y, a continuación, use el **comando mover usuarios seleccionados a** la agrupación en lugar de **mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="b5e2c-495">Use el shell de administración de Lync Server para mover usuarios heredados en lotes mediante el uso de cmdlets de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="b5e2c-496">El panel de control de Lync Server deja de funcionar en un entorno de VMware después de que el complemento de explorador Microsoft Silverlight se actualice a la versión 5</span><span class="sxs-lookup"><span data-stu-id="b5e2c-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="b5e2c-497">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-497">**Issue:**</span></span>

<span data-ttu-id="b5e2c-498">Si usa el panel de control de Lync Server en un entorno de VMware, es posible que el panel de control de Lync Server deje de funcionar después de actualizar Silverlight a la versión 5.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="b5e2c-499">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-499">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-500">Para solucionar este problema, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b5e2c-501">Desinstale Silverlight 5 y, a continuación, instale Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)4 desde.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="b5e2c-502">Abra el panel de control de Lync Server desde un equipo que no sea un equipo virtual de VMware.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="b5e2c-503">Para abrir el panel de control de Lync Server desde un equipo remoto, instale las herramientas de administración de Lync Server en el equipo y, a continuación, inicie el panel de control de Lync Server en el menú **Inicio** de Windows.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="b5e2c-504">También puede abrir el panel de control de Lync Server escribiendo la dirección URL en un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="b5e2c-505">La dirección URL será similar a https://\<Front\_-\_end\>Pool FQDN/CSCP.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="b5e2c-506">Un administrador no puede ejecutar el cmdlet Uninstall-csMirrorDB después de quitar la base de datos de reflejo en el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="b5e2c-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="b5e2c-507">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-507">**Issue:**</span></span>

<span data-ttu-id="b5e2c-508">Cuando un administrador deshabilita una base de datos de reflejo en el generador de topología y, a continuación, elimina la base de datos de reflejo en el generador de topología, se muestra un mensaje en la lista de tareas pendientes para que el administrador ejecute el cmdlet **Uninstall-csMirrorDatabase** para quitar reflejo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="b5e2c-509">Cuando el administrador intenta ejecutar el cmdlet, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="b5e2c-510">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-510">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-511">Para quitar la creación de reflejos de SQL de un grupo en el generador de topología, primero debe usar un cmdlet para quitar el reflejo en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="b5e2c-512">Después, podrá usar el Generador de topologías para quitar el reflejo de la topología.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="b5e2c-513">Para quitar el reflejo de SQL Server, use este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="b5e2c-514">Por ejemplo, para quitar el reflejo y colocar las bases de datos de las bases de datos de usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="b5e2c-515">El parámetro *DropExistingDatabasesOnMirror* hace que las bases de datos afectadas se eliminen del reflejo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="b5e2c-516">Luego, para quitar el reflejo de la topología, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="b5e2c-517">En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="b5e2c-518">Desactive habilitar el reflejo de la **tienda SQL** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="b5e2c-519">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="b5e2c-520">Siempre que realice un cambio en una relación de reflejo de la base de datos back-end, debe reiniciar todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="b5e2c-521">Los errores de validación se devuelven en el generador de topología cuando un administrador intenta quitar una implementación con un grupo de servidores front-end que tiene un almacén testigo asociado</span><span class="sxs-lookup"><span data-stu-id="b5e2c-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="b5e2c-522">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-522">**Issue:**</span></span>

<span data-ttu-id="b5e2c-523">Si un administrador intenta usar el comando **quitar implementación** del generador de topología para quitar una implementación que incluye un grupo de servidores front-end con un almacén testigo asociado, se muestra un error de validación en el generador de topologías y la acción no se realizará .</span><span class="sxs-lookup"><span data-stu-id="b5e2c-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="b5e2c-524">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-524">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-525">Para solucionar este problema, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b5e2c-526">Quite el almacén testigo antes de intentar quitar la implementación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="b5e2c-527">Agregue una tienda de testigos para el grupo de servidores front-end y, a continuación, quítela.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="b5e2c-528">La información de implementación del servidor de chat persistente es incoherente entre la herramienta de planificación y el generador de topología</span><span class="sxs-lookup"><span data-stu-id="b5e2c-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="b5e2c-529">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-529">**Issue:**</span></span>

<span data-ttu-id="b5e2c-530">Cuando el 2013 de Lync Server, la herramienta de planeación genera el diagrama de topología del sitio para una implementación de servidor de chat persistente con la recuperación de desastres habilitada, el diagrama de topología del sitio incluye varios sitios (físicos), con servidores de chat persistentes asignados uniformemente en cada uno de ellos. Ubicación.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="b5e2c-531">En el generador de topología, todos los servidores de chat persistentes se representan como pertenecientes a un único sitio (lógico) y se enumeran en el mismo nodo del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="b5e2c-532">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-532">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-533">Por el momento, no tenemos ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="b5e2c-534">El usuario debe analizar el resultado de la herramienta de planeación de la implementación del servidor de chat persistente y modificar el plan para satisfacer sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="b5e2c-535">Local</span><span class="sxs-lookup"><span data-stu-id="b5e2c-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="b5e2c-536">Supervisión</span><span class="sxs-lookup"><span data-stu-id="b5e2c-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="b5e2c-537">El asistente implementar informes de supervisión muestra caracteres incorrectos en determinadas circunstancias al usar la versión de Lync Server de Asia oriental</span><span class="sxs-lookup"><span data-stu-id="b5e2c-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="b5e2c-538">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-538">**Issue:**</span></span>

<span data-ttu-id="b5e2c-539">Al usar una versión de Lync Server 2013 para Asia Oriental (por ejemplo, Chino (simplificado), Chino (tradicional), Japonés o coreano, en un sistema operativo que tiene la configuración regional del sistema no establecida en un idioma de Asia oriental, el Asistente para implementar informes de supervisión le mostrar signos de interrogación u otros caracteres en lugar de mensajes localizados.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="b5e2c-540">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-540">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-541">Para corregir este problema, establezca la configuración regional del sistema operativo y de Lync Server 2013 en el mismo idioma, lo que mostrará todos los mensajes correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="b5e2c-542">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b5e2c-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="b5e2c-543">En algunos casos, el primer elemento de la barra de navegación superior de una página del panel de control de Lync Server desaparece cuando se hace clic en el último elemento de la barra de navegación superior</span><span class="sxs-lookup"><span data-stu-id="b5e2c-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="b5e2c-544">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-544">**Issue:**</span></span>

<span data-ttu-id="b5e2c-545">Hay tres casos conocidos en los que, al hacer clic en el último elemento de la barra de navegación superior de una página del panel de control de Lync Server, el primer elemento de la barra de navegación superior desaparece:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="b5e2c-546">En el francés de la versión, en la página "Féderation et Accès externo", el elemento "Stratégie d'accès extern" desaparecerá cuando se haga clic en "partenaires Fédérés XMPP".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="b5e2c-547">En la versión alemana, en la página "clientes", el elemento "Clientversionskonfiguration" desaparece cuando se hace clic en "Pushbenachrichtigungskonfiguration".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="b5e2c-548">En la versión rusa, en la página "Конфигурация сети", el elemento "Глобально" desaparece cuando se hace clic en "Маршрут региона".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="b5e2c-549">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-549">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-550">Para solucionar este problema, actualice la página del panel de control de Lync Server en el explorador.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="b5e2c-551">La página se cargará en el explorador con todos los elementos de la barra de navegación superior mostrada.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="b5e2c-552">Libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="b5e2c-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="b5e2c-553">La indización de la libreta de direcciones no funciona de la forma esperada en algunos idiomas</span><span class="sxs-lookup"><span data-stu-id="b5e2c-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b5e2c-554">La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b5e2c-555">Si las propiedades de un usuario contienen un campo indizado y ese campo solo contiene caracteres que no se pueden indizar, el usuario no aparecerá en las búsquedas realizadas en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="b5e2c-556">Los siguientes caracteres y configuraciones regionales no se pueden indizar:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="b5e2c-557">Caracteres cirílico, griego y armenio en mayúsculas</span><span class="sxs-lookup"><span data-stu-id="b5e2c-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="b5e2c-558">Caracteres con acento mayúscula</span><span class="sxs-lookup"><span data-stu-id="b5e2c-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="b5e2c-559">Tailandés</span><span class="sxs-lookup"><span data-stu-id="b5e2c-559">Thai</span></span>

  - <span data-ttu-id="b5e2c-560">Lao</span><span class="sxs-lookup"><span data-stu-id="b5e2c-560">Lao</span></span>

  - <span data-ttu-id="b5e2c-561">Myanmar</span><span class="sxs-lookup"><span data-stu-id="b5e2c-561">Myanmar</span></span>

  - <span data-ttu-id="b5e2c-562">Devanagari</span><span class="sxs-lookup"><span data-stu-id="b5e2c-562">Devanagari</span></span>

  - <span data-ttu-id="b5e2c-563">Dígito</span><span class="sxs-lookup"><span data-stu-id="b5e2c-563">Ethiopic</span></span>

  - <span data-ttu-id="b5e2c-564">Tibetano</span><span class="sxs-lookup"><span data-stu-id="b5e2c-564">Tibetan</span></span>

  - <span data-ttu-id="b5e2c-565">Bengalí</span><span class="sxs-lookup"><span data-stu-id="b5e2c-565">Bengali</span></span>

  - <span data-ttu-id="b5e2c-566">Gujarati</span><span class="sxs-lookup"><span data-stu-id="b5e2c-566">Gujarati</span></span>

  - <span data-ttu-id="b5e2c-567">Telugu</span><span class="sxs-lookup"><span data-stu-id="b5e2c-567">Telugu</span></span>

  - <span data-ttu-id="b5e2c-568">Todas las demás secuencias de comandos indios</span><span class="sxs-lookup"><span data-stu-id="b5e2c-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="b5e2c-569">Lync Web App, programador web y componentes Web</span><span class="sxs-lookup"><span data-stu-id="b5e2c-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="b5e2c-570">La reserva de idioma para algunos idiomas en el programador web de Lync, el acceso telefónico, el iniciador de la Unión, la administración de salones de chat persistente y OCTab podría no funcionar de la manera esperada</span><span class="sxs-lookup"><span data-stu-id="b5e2c-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="b5e2c-571">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-571">**Issue:**</span></span>

<span data-ttu-id="b5e2c-572">Al seleccionar una configuración regional neutra en un explorador Web (en Internet Explorer, por ejemplo, el nombre del idioma sin especificación adicional, como " \[noruego\], Bokmål") en lugar de una configuración regional que especifique el idioma, la secuencia de comandos y la configuración regional (como "noruego, Bokmål ( Noruega) \[NB no\]") podría provocar un comportamiento de visualización inesperado para algunos idiomas en el programador web de Lync, acceso telefónico, iniciador de unirse, administración de salones de chat persistente y OCTab.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="b5e2c-573">Por ejemplo, es posible que los usuarios vean la página en inglés cuando se selecciona uno de los siguientes idiomas:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="b5e2c-574">Noruego</span><span class="sxs-lookup"><span data-stu-id="b5e2c-574">Norwegian</span></span>

  - <span data-ttu-id="b5e2c-575">Portugués</span><span class="sxs-lookup"><span data-stu-id="b5e2c-575">Portuguese</span></span>

  - <span data-ttu-id="b5e2c-576">Serbio</span><span class="sxs-lookup"><span data-stu-id="b5e2c-576">Serbian</span></span>

<span data-ttu-id="b5e2c-577">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-577">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-578">Si desea seleccionar un idioma con una configuración regional neutra, asegúrese siempre de agregar el idioma con una configuración regional específica (con el código de la secuencia de comandos o el país) como idioma adicional en la lista de preferencias de idioma del explorador.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="b5e2c-579">Hay compatibilidad limitada con las configuraciones regionales azerí y uzbeko cuando se usa el programador web de Lync, el acceso telefónico, el iniciador de unirse, la administración de salones de chat persistente y OCTab en algunos exploradores Web.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b5e2c-580">La información de esta sección se refiere a las actualizaciones acumulativas de Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b5e2c-581">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-581">**Issue:**</span></span>

<span data-ttu-id="b5e2c-582">Cuando usa Internet Explorer 8 o Internet Explorer 9, y establece el idioma del explorador en Azerí (Latino) o uzbeko (Latino), las páginas de acceso telefónico local y de iniciador de la Unión se mostrarán en inglés o en el idioma preferido establecido en el explorador.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="b5e2c-583">Al usar los exploradores Firefox o Chrome, y establecer el idioma del explorador en Azerí (Latino) o uzbeko (Latino), Lync Web App, Lync web Scheduler y RGS OCTab se mostrará en inglés o en el idioma preferido establecido para el explorador.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="b5e2c-584">La configuración regional uzbeko (Latino) no es compatible con el explorador Safari.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="b5e2c-585">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-585">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-586">No hay solución para estos problemas.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="b5e2c-587">Falta la flecha desplegable de la lista "unirse a la reunión desde" en la versión rumano de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="b5e2c-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="b5e2c-588">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-588">**Issue:**</span></span>

<span data-ttu-id="b5e2c-589">Cuando un usuario que usa la versión rumano de Lync Web App realiza los siguientes pasos, la flecha desplegable no se muestra para unirse a la **reunión** en la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="b5e2c-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="b5e2c-590">Seleccione **recordar mis en este equipo** en la pestaña **General** .</span><span class="sxs-lookup"><span data-stu-id="b5e2c-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="b5e2c-591">Seleccione la pestaña **teléfono** .</span><span class="sxs-lookup"><span data-stu-id="b5e2c-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="b5e2c-592">Haga clic en la lista desplegable para unirse a la **reunión desde**.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="b5e2c-593">Los usuarios no verán una flecha que indica que hay más opciones que la predeterminada de **Lync Web App**, entre las que se incluyen: **no unirse al audio** (en el rumano, "nu se asociaža la aplicación audio") y al **nuevo número**"(en rumano," Număr Nou ").</span><span class="sxs-lookup"><span data-stu-id="b5e2c-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="b5e2c-594">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-594">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-595">Aunque no se muestre la flecha de esta lista desplegable, los usuarios pueden seguir seleccionando la configuración adicional en la lista haciendo clic en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="b5e2c-596">Al usar la versión turca de Lync web Scheduler, no se puede guardar una reunión al usar la opción "las personas que elijo" en "quién es un moderador".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="b5e2c-597">**Vulnerabilidad**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-597">**Issue:**</span></span>

<span data-ttu-id="b5e2c-598">Al crear o editar una reunión en la versión turca del programador web de Lync, no se admite la opción "las personas que elijo" en "¿quién es un moderador".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="b5e2c-599">Cuando esta opción está seleccionada, la reunión no se puede guardar.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="b5e2c-600">En su lugar, aparece un mensaje de error que indica que una o más personas no pueden hacerse moderadores.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="b5e2c-601">**Solución alternativa**</span><span class="sxs-lookup"><span data-stu-id="b5e2c-601">**Workaround:**</span></span>

<span data-ttu-id="b5e2c-602">Para evitar este problema, los usuarios pueden usar la opción predeterminada "personas de mi compañía" o cualquier otra opción, como "solo Organizer" o "todos las personas que no pertenecen a mi compañía".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="b5e2c-603">El organizador puede disminuir o promover a los usuarios a sus roles correctos después de que se hayan unido a la reunión.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="b5e2c-604">Como alternativa, los usuarios que entienden otro idioma pueden cambiar la selección de idioma en el explorador a uno de los otros idiomas admitidos por 43 e intentar usar la opción "las personas que elijas".</span><span class="sxs-lookup"><span data-stu-id="b5e2c-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="b5e2c-605">Tratados</span><span class="sxs-lookup"><span data-stu-id="b5e2c-605">Copyright</span></span>

<span data-ttu-id="b5e2c-606">Este documento es una versión preliminar de un producto de software que puede cambiar sustancialmente antes del lanzamiento comercial final, y es la información confidencial y de propiedad de Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="b5e2c-607">Se revelará conforme a un acuerdo de no divulgación entre el destinatario y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="b5e2c-608">Este documento se proporciona solo a título informativo y Microsoft no otorga garantías expresas ni implícitas en este documento.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="b5e2c-609">La información de este documento, incluidas las direcciones URL y otras referencias a sitios web de Internet, está sujeta a cambios sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="b5e2c-610">El riesgo completo del uso o los resultados del uso de este documento se mantiene con el usuario.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="b5e2c-611">A menos que se indique lo contrario, las empresas, las organizaciones, los productos, los nombres de dominio, las direcciones de correo electrónico, los logotipos, las personas, los lugares y los acontecimientos descritos en los ejemplos son ficticios.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="b5e2c-612">No se pretende indicar ni debe deducirse ninguna asociación con ninguna compañía, organización, producto, nombre de dominio, dirección de correo electrónico, logotipo, persona, lugar o acontecimiento reales.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="b5e2c-613">El cumplimiento de todas las leyes de propiedad intelectual vigentes es responsabilidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="b5e2c-614">Sin limitación de los derechos de propiedad intelectual, ninguna parte de este documento puede ser reproducida, almacenada o introducida en un sistema de recuperación o transmitida de ninguna forma ni por ningún medio (electrónico, mecánico, Fotocopiado, grabación o de otra manera), ni con ningún propósito, sin los permisos expreso y por escrito de Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="b5e2c-615">Microsoft puede tener patentes, solicitudes de patentes, marcas comerciales, derechos de propiedad intelectual u otros derechos de propiedad intelectual sobre los contenidos de este documento.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-615">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="b5e2c-616">A excepción de lo estipulado expresamente en un contrato de licencia por escrito de Microsoft, el suministro de este documento no le otorga ninguna licencia para estas patentes, marcas comerciales, derechos de propiedad intelectual u otros derechos de propiedad intelectual.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-616">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="b5e2c-617">© 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="b5e2c-618">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-618">All rights reserved.</span></span>

<span data-ttu-id="b5e2c-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook y SQL Server son marcas comerciales o marcas comerciales registradas de Microsoft Corporation en los Estados Unidos y en otros países o regiones.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="b5e2c-620">El resto de marcas comerciales pertenecen a sus respectivos dueños.</span><span class="sxs-lookup"><span data-stu-id="b5e2c-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

