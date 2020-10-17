---
title: Notas de la versión de Lync Server 2013
description: Notas de la versión de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fabb0912d7ea3defd91014df732368eced909e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555876"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="6dec6-103">Notas de la versión para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-103">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dec6-104">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="6dec6-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="6dec6-105">Bienvenido a las notas de la versión de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-105">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="6dec6-106">Consulte este archivo para obtener información sobre problemas conocidos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-106">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="6dec6-107">Acerca de este documento</span><span class="sxs-lookup"><span data-stu-id="6dec6-107">About this document</span></span>

<span data-ttu-id="6dec6-108">Este documento contiene información importante que debe conocer antes de implementar y usar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-108">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="6dec6-109">Para obtener más información sobre Lync Server 2013, consulte la documentación de [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="6dec6-109">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="6dec6-110">En este documento se presentan las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="6dec6-110">This document contains the following sections:</span></span>

  - <span data-ttu-id="6dec6-111">Cliente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-111">Lync 2013 client</span></span>

  - <span data-ttu-id="6dec6-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="6dec6-112">Lync Server</span></span>

  - <span data-ttu-id="6dec6-113">Instalación</span><span class="sxs-lookup"><span data-stu-id="6dec6-113">Installation</span></span>

  - <span data-ttu-id="6dec6-114">Movilidad</span><span class="sxs-lookup"><span data-stu-id="6dec6-114">Mobility</span></span>

  - <span data-ttu-id="6dec6-115">Conferencia</span><span class="sxs-lookup"><span data-stu-id="6dec6-115">Conferencing</span></span>

  - <span data-ttu-id="6dec6-116">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="6dec6-116">Enterprise Voice</span></span>

  - <span data-ttu-id="6dec6-117">Presencia</span><span class="sxs-lookup"><span data-stu-id="6dec6-117">Presence</span></span>

  - <span data-ttu-id="6dec6-118">Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="6dec6-118">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="6dec6-119">Panel de control de Lync Server, Generador de topologías y Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="6dec6-119">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="6dec6-120">Localización</span><span class="sxs-lookup"><span data-stu-id="6dec6-120">Localization</span></span>

  - <span data-ttu-id="6dec6-121">Copyright</span><span class="sxs-lookup"><span data-stu-id="6dec6-121">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="6dec6-122">Cliente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-122">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="6dec6-123">La transferencia de un archivo en un mensaje instantáneo produce un error si el archivo está abierto en otra aplicación</span><span class="sxs-lookup"><span data-stu-id="6dec6-123">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="6dec6-124">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-124">**Issue:**</span></span>

<span data-ttu-id="6dec6-125">Si intenta transferir un archivo, como un documento de Word, si lo incluye en un mensaje instantáneo a otro usuario de Lync, la transferencia parecerá que es correcta, pero es posible que, en realidad, no pueda transferir el archivo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-125">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="6dec6-126">Se mostrará un icono para el tipo de archivo en el cliente de Lync, pero el destinatario previsto no podrá abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-126">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="6dec6-127">No se muestra ningún mensaje de error para informarle de que la transferencia no se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6dec6-127">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="6dec6-128">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-128">**Workaround:**</span></span>

<span data-ttu-id="6dec6-129">Para solucionar este problema, cierre el archivo o aplicación abierto que lo tiene abierto antes de intentar transferir el archivo en un mensaje instantáneo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-129">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="6dec6-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="6dec6-130">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="6dec6-131">Si se produce un error en la replicación de datos del servicio de almacenamiento de Lync Server, los administradores deberán comprobar los contadores de rendimiento de los elementos de la cola del servicio de almacenamiento obsoleto</span><span class="sxs-lookup"><span data-stu-id="6dec6-131">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="6dec6-132">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-132">**Issue:**</span></span>

<span data-ttu-id="6dec6-133">El servicio de almacenamiento de Lync Server usa Windows fabric para la replicación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-133">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="6dec6-134">Si los datos se eliminan en un servidor front-end principal, pero se produce un error en la eliminación de un servidor front-end secundario (por ejemplo, si hay un apagado inesperado o un error en el servidor front-end), los datos pueden quedar "huérfanos".</span><span class="sxs-lookup"><span data-stu-id="6dec6-134">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="6dec6-135">Los datos huérfanos pueden provocar la degradación del rendimiento y la pérdida de espacio en la unidad.</span><span class="sxs-lookup"><span data-stu-id="6dec6-135">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="6dec6-136">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-136">**Workaround:**</span></span>

<span data-ttu-id="6dec6-137">Para solucionar este problema, si se generan los eventos \_ LYSS \_ espacio de base de datos \_ \_ (ID = 32058) y LYSS \_ \_ espacio de base de datos \_ usado \_ crítico (ID = 32059) en el registro de eventos, los administradores deben comprobar el contador de rendimiento en el servidor front-end en **LS: LYSS-API del servicio** de almacenamiento con el nombre **LYSS-Current número de elementos de cola obsoletos**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-137">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="6dec6-138">Si este contador de rendimiento tiene un valor alto (por ejemplo, mayor que 50000), el administrador debe ejecutar la herramienta de CleanuUpStorageServiceData.exe en el kit de recursos de Lync Server 2013, que eliminará todos los datos huérfanos del grupo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-138">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="6dec6-139">Para obtener más información sobre la herramienta, consulte la documentación del kit de recursos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-139">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="6dec6-140">Siempre que se cambia la configuración de la dirección IP de un servidor o grupo de servidores, es necesario reiniciar los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-140">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="6dec6-141">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-141">**Issue:**</span></span>

<span data-ttu-id="6dec6-142">Cuando se cambia la configuración de la dirección IP para una implementación de Lync Server 2013, como cambiar de IPv4 a pila dual o de pila dual a IPv6, no todos los componentes del servidor toman el cambio de configuración hasta que se reinicien los servicios.</span><span class="sxs-lookup"><span data-stu-id="6dec6-142">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="6dec6-143">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-143">**Workaround:**</span></span>

<span data-ttu-id="6dec6-144">Para solucionar este problema, reinicie los servicios de Lync Server después de cambiar la configuración de la dirección IP de la implementación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-144">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="6dec6-145">Para ello, ejecute los siguientes cmdlets en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6dec6-145">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="6dec6-146">El cmdlet de transacciones sintéticas de conferencias de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-146">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="6dec6-147">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-147">**Issue:**</span></span>

<span data-ttu-id="6dec6-148">El cmdlet **Test-CsDialInConferencing** de la transacción sintética de conferencia de acceso telefónico local ya no está disponible en el módulo de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-148">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="6dec6-149">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-149">**Workaround:**</span></span>

<span data-ttu-id="6dec6-150">El cmdlet de transacciones sintéticas de conferencia de acceso telefónico local **Test-CsDialInConferencing** solo se puede usar en una empresa de forma interna.</span><span class="sxs-lookup"><span data-stu-id="6dec6-150">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="6dec6-151">Los administradores pueden seguir usando el cmdlet en el shell de administración de Lync Server para fines de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="6dec6-151">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="6dec6-152">Si es necesario, una empresa también puede desarrollar un módulo de administración privado para ejecutar el cmdlet de forma interna.</span><span class="sxs-lookup"><span data-stu-id="6dec6-152">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="6dec6-153">El servicio de registro centralizado se detiene si el tráfico de red se interrumpe cuando los archivos de registro se copian a un recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="6dec6-153">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="6dec6-154">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-154">**Issue:**</span></span>

<span data-ttu-id="6dec6-155">Cuando el servicio de registro centralizado se configura para usar una ruta de red (el valor del parámetro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** es una ruta UNC válida), los archivos de registro almacenados en caché se copian al recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="6dec6-155">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="6dec6-156">Si se produce una interrupción en el tráfico de red mientras se copian los archivos, se generará una excepción que provocará que el servicio de registro centralizado se detenga.</span><span class="sxs-lookup"><span data-stu-id="6dec6-156">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="6dec6-157">El servicio está configurado para reiniciarse automáticamente hasta tres veces y, por lo tanto, se recuperará de las primeras tres excepciones.</span><span class="sxs-lookup"><span data-stu-id="6dec6-157">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="6dec6-158">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-158">**Workaround:**</span></span>

<span data-ttu-id="6dec6-159">No existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-159">There is no workaround for this issue.</span></span> <span data-ttu-id="6dec6-160">Para identificar el problema, supervise el identificador de evento 7031 en el registro de eventos de la "Administrador de control de servicios" que registra cuando el servicio "agente de servicio de registro centralizado de Lync Server" ha finalizado de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="6dec6-160">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="6dec6-161">Si esto sucede más de tres veces, reinicie el servicio manualmente con el cmdlet **Start-CsWindowService**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-161">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="6dec6-162">Los elementos de la cola del servicio de almacenamiento deben importarse manualmente</span><span class="sxs-lookup"><span data-stu-id="6dec6-162">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="6dec6-163">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-163">**Issue:**</span></span>

<span data-ttu-id="6dec6-164">Lync Server 2013 almacena datos sobre conferencias y mensajería instantánea, como mensajes archivados y registro detallado de llamadas (CDR), en una base de datos en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6dec6-164">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="6dec6-165">Los datos se almacenan en la base de datos mientras se procesan antes de que se entreguen al destino previsto.</span><span class="sxs-lookup"><span data-stu-id="6dec6-165">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="6dec6-166">Para mejorar el rendimiento, Lync Server 2013 exporta periódicamente los elementos de la cola de la base de datos local que no se procesan durante un período de tiempo prolongado, y los guarda en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="6dec6-166">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="6dec6-167">Si el almacén de archivos no está disponible, los elementos se almacenan en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6dec6-167">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="6dec6-168">La misma operación se realiza para evitar la pérdida de datos durante la conmutación por error del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6dec6-168">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="6dec6-169">Durante la operación de exportación, el servicio de almacenamiento de Lync Server registra todas las fases en el registro de eventos con los identificadores de evento de 32075 (se inicia la operación de vaciado completa), 32076 (vaciado completo), 32082 (se inicia el vaciado de nivel de mantenimiento), 32083 (se completa el vaciado de nivel de mantenimiento), 32089 (vaciado debido a</span><span class="sxs-lookup"><span data-stu-id="6dec6-169">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="6dec6-170">Estos datos no se importarán automáticamente al sistema para ser procesados y entregados a su destino final (SQL Server o Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="6dec6-170">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="6dec6-171">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-171">**Workaround:**</span></span>

<span data-ttu-id="6dec6-172">Para importar los datos al sistema, los administradores deberán usar la herramienta ImportStorageServiceData del kit de recursos de Lync Server, que agregará los datos de vuelta al sistema para que se procesen y entreguen a su destino final.</span><span class="sxs-lookup"><span data-stu-id="6dec6-172">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="6dec6-173">Se producirá un error en las búsquedas de consulta Web de la libreta de direcciones si el valor predeterminado de UseNormalizationRules se cambia a false.</span><span class="sxs-lookup"><span data-stu-id="6dec6-173">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="6dec6-174">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-174">**Issue:**</span></span>

<span data-ttu-id="6dec6-p112">Si el valor predeterminado de UseNormalizationRules se cambia a False, se producirá un error en las búsquedas de la consulta web de la libreta de direcciones. Tras modificar el valor predeterminado, los usuarios del cliente de Lync no podrán usar la consulta web de la libreta de direcciones de Lync para buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p112">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail. After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="6dec6-177">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-177">**Workaround:**</span></span>

<span data-ttu-id="6dec6-178">Si el valor predeterminado de UseNormalizationRules se establece en false para que los usuarios puedan usar los números de teléfono definidos en los servicios de dominio de Active Directory sin que Lync Server 2013 aplique reglas de normalización, haga lo siguiente para solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="6dec6-178">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="6dec6-179">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-179">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6dec6-180">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6dec6-180">Do one of the following:</span></span>
    
      - <span data-ttu-id="6dec6-181">Si la implementación incluye solo servidores de Lync Server 2013, ejecute el siguiente cmdlet en el nivel global para cambiar los valores de UseNormalizationRules y IgnoreGenericRules a true:</span><span class="sxs-lookup"><span data-stu-id="6dec6-181">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="6dec6-182">Si su implementación incluye una combinación de Lync Server 2013 y Lync Server 2010 u Office Communications Server 2007 R2, ejecute el siguiente cmdlet y asígnelo a cada grupo de servidores de Lync Server 2013 en la topología:</span><span class="sxs-lookup"><span data-stu-id="6dec6-182">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="6dec6-183">Espere hasta que la replicación de CMS se complete en todos los grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="6dec6-183">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="6dec6-184">Modifique el archivo de reglas de normalización del teléfono de su implementación para borrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="6dec6-184">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="6dec6-185">El archivo se encuentra en el recurso compartido de archivos de cada grupo de servidores de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-185">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="6dec6-186">Si el archivo no está presente, cree un archivo vacío denominado "Rules.txt de \_ normalización de números de teléfono de la empresa \_ \_ \_ ".</span><span class="sxs-lookup"><span data-stu-id="6dec6-186">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="6dec6-187">Espere varios minutos hasta que todos los grupos de servidores front-end lean los nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="6dec6-187">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="6dec6-188">Ejecute el siguiente cmdlet en cada grupo de servidores de Lync Server 2013 de la implementación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-188">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="6dec6-189">El evento de error del servidor de libreta de direcciones 21054 se genera una vez al día para cada grupo de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-189">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="6dec6-190">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-190">**Issue:**</span></span>

<span data-ttu-id="6dec6-191">El servidor de la libreta de direcciones 2013 de Lync Server generará el evento de error 21054 una vez al día al realizar el mantenimiento diario.</span><span class="sxs-lookup"><span data-stu-id="6dec6-191">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="6dec6-192">El error también se genera cada vez que un administrador ejecuta el cmdlet **Update-csAddressBook** , incluso cuando la actualización se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6dec6-192">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="6dec6-193">Sin embargo, este evento de error puede omitirse con seguridad cuando la actualización se haya realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6dec6-193">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="6dec6-194">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-194">**Workaround:**</span></span>

<span data-ttu-id="6dec6-195">Cuando detecta este evento de error, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6dec6-195">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="6dec6-196">Si el cmdlet informa de que no hay objetos no indizados o abandonados, el evento de error 21054 se puede omitir sin problemas.</span><span class="sxs-lookup"><span data-stu-id="6dec6-196">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="6dec6-197">Además, se debe desactivar el indicador clave de estado (KHI) de los usuarios de libreta de direcciones indizados correctamente en System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6dec6-197">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="6dec6-198">Las solicitudes pueden producir un error cuando se configura IPv6 en un grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="6dec6-198">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="6dec6-199">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-199">**Issue:**</span></span>

<span data-ttu-id="6dec6-200">Cuando se configura IPv6 en un grupo de servidores perimetrales, es posible que algunas solicitudes enviadas al grupo presenten errores.</span><span class="sxs-lookup"><span data-stu-id="6dec6-200">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="6dec6-201">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-201">**Workaround:**</span></span>

<span data-ttu-id="6dec6-202">Para solucionar este problema, no configure IPv6 en un grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="6dec6-202">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="6dec6-203">El cmdlet Invoke-csPoolFailback puede fallar durante la conmutación por recuperación del grupo</span><span class="sxs-lookup"><span data-stu-id="6dec6-203">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="6dec6-204">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-204">**Issue:**</span></span>

<span data-ttu-id="6dec6-205">Al intentar la conmutación por recuperación de un grupo de servidores, el cmdlet **invoke-csPoolFailback** puede generar un error que indica que no se pudo al completar el proceso de hidratación tras varios intentos.</span><span class="sxs-lookup"><span data-stu-id="6dec6-205">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="6dec6-206">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-206">**Workaround:**</span></span>

<span data-ttu-id="6dec6-p115">Para solucionar este problema, ejecute el cmdlet de nuevo y espere hasta que se complete correctamente. Tenga en cuenta que el proceso de conmutación por recuperación puede tardar varios minutos en completarse. Puede tardar hasta 60 minutos para un grupo de servidores con 20.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p115">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds. Note that the failback process can take several minutes to complete. It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="6dec6-210">Se pueden producir pérdidas de datos cuando se agrega un servidor front-end a un grupo ya establecido: híbrido, Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="6dec6-210">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="6dec6-211">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-211">**Issue:**</span></span>

<span data-ttu-id="6dec6-212">Este problema se puede producir en un entorno en el que un grupo tiene más de un servidor front-end y se reinicia uno de los servidores front-end, o bien se agrega un nuevo servidor front-end que no formaba parte del grupo anterior.</span><span class="sxs-lookup"><span data-stu-id="6dec6-212">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="6dec6-p116">Los usuarios que tienen datos para archivar pueden sufrir pérdidas de datos hasta que se establezca una distribución estable del archivado para el grupo de servidores. Este período de posibles pérdidas de datos está limitado a 15 minutos para las conversaciones entre personas y a 30 minutos para las conferencias.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p116">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool. This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="6dec6-215">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-215">**Workaround:**</span></span>

<span data-ttu-id="6dec6-216">Al realizar el mantenimiento, en lugar de iniciar los servidores front-end en el grupo de uno en uno, debe realizar una conmutación por error del grupo a otro grupo y, a continuación, realizar las tareas de mantenimiento en los servidores.</span><span class="sxs-lookup"><span data-stu-id="6dec6-216">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="6dec6-217">También puede interrumpir el servicio antes de realizar las tareas de mantenimiento y luego restaurar su disponibilidad una vez completadas las tareas.</span><span class="sxs-lookup"><span data-stu-id="6dec6-217">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="6dec6-218">Los administradores no pueden obtener el número de licencias con el cmdlet Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="6dec6-218">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="6dec6-219">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-219">**Issue:**</span></span>

<span data-ttu-id="6dec6-220">Los administradores no pueden obtener el uso exacto de licencias de cliente con el cmdlet **Get-CsClientAccessLicense**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-220">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="6dec6-221">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-221">**Workaround:**</span></span>

<span data-ttu-id="6dec6-222">Para comprobar el tipo de licencia del servidor, puede ejecutar el cmdlet **Get-CsService** para recuperar los nombres de dominio completos (FQDN) de todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="6dec6-222">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="6dec6-223">Si el FQDN del servidor front-end es el mismo que el FQDN de la base de datos back-end, la licencia es una licencia de Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6dec6-223">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="6dec6-224">En caso contrario, la licencia será de un servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="6dec6-224">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="6dec6-225">El número de licencias de cliente no se ha notificado con precisión</span><span class="sxs-lookup"><span data-stu-id="6dec6-225">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="6dec6-226">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-226">**Issue:**</span></span>

<span data-ttu-id="6dec6-227">Al determinar el número de licencias de cliente, es posible que se produzcan las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="6dec6-227">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="6dec6-228">**Número impreciso de licencias para usuarios móviles**</span><span class="sxs-lookup"><span data-stu-id="6dec6-228">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="6dec6-p119">El número de licencias se basa en el número de direcciones IP únicas para los usuarios de dispositivos. El número de licencias estará limitado de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="6dec6-p119">The license count is based on the number of unique IP addresses for device-based users. The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="6dec6-231">El número de licencias será superior al real si la dirección IP del usuario se modifica durante las sesiones de Lync.</span><span class="sxs-lookup"><span data-stu-id="6dec6-231">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="6dec6-232">Esto puede ocurrir cuando un usuario se conecta a Lync Server desde más de una ubicación con un cliente de escritorio.</span><span class="sxs-lookup"><span data-stu-id="6dec6-232">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="6dec6-233">El número de licencias será inferior al real si un usuario se conecta a un cliente móvil, ya que la dirección IP del dispositivo no se puede determinar.</span><span class="sxs-lookup"><span data-stu-id="6dec6-233">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="6dec6-234">**Las licencias se cuentan dos veces para las llamadas de la red telefónica conmutada (RTC) al cliente de Lync, las llamadas del cliente de Lync a las líneas RTC y las llamadas de Lync desviadas a las líneas RTC**</span><span class="sxs-lookup"><span data-stu-id="6dec6-234">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="6dec6-p121">En los siguientes escenarios, se contarán dos licencias adicionales en lugar de una, porque se considera tanto el número de teléfono como el usuario de Lync para determinar el número de licencias usadas. Para obtener datos precisos de las licencias, quite manualmente las licencias generadas por el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p121">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used. To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="6dec6-237">Una llamada telefónica RTC a Lync</span><span class="sxs-lookup"><span data-stu-id="6dec6-237">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="6dec6-238">Una llamada de Lync a una línea RTC</span><span class="sxs-lookup"><span data-stu-id="6dec6-238">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="6dec6-p122">Una llamada RTC a Lync y el posterior desvío de la llamada de Lync a una línea RTC. Se contará una de las líneas RTC.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p122">A PSTN call to Lync, and then Lync forwards the call to a PSTN line. One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="6dec6-241">**No se contará ninguna licencia para un teléfono Lync conectado**</span><span class="sxs-lookup"><span data-stu-id="6dec6-241">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="6dec6-242">Cuando un usuario usa un teléfono certificado para Lync, si el teléfono inicia sesión y permanece conectado, lo que conserva su estado de inicio de sesión, no se considerará que el teléfono usa una licencia si la consulta de las licencias se realiza después del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6dec6-242">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="6dec6-243">**Licencias consideradas para teléfonos RTC que se unen a conferencias**</span><span class="sxs-lookup"><span data-stu-id="6dec6-243">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="6dec6-p123">Cuando un usuario se une a una conferencia con un teléfono RTC, se contará erróneamente una licencia por unirse a la conferencia. Sin embargo, no se necesita ninguna licencia para unirse a una conferencia con un teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p123">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference. However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="6dec6-246">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-246">**Workaround:**</span></span>

1.  <span data-ttu-id="6dec6-247">**Número impreciso de licencias para usuarios móviles**</span><span class="sxs-lookup"><span data-stu-id="6dec6-247">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="6dec6-248">Puede identificar manualmente las direcciones IP que pertenecen al mismo dispositivo y luego quitar una de ellas del número de licencias.</span><span class="sxs-lookup"><span data-stu-id="6dec6-248">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="6dec6-249">No existe ninguna solución para este problema con los dispositivos móviles que se conectan a un cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="6dec6-249">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="6dec6-250">**Las licencias se cuentan dos veces para las llamadas RTC al cliente de Lync, las llamadas del cliente de Lync a las líneas RTC y las llamadas de Lync desviadas a las líneas RTC**</span><span class="sxs-lookup"><span data-stu-id="6dec6-250">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="6dec6-251">Deberá identificar manualmente el número de teléfono RTC y quitar el número de licencias generado para él.</span><span class="sxs-lookup"><span data-stu-id="6dec6-251">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="6dec6-252">**No se contará ninguna licencia para un teléfono Lync conectado**</span><span class="sxs-lookup"><span data-stu-id="6dec6-252">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="6dec6-253">Puede configurar el teléfono Lync para que cierre la sesión y vuelva a iniciarla, a un intervalo regular, por ejemplo, cada tres meses.</span><span class="sxs-lookup"><span data-stu-id="6dec6-253">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="6dec6-254">**Licencias consideradas para teléfonos RTC que se unen a conferencias**</span><span class="sxs-lookup"><span data-stu-id="6dec6-254">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="6dec6-255">Puede identificar manualmente el número de teléfono RTC que se usa para unirse a la conferencia y quitar la licencia generada por el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="6dec6-255">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="6dec6-256">El panel de control de Lync Server deja de funcionar en un entorno VMware después de actualizar a Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="6dec6-256">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="6dec6-257">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-257">**Issue:**</span></span>

<span data-ttu-id="6dec6-258">Si usa el panel de control de Lync Server en un entorno de VMware, el panel de control de Lync Server puede dejar de funcionar después de actualizar Microsoft Silverlight a la versión 5.</span><span class="sxs-lookup"><span data-stu-id="6dec6-258">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="6dec6-259">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-259">**Workaround:**</span></span>

<span data-ttu-id="6dec6-260">Para solucionar este problema, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6dec6-260">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="6dec6-261">Desinstalar Silverlight 5 e instalar Silverlight 4 desde [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) .</span><span class="sxs-lookup"><span data-stu-id="6dec6-261">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="6dec6-262">Obtenga acceso al panel de control de Lync Server desde un equipo que no sea un equipo virtual VMware.</span><span class="sxs-lookup"><span data-stu-id="6dec6-262">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="6dec6-263">Para ello, puede iniciar el panel de control de Lync Server desde el menú **Inicio** de Windows en el servidor, si las herramientas de administración de Lync Server están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-263">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="6dec6-264">También puede obtener acceso al panel de control de Lync Server mediante un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="6dec6-264">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="6dec6-265">La dirección URL será similar a https:// \<frontend\_pool\_fqdn\> /CSCP.</span><span class="sxs-lookup"><span data-stu-id="6dec6-265">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="6dec6-266">La información del usuario en el servicio de libreta de direcciones no se actualiza después de modificar el nombre distintivo del usuario en Active Directory</span><span class="sxs-lookup"><span data-stu-id="6dec6-266">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="6dec6-267">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-267">**Issue:**</span></span>

<span data-ttu-id="6dec6-268">Si se cambia el nombre distintivo de un usuario (también conocido como DN) en servicios de dominio de Active Directory, los cambios adicionales no se actualizarán en el servicio de libreta de direcciones (ABS).</span><span class="sxs-lookup"><span data-stu-id="6dec6-268">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="6dec6-269">Esto no afecta el inicio de sesión ni la presencia del usuario, pero impedirá la comunicación del usuario si también se modifica la dirección SIP, ya que las búsquedas devolverán una dirección SIP obsoleta.</span><span class="sxs-lookup"><span data-stu-id="6dec6-269">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="6dec6-270">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-270">**Workaround:**</span></span>

<span data-ttu-id="6dec6-p126">Para solucionar este problema, no modifique el DN de un usuario. Si revierte el DN del usuario al valor anterior, las actualizaciones se reflejarán en el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p126">To work around this issue, do not change a user’s DN. If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="6dec6-273">Instalación</span><span class="sxs-lookup"><span data-stu-id="6dec6-273">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="6dec6-274">El uso de caracteres que no sean ASCII puede dar lugar a que no se inicie Lync Server</span><span class="sxs-lookup"><span data-stu-id="6dec6-274">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="6dec6-275">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-275">**Issue:**</span></span>

<span data-ttu-id="6dec6-276">Se producirá un error en la instalación si el nombre de la carpeta de destino incluye caracteres que no sean ASCII (como Unicode, juego de caracteres de doble byte (DBCS), UTF-8 y UTF-16).</span><span class="sxs-lookup"><span data-stu-id="6dec6-276">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="6dec6-277">Además, el programa de instalación puede tener éxito, pero el servidor no se iniciará si los caracteres que no son ASCII están incluidos en alguna de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6dec6-277">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="6dec6-278">Nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="6dec6-278">Computer name</span></span>

  - <span data-ttu-id="6dec6-279">Nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="6dec6-279">Domain name</span></span>

  - <span data-ttu-id="6dec6-280">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="6dec6-280">User name</span></span>

  - <span data-ttu-id="6dec6-281">URI del SIP del usuario</span><span class="sxs-lookup"><span data-stu-id="6dec6-281">User SIP URI</span></span>

  - <span data-ttu-id="6dec6-282">Nombre de la cuenta de servicio</span><span class="sxs-lookup"><span data-stu-id="6dec6-282">Service account name</span></span>

<span data-ttu-id="6dec6-283">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-283">**Workaround:**</span></span>

<span data-ttu-id="6dec6-284">Use solo caracteres ASCII en el nombre de la carpeta de destino, el nombre del equipo, el nombre del dominio, el nombre de usuario, el URI del SIP del usuario y los nombres de cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="6dec6-284">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="6dec6-285">La revisión de "los daños en el montón se produce cuando un módulo llama al método al InsertEntityBody en IIS 7,5" debe estar instalado antes de instalar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-285">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="6dec6-286">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-286">**Issue:**</span></span>

<span data-ttu-id="6dec6-287">La revisión de "los daños en el montón se produce cuando un módulo llama al método al InsertEntityBody en IIS 7,5" ( [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) ), que se describe en el artículo 264886 () de Microsoft Knowledge base [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) , debe estar instalado antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-287">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="6dec6-288">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-288">**Workaround:**</span></span>

<span data-ttu-id="6dec6-289">Descargue e instale la revisión desde el centro de descarga de Microsoft en [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) .</span><span class="sxs-lookup"><span data-stu-id="6dec6-289">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="6dec6-290">Lync Server 2013 no se puede instalar en la versión de Windows Server 2012 OS RTM de ITA</span><span class="sxs-lookup"><span data-stu-id="6dec6-290">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="6dec6-291">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-291">**Issue:**</span></span>

<span data-ttu-id="6dec6-292">La instalación de Lync Server 2013 no funciona en ITA Windows Server 2012 debido a un error en la instalación de Windows fabric.</span><span class="sxs-lookup"><span data-stu-id="6dec6-292">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="6dec6-p128">Se produce un error al instalar Windows Fabric porque se crean seguimientos de tejidos con el formato de hora HH:MM:SS. Sin embargo, en ITA Windows Server, el formato de hora es HH.MM.SS.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p128">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS. However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="6dec6-295">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-295">**Workaround:**</span></span>

<span data-ttu-id="6dec6-296">Para solucionar este problema, actualice el registro del sistema antes de instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-296">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="6dec6-297">La clave del registro que debe actualizarse es: \_ usuarios HKEY \\ . \\Panel de control \\ predeterminado \\ sTimeFormat.</span><span class="sxs-lookup"><span data-stu-id="6dec6-297">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="6dec6-298">Cambie el valor de sTimeFormat a HH: mm: SS mediante la interfaz de línea de comandos de Windows PowerShell como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6dec6-298">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="6dec6-299">Inicie Windows PowerShell y ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6dec6-299">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="6dec6-300">Para ver el valor actual, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6dec6-300">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="6dec6-301">Anote el valor actual de sTimeFormat para poder restaurarlo una vez finalizada la instalación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-301">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="6dec6-302">Para establecer un nuevo valor, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6dec6-302">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="6dec6-303">Una vez instalado Lync Server 2013 correctamente, restaure el valor original de la sTimeFormat mediante la ejecución del siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6dec6-303">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="6dec6-304">Set-ItemProperty $a sTimeFormat-Value "<Value se anota en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="6dec6-304">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="6dec6-305">anterior> "</span><span class="sxs-lookup"><span data-stu-id="6dec6-305">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="6dec6-306">Movilidad</span><span class="sxs-lookup"><span data-stu-id="6dec6-306">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="6dec6-307">Problemas para clientes móviles durante el proceso de conmutación por error del servidor</span><span class="sxs-lookup"><span data-stu-id="6dec6-307">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="6dec6-308">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-308">**Issue:**</span></span>

<span data-ttu-id="6dec6-309">Cuando se produce un error en un Lync Server y se inicia el proceso de conmutación por error, los siguientes problemas pueden afectar a los usuarios de clientes móviles:</span><span class="sxs-lookup"><span data-stu-id="6dec6-309">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="6dec6-310">No se realiza ninguna llamada entrante de Lync ni señala hasta 10 minutos después de que se inicie la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="6dec6-310">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="6dec6-311">No se pueden aceptar las solicitudes entrantes de chat</span><span class="sxs-lookup"><span data-stu-id="6dec6-311">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="6dec6-312">No se pueden unir reuniones si el servidor con error es el servidor principal del usuario</span><span class="sxs-lookup"><span data-stu-id="6dec6-312">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="6dec6-313">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-313">**Workaround:**</span></span>

<span data-ttu-id="6dec6-314">No existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-314">There is no workaround for this issue.</span></span> <span data-ttu-id="6dec6-315">La funcionalidad normal se restaurará una vez que se haya completado el proceso de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="6dec6-315">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="6dec6-316">Si un usuario móvil rechaza una llamada entrante desde otro extremo de Lync, la llamada se muestra como una conversión perdida en clientes móviles de Lync</span><span class="sxs-lookup"><span data-stu-id="6dec6-316">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="6dec6-317">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-317">**Issue:**</span></span>

<span data-ttu-id="6dec6-318">Si un usuario móvil rechaza una llamada entrante y la llamada se originó en otro extremo de Lync, la llamada se muestra como una conversación perdida en el cliente móvil de Lync, en lugar de una llamada en la lista de llamadas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-318">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="6dec6-319">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-319">**Workaround:**</span></span>

<span data-ttu-id="6dec6-320">No existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-320">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="6dec6-321">Es posible que el cliente móvil no muestre el nombre para mostrar de un contacto federado al buscar contactos</span><span class="sxs-lookup"><span data-stu-id="6dec6-321">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="6dec6-322">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-322">**Issue:**</span></span>

<span data-ttu-id="6dec6-323">Es posible que el nombre para mostrar de los contactos federados no se muestre en algunos escenarios, como cuando se busca un contacto federado en la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="6dec6-323">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="6dec6-324">Esto puede ocurrir cuando no hay ninguna suscripción de presencia activa para el contacto desde el cliente móvil de Lync.</span><span class="sxs-lookup"><span data-stu-id="6dec6-324">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="6dec6-325">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-325">**Workaround:**</span></span>

<span data-ttu-id="6dec6-326">No existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-326">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="6dec6-327">En el cliente móvil, la información de invite y timestamp no se encuentra en una conversación perdida que es una invitación a una conferencia</span><span class="sxs-lookup"><span data-stu-id="6dec6-327">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="6dec6-328">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-328">**Issue:**</span></span>

<span data-ttu-id="6dec6-329">En el cliente móvil, cuando una conversación perdida es una invitación a una conferencia, falta la información de la invitación y la marca de hora del mensaje de conversación perdido.</span><span class="sxs-lookup"><span data-stu-id="6dec6-329">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="6dec6-330">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-330">**Workaround:**</span></span>

<span data-ttu-id="6dec6-331">No existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-331">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="6dec6-332">Los usuarios de clientes móviles que realizan llamadas mediante VoIP no pueden dejar correo de voz para los usuarios cuyo correo de voz está configurado en Exchange 2010 o versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="6dec6-332">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="6dec6-333">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-333">**Issue:**</span></span>

<span data-ttu-id="6dec6-334">Si un usuario de cliente móvil usa VoIP para realizar llamadas, el usuario no podrá dejar mensajes de correo de voz para usuarios configurados para usar el correo de voz en Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6dec6-334">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="6dec6-335">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-335">**Workaround:**</span></span>

<span data-ttu-id="6dec6-336">Para solucionar este problema, use Exchange 2010 con SP1 o una versión posterior de Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-336">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="6dec6-337">Cuando se usa Block con URL para la configuración de versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto</span><span class="sxs-lookup"><span data-stu-id="6dec6-337">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="6dec6-338">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-338">**Issue:**</span></span>

<span data-ttu-id="6dec6-339">Cuando se usa **Block con URL** para la configuración de versión de cliente en clientes móviles, se puede mostrar un mensaje de error incorrecto cuando la versión de cliente no es compatible.</span><span class="sxs-lookup"><span data-stu-id="6dec6-339">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="6dec6-340">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-340">**Workaround:**</span></span>

<span data-ttu-id="6dec6-341">Para solucionar este problema, configure la versión de cliente para que use **Block** en lugar de **Block with URL**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-341">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="6dec6-342">Conferencia</span><span class="sxs-lookup"><span data-stu-id="6dec6-342">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="6dec6-343">El software antivirus que se ejecuta en los servidores front-end de Lync Server 2013 puede provocar el reciclaje del dominio de aplicación, lo que interrumpe temporalmente el servicio para los clientes de Lync Mobile App 2013, Lync Mobile 2010 y Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-343">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="6dec6-344">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-344">**Issue:**</span></span>

<span data-ttu-id="6dec6-345">El software antivirus puede desencadenar reinicios de dominio de aplicación, lo que puede dar como resultado aplicaciones de cliente de la API Web de Lync Mobility Service 2013 y comunicaciones unificadas (UC) (Lync Web App 2013, Lync Mobile 2010 y Lync Mobile 2013) para perder su estado.</span><span class="sxs-lookup"><span data-stu-id="6dec6-345">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="6dec6-346">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-346">**Workaround:**</span></span>

<span data-ttu-id="6dec6-347">Para solucionar este problema, excluya las carpetas que contienen componentes web y .NET Framework del análisis antivirus.</span><span class="sxs-lookup"><span data-stu-id="6dec6-347">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="6dec6-348">Para obtener más información, consulte el artículo 312592 de Microsoft Knowledge base, "PRB: Random Application restarts with ' Application is reiniciating ' error en ASP.NET, en [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) .</span><span class="sxs-lookup"><span data-stu-id="6dec6-348">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="6dec6-349">Se deben excluir las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="6dec6-349">The following folders should be excluded:</span></span>

  - <span data-ttu-id="6dec6-350">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ MCX \\ ext</span><span class="sxs-lookup"><span data-stu-id="6dec6-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="6dec6-351">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ MCX \\ int</span><span class="sxs-lookup"><span data-stu-id="6dec6-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="6dec6-352">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ Ucwa \\ int</span><span class="sxs-lookup"><span data-stu-id="6dec6-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="6dec6-353">% ProgramFiles% de \\ componentes Web de Microsoft Lync Server 2013 de \\ \\ Ucwa \\ ext</span><span class="sxs-lookup"><span data-stu-id="6dec6-353">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="6dec6-354">% WINDIR% \\ Microsoft.net \\ Framework64 \\ v 4.0.30319 \\ config</span><span class="sxs-lookup"><span data-stu-id="6dec6-354">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="6dec6-355">Los controles ActiveX o la compatibilidad con XMLHTTP nativo deben estar habilitados en Windows Internet Explorer para unirse correctamente a las conferencias.</span><span class="sxs-lookup"><span data-stu-id="6dec6-355">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="6dec6-356">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-356">**Issue:**</span></span>

<span data-ttu-id="6dec6-357">Si un usuario deshabilitó los controles ActiveX y la compatibilidad con XMLHTTP nativo en la configuración del explorador Windows Internet Explorer, el usuario no podrá unirse a una reunión si se seleccionó Internet Explorer como explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6dec6-357">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="6dec6-358">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-358">**Workaround:**</span></span>

<span data-ttu-id="6dec6-359">Habilite los controles ActiveX o la compatibilidad con XMLHTTP nativo en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6dec6-359">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="6dec6-360">El servicio de conferencia Web de Lync Server no puede recuperarse del modo crítico</span><span class="sxs-lookup"><span data-stu-id="6dec6-360">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="6dec6-361">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-361">**Issue:**</span></span>

<span data-ttu-id="6dec6-p134">Si el modo crítico está activado para el archivado, en caso de errores del sistema, se iniciará el modo crítico y las conferencias ya no funcionarán para los participantes. Una vez que el administrador corrige los errores del sistema (por ejemplo, un problema en la base de datos), el servicio de conferencia de datos no se recupera de manera automática, y el administrador debe reiniciar el servicio manualmente para reanudar las conferencias.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p134">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants. After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="6dec6-364">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-364">**Workaround:**</span></span>

<span data-ttu-id="6dec6-365">El administrador debe reiniciar manualmente el servicio de conferencia una vez que se corrige el error del sistema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-365">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="6dec6-366">El servicio de conferencia web omite el proxy HTTP para los servidores externos de Office Web App</span><span class="sxs-lookup"><span data-stu-id="6dec6-366">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="6dec6-367">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-367">**Issue:**</span></span>

<span data-ttu-id="6dec6-368">Si ha implementado un servidor de Office Web Apps externo al servicio de conferencia web (es decir, un servidor que no se encuentra en la red corporativa interna) en Internet, la red perimetral y el servicio de conferencia Web necesitan un proxy HTTP para conectarse, se producirá un error en la detección de Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-368">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="6dec6-369">El servicio de conferencia web ignora la configuración de proxy HTTP, tal como se define en Topology Builder for Office Web Apps Server Setup.</span><span class="sxs-lookup"><span data-stu-id="6dec6-369">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="6dec6-370">Como resultado, el cliente de Lync no podrá compartir Microsoft PowerPoint 2010 con otros participantes en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="6dec6-370">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="6dec6-371">Si está instalando Lync Server local y también configura Office Web Apps Server local en la red interna, no se requiere una configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="6dec6-371">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="6dec6-372">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-372">**Workaround:**</span></span>

<span data-ttu-id="6dec6-373">La única solución alternativa es no tener una configuración de implementación que requiera el uso de proxy HTTP para comunicarse con un servidor de Office Web Apps externo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-373">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="6dec6-374">No se admite Agregar vídeo a una conferencia de un proveedor de servicios de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="6dec6-374">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="6dec6-375">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-375">**Issue:**</span></span>

<span data-ttu-id="6dec6-376">No es posible agregar un vídeo si el usuario se unió a una conferencia de un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="6dec6-376">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="6dec6-377">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-377">**Workaround:**</span></span>

<span data-ttu-id="6dec6-378">No existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-378">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="6dec6-379">Topologías con IPv6 habilitada fuerce la actualización automática del complemento Silverlight Web App Silverlight para garantizar que la funcionalidad de uso compartido de la pantalla puede funcionar desde Lync Web App</span><span class="sxs-lookup"><span data-stu-id="6dec6-379">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="6dec6-380">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-380">**Issue:**</span></span>

<span data-ttu-id="6dec6-381">Cuando se configura una topología con IPv6 habilitado, los usuarios no pueden compartir su pantalla desde el cliente de Lync Web App si ya hay instalada una versión anterior del complemento de uso compartido de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="6dec6-381">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="6dec6-382">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-382">**Workaround:**</span></span>

<span data-ttu-id="6dec6-383">Para forzar una actualización a la versión más reciente del complemento de uso compartido de pantalla al unirse a una reunión a través de Lync Web App, modifique el valor de **MinSupportedBuildVersion** de "4.0.7457.0" a "4.0.7577.380" en los dos archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dec6-383">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="6dec6-384">% ProgramFiles% \\ los componentes Web de Microsoft Lync Server 15 \\ \\ lleguen a los \\ \\ Complementos de cliente de int \\ \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="6dec6-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="6dec6-385">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web Components \\ REACH \\ \\ Complementos de cliente de ext \\ \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="6dec6-385">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="6dec6-386">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6dec6-386">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="6dec6-387">En algunos casos, es posible que un cliente de Lync que se ejecuta en un equipo configurado para usar IPv4 e IPv6 Dual Stack no admita funciones basadas en la subred IP del equipo, como E911, omisión de medios, control de admisión de llamadas y enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-387">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6dec6-388">La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-388">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="6dec6-389">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-389">**Issue:**</span></span>

<span data-ttu-id="6dec6-390">Cuando un cliente de Lync se ejecuta en un equipo que está habilitado para la pila dual IPv4 e IPv6 y se basa en la resolución DNS del servidor proxy, el cliente puede usar la dirección IPv6 del equipo para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6dec6-390">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="6dec6-391">Después de hacerlo, el cliente de Lync será compatible solo con las funciones compatibles con IPv6, que excluyen el enrutamiento basado en la E911, la omisión de medios, el control de admisión de llamadas y la ubicación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-391">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="6dec6-392">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-392">**Workaround:**</span></span>

<span data-ttu-id="6dec6-393">Para solucionar este problema, deshabilite la compatibilidad de IPv6 en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="6dec6-393">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="6dec6-394">Si la telefonía IP empresarial no está configurada para un usuario, el usuario tendrá que usar el formato E164 para realizar llamadas desde una conferencia.</span><span class="sxs-lookup"><span data-stu-id="6dec6-394">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="6dec6-395">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-395">**Issue:**</span></span>

<span data-ttu-id="6dec6-396">Si la telefonía IP empresarial no está configurada para un usuario, dicho usuario tendrá que usar el formato E164 para marcar correctamente desde una conferencia.</span><span class="sxs-lookup"><span data-stu-id="6dec6-396">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="6dec6-397">Si no se usa el formato E164, el usuario no podrá realizar llamadas salientes desde la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6dec6-397">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="6dec6-398">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-398">**Workaround:**</span></span>

<span data-ttu-id="6dec6-399">Para solucionar este problema, los usuarios que no están habilitados para telefonía IP empresarial deben marcar desde una conferencia con números en el formato E164.</span><span class="sxs-lookup"><span data-stu-id="6dec6-399">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="6dec6-400">Presencia</span><span class="sxs-lookup"><span data-stu-id="6dec6-400">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="6dec6-401">Si un usuario ha seleccionado "bloquear todas las invitaciones y comunicaciones" mientras el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechaza cuando debería</span><span class="sxs-lookup"><span data-stu-id="6dec6-401">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="6dec6-402">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-402">**Issue:**</span></span>

<span data-ttu-id="6dec6-403">Si un usuario seleccionó "Bloquear todas las invitaciones y comunicaciones" cuando el almacén de contactos unificado está activado para el usuario, el estado de presencia no se rechaza cuando debería.</span><span class="sxs-lookup"><span data-stu-id="6dec6-403">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="6dec6-404">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-404">**Workaround:**</span></span>

<span data-ttu-id="6dec6-p138">Para solucionar este problema, puede desactivar el almacén de contactos unificado para el usuario. Para ello, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6dec6-p138">To work around this issue, you can turn off the unified contact store for the user. To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="6dec6-407">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6dec6-407">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="6dec6-408">Los usuarios de Office Communications Server 2007 R2 hospedados de forma local no pueden ver el estado de presencia de los usuarios de Skype empresarial online en implementaciones híbridas: híbrida</span><span class="sxs-lookup"><span data-stu-id="6dec6-408">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="6dec6-409">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-409">**Issue:**</span></span>

<span data-ttu-id="6dec6-410">El problema puede producirse en una implementación híbrida cuando se usa un director 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-410">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="6dec6-411">El estado de presencia de los usuarios hospedados en Skype empresarial online se muestra como presencia desconocida para los usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="6dec6-411">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="6dec6-412">Además, los usuarios hospedados en Skype empresarial online no pueden ver el estado de presencia de los usuarios locales de Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="6dec6-412">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="6dec6-413">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-413">**Workaround:**</span></span>

<span data-ttu-id="6dec6-414">Para evitar este problema parcialmente, cambie el servidor principal (msRTCSIP-presencehomeserver) de los usuarios de Skype empresarial online para que apunte a un grupo local de Lync Server 2013 en lugar del Director de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-414">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="6dec6-415">Puede modificar esta configuración en el servidor front-end local.</span><span class="sxs-lookup"><span data-stu-id="6dec6-415">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="6dec6-416">Esta solución mostrará correctamente el estado de presencia de los usuarios hospedados en Office Communications Server 2007 R2 a los usuarios de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="6dec6-416">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="6dec6-417">Aplicación de grupo de respuesta, aplicación de estacionamiento de llamadas y recogida de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="6dec6-417">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="6dec6-418">Una persona que llama puede oír un segundo de la música en espera durante el establecimiento de una llamada con la entidad de recuperación</span><span class="sxs-lookup"><span data-stu-id="6dec6-418">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6dec6-419">La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-419">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="6dec6-420">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-420">**Issue:**</span></span>

<span data-ttu-id="6dec6-421">Cuando se recupera una llamada a través de la atención de llamadas grupales, el autor de la llamada puede oír un segundo de la música en espera durante el establecimiento de la llamada con la parte del recuperador.</span><span class="sxs-lookup"><span data-stu-id="6dec6-421">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="6dec6-422">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-422">**Workaround:**</span></span>

<span data-ttu-id="6dec6-423">No existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-423">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="6dec6-424">Un agente de grupo de respuesta puede iniciar sesión y cerrar sesión mediante una consola de agente 2010 de Lync Server para Lync Server 2010 solo a grupos de agentes formales.</span><span class="sxs-lookup"><span data-stu-id="6dec6-424">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="6dec6-425">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-425">**Issue:**</span></span>

<span data-ttu-id="6dec6-426">Un agente de grupo de respuesta 2013 de Lync Server puede iniciar y cerrar sesión con una consola de agente de Lync Server 2010 solamente para los grupos de agentes formales de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6dec6-426">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="6dec6-427">En la consola del agente 2010 de Lync Server, los usuarios solo pueden ver el grupo de respuesta de Lync Server 2010 al que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="6dec6-427">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="6dec6-428">No pueden ver ninguno de los grupos de respuesta 2013 de Lync Server a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="6dec6-428">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="6dec6-429">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-429">**Workaround:**</span></span>

<span data-ttu-id="6dec6-430">Si el agente de grupo de respuesta es un usuario de Lync Server 2013 y parte de un grupo de agentes formales de Lync Server 2013, el usuario debe tener acceso a la consola del agente de Lync Server 2013 directamente a través de un vínculo Web en un explorador para iniciar sesión y cerrar los grupos de agentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-430">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="6dec6-431">Un agente de grupo de respuesta 2010 de Lync Server no puede realizar llamadas en nombre de un grupo de respuesta de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dec6-431">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="6dec6-432">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-432">**Issue:**</span></span>

<span data-ttu-id="6dec6-433">Un usuario de Lync Server 2010 que es un agente de un grupo de respuesta de Lync Server 2013 no puede realizar una llamada en nombre del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6dec6-433">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="6dec6-434">El grupo de respuesta de Lync Server 2013 no estará disponible en el cliente de Lync para realizar una llamada.</span><span class="sxs-lookup"><span data-stu-id="6dec6-434">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="6dec6-435">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-435">**Workaround:**</span></span>

<span data-ttu-id="6dec6-436">Para solucionar este problema, debe mover el usuario de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-436">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="6dec6-437">La eliminación de un grupo de respuesta de Lync Server 2010 después de que se haya migrado a Lync Server 2013 impedirá que el grupo de respuesta acepte llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="6dec6-437">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="6dec6-438">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-438">**Issue:**</span></span>

<span data-ttu-id="6dec6-439">Si un grupo de respuesta que se ha migrado de Lync Server 2010 a Lync Server 2013 se ha quitado de Lync Server 2010 a través del panel de control de Lync Server o el shell de administración de Lync Server, el grupo de respuesta de Lync Server 2013 dejará de recibir las llamadas entrantes.</span><span class="sxs-lookup"><span data-stu-id="6dec6-439">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="6dec6-440">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-440">**Workaround:**</span></span>

<span data-ttu-id="6dec6-441">Para solucionar este problema, no quite los grupos de respuesta de Lync Server 2010 que se hayan migrado de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-441">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="6dec6-442">Si ya se ha quitado el grupo de respuesta, debe volver a implementarlo en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-442">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="6dec6-443">Cuando un nuevo flujo de trabajo administrado se establece en inactivo cuando se crea, se producirá un error en la implementación del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6dec6-443">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="6dec6-444">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-444">**Issue:**</span></span>

<span data-ttu-id="6dec6-p143">Cuando un nuevo flujo de trabajo administrado se establece en inactivo al crearse, se producirá un error al implementar el flujo de trabajo. Este problema se detecta cuando el flujo de trabajo se establece en inactivo al crearse, pero no afecta a un flujo de trabajo que se modifica para establecerse en inactivo después de su implementación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p143">When a new managed workflow is set to inactive when created, deployment of the workflow will fail. This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="6dec6-447">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-447">**Workaround:**</span></span>

<span data-ttu-id="6dec6-p144">Al crear e implementar un flujo de trabajo, establezca el flujo de trabajo como activo y luego impleméntelo. Una vez que se implementa correctamente, el flujo de trabajo se puede modificar y establecer en inactivo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p144">When creating and deploying a workflow, set the workflow as active and then deploy it. After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="6dec6-450">La eliminación de un grupo de respuesta del grupo de propietarios impedirá que el grupo de respuesta del grupo de copia de seguridad acepte llamadas entrantes durante la conmutación por error si el grupo de respuesta se ha importado al grupo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6dec6-450">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="6dec6-451">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-451">**Issue:**</span></span>

<span data-ttu-id="6dec6-452">Si un grupo de respuesta que pertenece al grupo principal se ha importado al grupo de copia de seguridad sin sobrescribir el propietario y el grupo de respuesta se quita del grupo de servidores propietario, el grupo de respuesta del grupo de copia de seguridad no aceptará ninguna llamada entrante durante la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="6dec6-452">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="6dec6-453">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-453">**Workaround:**</span></span>

<span data-ttu-id="6dec6-454">Tendrá que volver a implementar el grupo de respuesta en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="6dec6-454">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="6dec6-455">A continuación, tendrá que exportar la configuración del grupo de respuesta del grupo principal e importarla nuevamente en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6dec6-455">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="6dec6-456">También puede volver a crear el grupo de respuesta en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6dec6-456">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="6dec6-457">En este caso, el grupo de copia de seguridad será el grupo propietario del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6dec6-457">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="6dec6-458">No se puede recuperar una llamada estacionada desde la aplicación de estacionamiento de llamadas si la solicitud de recuperación se realiza en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6dec6-458">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="6dec6-459">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-459">**Issue:**</span></span>

<span data-ttu-id="6dec6-460">Cuando se cumplen las siguientes condiciones, se producirá un error en la solicitud de recuperación de una llamada estacionada:</span><span class="sxs-lookup"><span data-stu-id="6dec6-460">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="6dec6-461">Un agente forma parte de un grupo de respuesta anónimo</span><span class="sxs-lookup"><span data-stu-id="6dec6-461">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="6dec6-462">El agente intenta recuperar una llamada estacionada de la aplicación estacionamiento de llamadas a través del grupo de respuesta anónimo</span><span class="sxs-lookup"><span data-stu-id="6dec6-462">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="6dec6-463">El agente intenta recuperar la llamada marcando el número de órbita con la opción de llamada en nombre de un grupo de respuesta o con la misma opción en el cliente de Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="6dec6-463">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="6dec6-464">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-464">**Workaround:**</span></span>

<span data-ttu-id="6dec6-465">No existen soluciones para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-465">There are no workarounds for this issue.</span></span> <span data-ttu-id="6dec6-466">La llamada estacionada debe recuperarse sin hacerlo en nombre de un grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6dec6-466">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="6dec6-467">Panel de control de Lync Server, Generador de topologías y Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="6dec6-467">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="6dec6-468">Limitaciones de la herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="6dec6-468">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6dec6-469">La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-469">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="6dec6-470">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-470">**Issue:**</span></span>

<span data-ttu-id="6dec6-471">La herramienta de planeación tiene las siguientes limitaciones al planear la implementación:</span><span class="sxs-lookup"><span data-stu-id="6dec6-471">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="6dec6-472">Hay un máximo de 10 sitios centrales admitidos</span><span class="sxs-lookup"><span data-stu-id="6dec6-472">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="6dec6-473">Cada sitio central puede tener un máximo de 14 sitios de sucursal</span><span class="sxs-lookup"><span data-stu-id="6dec6-473">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="6dec6-474">Cada sitio central puede tener un máximo de 240.000 usuarios</span><span class="sxs-lookup"><span data-stu-id="6dec6-474">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="6dec6-475">Además, la herramienta de planeación no incluye los valores de los siguientes elementos al calcular la topología recomendada:</span><span class="sxs-lookup"><span data-stu-id="6dec6-475">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="6dec6-476">El número de usuarios que están hospedados en línea</span><span class="sxs-lookup"><span data-stu-id="6dec6-476">The number of users that are homed online</span></span>

  - <span data-ttu-id="6dec6-477">El porcentaje de usuarios que están habilitados para la Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="6dec6-477">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="6dec6-478">Porcentaje de usuarios que usan Lync Web App</span><span class="sxs-lookup"><span data-stu-id="6dec6-478">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="6dec6-479">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-479">**Workaround:**</span></span>

<span data-ttu-id="6dec6-480">No hay ninguna solución alternativa para estos problemas.</span><span class="sxs-lookup"><span data-stu-id="6dec6-480">There is no workaround for these issues.</span></span> <span data-ttu-id="6dec6-481">Para obtener más información acerca de la herramienta de planeación, consulte [diseño de la topología para Lync Server 2013 mediante la herramienta de planeación](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="6dec6-481">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="6dec6-482">Es posible que la herramienta de planeación no use direcciones IP definidas previamente para la red perimetral al actualizar las opciones</span><span class="sxs-lookup"><span data-stu-id="6dec6-482">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="6dec6-483">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-483">**Issue:**</span></span>

<span data-ttu-id="6dec6-484">Una vez que haya completado el diseño mediante la herramienta de planeación, si realiza cambios en las opciones de la red perimetral, se pueden agregar direcciones IP adicionales al diseño en lugar de actualizar las direcciones IP existentes.</span><span class="sxs-lookup"><span data-stu-id="6dec6-484">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="6dec6-485">Esto puede ocurrir cuando se ven los detalles del diagrama de red perimetral, seleccione **hacer clic aquí para actualizar las opciones**y, a continuación, en el cuadro de diálogo Opciones de configuración, seleccione red perimetral, seleccione **quiero usar los mismos FQDN y direcciones IP, pero distintos puertos para los servicios perimetrales en el servidor perimetral**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-485">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="6dec6-486">Aplicar los cambios puede dar lugar a que se agreguen nuevas direcciones IP y servidores perimetrales al diseño.</span><span class="sxs-lookup"><span data-stu-id="6dec6-486">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="6dec6-487">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-487">**Workaround:**</span></span>

<span data-ttu-id="6dec6-488">No hay ninguna solución alternativa para este problema en este momento.</span><span class="sxs-lookup"><span data-stu-id="6dec6-488">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="6dec6-489">En el panel de control de Lync Server, "mover todos los usuarios al grupo" puede que no funcione según lo esperado</span><span class="sxs-lookup"><span data-stu-id="6dec6-489">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="6dec6-490">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-490">**Issue:**</span></span>

<span data-ttu-id="6dec6-491">Cuando se usa el panel de control de Lync Server para mover todos los usuarios de un grupo a otro en un entorno complejo de Active Directory, como uno con varios controladores de dominio y dominios principales/secundarios, se puede devolver un mensaje de error que indica que "el usuario especificado no es un usuario heredado, use Move-CsUser cmdlet en su lugar".</span><span class="sxs-lookup"><span data-stu-id="6dec6-491">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="6dec6-492">Esto es resultado de tiempos de replicación más largos en entornos complejos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6dec6-492">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="6dec6-493">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-493">**Workaround:**</span></span>

<span data-ttu-id="6dec6-494">Para solucionar este problema, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6dec6-494">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="6dec6-495">Use filtros en el panel de control de Lync Server para buscar usuarios heredados, seleccione esos usuarios y, a continuación, use el **comando mover usuarios seleccionados a grupo** en lugar de **mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-495">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="6dec6-496">Use el shell de administración de Lync Server para mover usuarios heredados en lotes con los cmdlets de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-496">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="6dec6-497">El panel de control de Lync Server deja de funcionar en un entorno de VMware después de que el complemento de explorador Microsoft Silverlight se actualice a la versión 5</span><span class="sxs-lookup"><span data-stu-id="6dec6-497">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="6dec6-498">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-498">**Issue:**</span></span>

<span data-ttu-id="6dec6-499">Si usa el panel de control de Lync Server en un entorno de VMware, el panel de control de Lync Server puede dejar de funcionar después de actualizar Silverlight a la versión 5.</span><span class="sxs-lookup"><span data-stu-id="6dec6-499">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="6dec6-500">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-500">**Workaround:**</span></span>

<span data-ttu-id="6dec6-501">Para solucionar este problema, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6dec6-501">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="6dec6-502">Desinstale Silverlight 5 y luego instale Silverlight 4 desde [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) .</span><span class="sxs-lookup"><span data-stu-id="6dec6-502">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="6dec6-503">Abra el panel de control de Lync Server desde un equipo que no sea un equipo virtual VMware.</span><span class="sxs-lookup"><span data-stu-id="6dec6-503">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="6dec6-504">Para abrir el panel de control de Lync Server desde un equipo remoto, instale las herramientas de administración de Lync Server en el equipo y, a continuación, inicie el panel de control de Lync Server desde el menú **Inicio** de Windows.</span><span class="sxs-lookup"><span data-stu-id="6dec6-504">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="6dec6-505">También puede abrir el panel de control de Lync Server escribiendo la dirección URL en un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="6dec6-505">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="6dec6-506">La dirección URL será similar a https:// \<frontend\_pool\_fqdn\> /CSCP.</span><span class="sxs-lookup"><span data-stu-id="6dec6-506">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="6dec6-507">Un administrador no puede ejecutar el cmdlet Uninstall-csMirrorDB después de quitar la base de datos de reflejo en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="6dec6-507">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="6dec6-508">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-508">**Issue:**</span></span>

<span data-ttu-id="6dec6-509">Cuando un administrador deshabilita una base de datos de reflejo en el generador de topologías y elimina la base de datos de reflejo en el generador de topologías, se muestra un mensaje en la lista de tareas pendientes para que el administrador ejecute el cmdlet **Uninstall-csMirrorDatabase** para quitar la creación de reflejo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-509">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="6dec6-510">Cuando el administrador intenta ejecutar el cmdlet, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="6dec6-510">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="6dec6-511">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-511">**Workaround:**</span></span>

<span data-ttu-id="6dec6-512">Para quitar la creación de reflejos de SQL de un grupo en el generador de topologías, primero debe usar un cmdlet para quitar el reflejo en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6dec6-512">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="6dec6-513">Después, podrá usar el Generador de topologías para quitar el reflejo de la topología.</span><span class="sxs-lookup"><span data-stu-id="6dec6-513">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="6dec6-514">Para quitar el reflejo de SQL Server, use este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6dec6-514">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="6dec6-515">Por ejemplo, para quitar el reflejo y descartar las bases de datos de usuario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dec6-515">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="6dec6-516">El parámetro *DropExistingDatabasesOnMirror* hace que las bases de datos afectadas se eliminen del reflejo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-516">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="6dec6-517">Después, para quitar el reflejo de la topología, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dec6-517">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="6dec6-518">En Topology Builder, haga clic con el botón secundario en el grupo y haga clic en **Modificar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-518">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="6dec6-519">Desactive **Habilitar creación de reflejo de almacén SQL** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-519">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="6dec6-520">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="6dec6-520">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="6dec6-521">Siempre que realice un cambio en una relación de creación de reflejo de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-521">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="6dec6-522">Los errores de validación se devuelven en el generador de topologías cuando un administrador intenta quitar una implementación con un grupo de servidores front-end que tiene un almacén de testigos asociado</span><span class="sxs-lookup"><span data-stu-id="6dec6-522">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="6dec6-523">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-523">**Issue:**</span></span>

<span data-ttu-id="6dec6-524">Si un administrador intenta usar el comando **quitar implementación** en el generador de topologías para quitar una implementación que incluye un grupo de servidores front-end con un almacén de testigos asociado, se muestra un error de validación en el generador de topologías y la acción no se llevará a cabo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-524">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="6dec6-525">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-525">**Workaround:**</span></span>

<span data-ttu-id="6dec6-526">Para solucionar este problema, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6dec6-526">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="6dec6-527">Quite el almacén de testigos antes de tratar de quitar la implementación.</span><span class="sxs-lookup"><span data-stu-id="6dec6-527">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="6dec6-528">Agregue un almacén de testigos para el grupo de servidores front-end y luego quítelo.</span><span class="sxs-lookup"><span data-stu-id="6dec6-528">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="6dec6-529">La información de implementación del servidor de chat persistente es incoherente entre la herramienta de planeación y el generador de topologías</span><span class="sxs-lookup"><span data-stu-id="6dec6-529">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="6dec6-530">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-530">**Issue:**</span></span>

<span data-ttu-id="6dec6-531">Cuando la herramienta de planeación de Lync Server 2013, genera el diagrama de la topología del sitio para una implementación del servidor de chat persistente con la recuperación ante desastres habilitada, el diagrama de topología de sitio incluye varios sitios (físicos), con servidores de chat persistente uniformemente asignados en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="6dec6-531">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="6dec6-532">En el generador de topologías, todos los servidores de chat persistente se representan como pertenecientes a un sitio único (lógico) y se enumeran en el mismo nodo de grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6dec6-532">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="6dec6-533">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-533">**Workaround:**</span></span>

<span data-ttu-id="6dec6-534">Actualmente, no existe ninguna solución para este problema.</span><span class="sxs-lookup"><span data-stu-id="6dec6-534">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="6dec6-535">El usuario debe analizar el resultado de la herramienta de planeación de la implementación del servidor de chat persistente y modificar el plan para satisfacer sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="6dec6-535">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="6dec6-536">Localización</span><span class="sxs-lookup"><span data-stu-id="6dec6-536">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="6dec6-537">Supervisión</span><span class="sxs-lookup"><span data-stu-id="6dec6-537">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="6dec6-538">El Asistente para implementar informes de supervisión muestra caracteres incorrectos en determinadas circunstancias al usar la versión de Asia oriental de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6dec6-538">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="6dec6-539">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-539">**Issue:**</span></span>

<span data-ttu-id="6dec6-540">Cuando se usa una versión de Asia oriental de Lync Server 2013 (por ejemplo, Chino (simplificado), Chino (tradicional), Japonés o coreano, en un sistema operativo que tiene la configuración regional del sistema no establecida en un idioma del este asiático, el Asistente para implementar informes de supervisión mostrará signos de interrogación u otros caracteres en lugar de mensajes localizados.</span><span class="sxs-lookup"><span data-stu-id="6dec6-540">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="6dec6-541">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-541">**Workaround:**</span></span>

<span data-ttu-id="6dec6-542">Para solucionar este problema, establezca la configuración regional del sistema operativo y Lync Server 2013 en el mismo idioma, que mostrará todos los mensajes correctamente.</span><span class="sxs-lookup"><span data-stu-id="6dec6-542">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="6dec6-543">Panel de Control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="6dec6-543">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="6dec6-544">En algunos casos, el primer elemento de la barra de navegación superior de una página del panel de control de Lync Server desaparece cuando se hace clic en el último elemento de la barra de navegación superior</span><span class="sxs-lookup"><span data-stu-id="6dec6-544">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="6dec6-545">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-545">**Issue:**</span></span>

<span data-ttu-id="6dec6-546">Hay tres casos conocidos en los que, al hacer clic en el último elemento de la barra de navegación superior de una página del panel de control de Lync Server, el primer elemento de la barra de navegación superior desaparecerá:</span><span class="sxs-lookup"><span data-stu-id="6dec6-546">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="6dec6-547">En la versión en francés, en la página "Féderation et accès externe", desaparece el elemento "Stratégie d'accès externe" al hacer clic en "Partenaires fédérés XMPP".</span><span class="sxs-lookup"><span data-stu-id="6dec6-547">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="6dec6-548">En la versión en alemán, en la página "Clients", desaparece el elemento "Clientversionskonfiguration" al hacer clic en "Pushbenachrichtigungskonfiguration".</span><span class="sxs-lookup"><span data-stu-id="6dec6-548">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="6dec6-549">En la versión en ruso, en la página "Конфигурация сети", desaparece el elemento "Глобально" al hacer clic en "Маршрут региона".</span><span class="sxs-lookup"><span data-stu-id="6dec6-549">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="6dec6-550">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-550">**Workaround:**</span></span>

<span data-ttu-id="6dec6-551">Para solucionar este problema, actualice la página del panel de control de Lync Server en el explorador.</span><span class="sxs-lookup"><span data-stu-id="6dec6-551">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="6dec6-552">La página se cargará en el explorador con todos los elementos de la barra de navegación superior visibles.</span><span class="sxs-lookup"><span data-stu-id="6dec6-552">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="6dec6-553">Libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="6dec6-553">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="6dec6-554">La indización de la libreta de direcciones no funciona según lo esperado en algunos idiomas</span><span class="sxs-lookup"><span data-stu-id="6dec6-554">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6dec6-555">La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-555">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="6dec6-556">Si las propiedades de un usuario contienen un campo indizado y ese campo contiene solo caracteres que no se pueden indizar, el usuario no aparecerá en las búsquedas realizadas en la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="6dec6-556">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="6dec6-557">Los siguientes caracteres y configuraciones regionales no se pueden indizar:</span><span class="sxs-lookup"><span data-stu-id="6dec6-557">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="6dec6-558">Caracteres en mayúsculas: cirílico, griego y armenio</span><span class="sxs-lookup"><span data-stu-id="6dec6-558">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="6dec6-559">Caracteres en mayúsculas acentuados</span><span class="sxs-lookup"><span data-stu-id="6dec6-559">Upper-case accented characters</span></span>

  - <span data-ttu-id="6dec6-560">Tailandés</span><span class="sxs-lookup"><span data-stu-id="6dec6-560">Thai</span></span>

  - <span data-ttu-id="6dec6-561">Lao</span><span class="sxs-lookup"><span data-stu-id="6dec6-561">Lao</span></span>

  - <span data-ttu-id="6dec6-562">Myanmar</span><span class="sxs-lookup"><span data-stu-id="6dec6-562">Myanmar</span></span>

  - <span data-ttu-id="6dec6-563">Devanagari</span><span class="sxs-lookup"><span data-stu-id="6dec6-563">Devanagari</span></span>

  - <span data-ttu-id="6dec6-564">Etíope</span><span class="sxs-lookup"><span data-stu-id="6dec6-564">Ethiopic</span></span>

  - <span data-ttu-id="6dec6-565">Tibetano</span><span class="sxs-lookup"><span data-stu-id="6dec6-565">Tibetan</span></span>

  - <span data-ttu-id="6dec6-566">Bengalí</span><span class="sxs-lookup"><span data-stu-id="6dec6-566">Bengali</span></span>

  - <span data-ttu-id="6dec6-567">Gujarati</span><span class="sxs-lookup"><span data-stu-id="6dec6-567">Gujarati</span></span>

  - <span data-ttu-id="6dec6-568">Telugu</span><span class="sxs-lookup"><span data-stu-id="6dec6-568">Telugu</span></span>

  - <span data-ttu-id="6dec6-569">Todos los demás scripts indios</span><span class="sxs-lookup"><span data-stu-id="6dec6-569">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="6dec6-570">Lync Web App, programador web y componentes Web</span><span class="sxs-lookup"><span data-stu-id="6dec6-570">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="6dec6-571">Reserva de idioma para determinados idiomas en el programador web de Lync, el acceso telefónico, el iniciador de sesiones, la administración del salón de chat persistente y OCTab podrían no funcionar según lo esperado</span><span class="sxs-lookup"><span data-stu-id="6dec6-571">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="6dec6-572">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-572">**Issue:**</span></span>

<span data-ttu-id="6dec6-573">Al seleccionar una configuración regional neutra en un explorador Web (en Internet Explorer, por ejemplo, el nombre del idioma sin especificación adicional, como "noruego \[ no \] ") en lugar de una configuración regional que especifica el idioma, el script y la configuración regional (como "noruego, Bokmål (Noruega) \[ NB-no \] ") puede llevar a un comportamiento de visualización inesperado para determinados idiomas en el programador web de Lync, acceso telefónico, iniciador de chat, administración de salones de</span><span class="sxs-lookup"><span data-stu-id="6dec6-573">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="6dec6-574">Por ejemplo, es posible que los usuarios vean la página en inglés al seleccionar uno de los siguientes idiomas:</span><span class="sxs-lookup"><span data-stu-id="6dec6-574">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="6dec6-575">Noruego</span><span class="sxs-lookup"><span data-stu-id="6dec6-575">Norwegian</span></span>

  - <span data-ttu-id="6dec6-576">Portugués</span><span class="sxs-lookup"><span data-stu-id="6dec6-576">Portuguese</span></span>

  - <span data-ttu-id="6dec6-577">Serbio</span><span class="sxs-lookup"><span data-stu-id="6dec6-577">Serbian</span></span>

<span data-ttu-id="6dec6-578">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-578">**Workaround:**</span></span>

<span data-ttu-id="6dec6-579">Si desea seleccionar un idioma con una configuración regional neutral, asegúrese siempre de agregar también el idioma con una configuración regional específica (con un script o código de país) como idioma adicional en la lista de preferencias de idioma del explorador.</span><span class="sxs-lookup"><span data-stu-id="6dec6-579">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="6dec6-580">Hay compatibilidad limitada con las configuraciones regionales azerí y uzbeko al usar el programador web de Lync, el acceso telefónico, el iniciador de reuniones, la administración del salón de chat persistente y OCTab en algunos exploradores Web</span><span class="sxs-lookup"><span data-stu-id="6dec6-580">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6dec6-581">La información de esta sección se refiere a las actualizaciones acumulativas para Lync Server 2013: febrero de 2013.</span><span class="sxs-lookup"><span data-stu-id="6dec6-581">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="6dec6-582">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-582">**Issue:**</span></span>

<span data-ttu-id="6dec6-583">Cuando usa Internet Explorer 8 o Internet Explorer 9 y establece el idioma del explorador en Azerí (Latino) o uzbeko (Latino), las páginas de acceso telefónico local y de iniciador de participación se mostrarán en inglés o en el idioma preferido establecido en el explorador.</span><span class="sxs-lookup"><span data-stu-id="6dec6-583">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="6dec6-584">Al usar los exploradores de Firefox o Chrome y establecer el idioma del explorador en Azerí (Latino) o uzbeko (Latino), la aplicación Web de Lync, el programador web de Lync y el OCTab de RGS se mostrarán en inglés o en el idioma preferido establecido para el explorador.</span><span class="sxs-lookup"><span data-stu-id="6dec6-584">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="6dec6-585">La configuración regional uzbeko (Latín) no es compatible con el explorador Safari.</span><span class="sxs-lookup"><span data-stu-id="6dec6-585">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="6dec6-586">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-586">**Workaround:**</span></span>

<span data-ttu-id="6dec6-587">No hay ninguna solución alternativa para estos problemas.</span><span class="sxs-lookup"><span data-stu-id="6dec6-587">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="6dec6-588">Falta la flecha de la lista desplegable para "unirse a la reunión de" en la versión en rumano de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="6dec6-588">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="6dec6-589">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-589">**Issue:**</span></span>

<span data-ttu-id="6dec6-590">Cuando un usuario que usa la versión rumano de Lync Web App realiza los pasos siguientes, la flecha desplegable no se muestra para unirse a la **reunión** en la lista desplegable:</span><span class="sxs-lookup"><span data-stu-id="6dec6-590">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="6dec6-591">Seleccione **Recordar mis datos en este equipo** en la pestaña **General**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-591">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="6dec6-592">Seleccione la pestaña **Teléfono**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-592">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="6dec6-593">Haga clic en la lista desplegable para **Unirse a la reunión**.</span><span class="sxs-lookup"><span data-stu-id="6dec6-593">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="6dec6-594">Los usuarios no verán una flecha que indica que hay más opciones que las predeterminadas de **Lync Web App**, entre las que se incluyen: **no Únase a audio** (en rumano, "nu se valores la aplicación audio") y un **número nuevo**"(en rumano," Număr Nou ").</span><span class="sxs-lookup"><span data-stu-id="6dec6-594">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="6dec6-595">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-595">**Workaround:**</span></span>

<span data-ttu-id="6dec6-596">Aunque no se muestre la flecha de esta lista desplegable, los usuarios pueden seleccionar de todos modos las opciones adicionales de la lista haciendo clic en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6dec6-596">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="6dec6-597">Cuando se usa la versión en Turco del programador web de Lync, no se puede guardar una reunión al usar la opción "las personas que elijan" en "quién es un moderador"</span><span class="sxs-lookup"><span data-stu-id="6dec6-597">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="6dec6-598">**Emitir**</span><span class="sxs-lookup"><span data-stu-id="6dec6-598">**Issue:**</span></span>

<span data-ttu-id="6dec6-p159">Al crear o modificar una reunión en la versión en turco del Programador web de Lync, no se admite la opción "Las personas que yo elija" en "Quién es moderador". Cuando se selecciona esta opción, no se puede guardar la reunión. En cambio, aparece un mensaje de error que indica que una o más personas no pueden convertirse en moderadores.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p159">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported. When this option is selected, the meeting can't be saved. Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="6dec6-602">**Evitar**</span><span class="sxs-lookup"><span data-stu-id="6dec6-602">**Workaround:**</span></span>

<span data-ttu-id="6dec6-p160">Para solucionar este problema, los usuarios pueden usar la opción predeterminada "Personas de mi compañía" o cualquier otra opción, como "Solo el organizador" o "Todos, incluidas las personas de fuera de mi compañía". El organizador puede disminuir o aumentar el nivel de los participantes para establecer sus roles correctos más adelante, una vez que se hayan unido a la reunión.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p160">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company." The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="6dec6-605">Además, los usuarios que entienden otro idioma pueden cambiar la selección de idioma en el explorador. Pueden elegir uno de los otros 43 idiomas admitidos e intentar usar la opción "Las personas que yo elija".</span><span class="sxs-lookup"><span data-stu-id="6dec6-605">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="6dec6-606">Copyright</span><span class="sxs-lookup"><span data-stu-id="6dec6-606">Copyright</span></span>

<span data-ttu-id="6dec6-p161">Este documento hace referencia a una versión preliminar de un producto de software que puede haber cambiado considerablemente antes del lanzamiento de la versión comercial definitiva. La información que contiene es propiedad confidencial de Microsoft Corporation. Dicha información se divulga conforme a un acuerdo de confidencialidad entre el destinatario y Microsoft. Este documento se proporciona con carácter informativo únicamente y Microsoft no otorga garantías expresas ni implícitas en él. La información contenida en este documento, incluidas las direcciones URL y otras referencias a sitios web de Internet, está sujeta a modificaciones sin previo aviso. El usuario asume todos los riesgos resultantes del uso de este documento. A menos que se indique lo contrario, las compañías, organizaciones, productos, nombres de dominio, direcciones de correo electrónico, logotipos, personas, lugares y eventos mencionados en los ejemplos son ficticios. No se pretende indicar ni debe deducirse ninguna asociación con compañías, organizaciones, productos, nombres de dominio, direcciones de correo electrónico, logotipos, personas, lugares o eventos reales. El cumplimiento de las leyes de derechos de autor aplicables es responsabilidad del usuario. Sin limitar los derechos de autor, ninguna parte de este documento puede ser reproducida, almacenada o introducida en un sistema de recuperación, ni transmitida, de ninguna forma ni por ningún medio (ya sea electrónico, mecánico, fotocopia, grabación o de otro tipo), con ningún propósito, sin autorización expresa y por escrito de Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p161">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation. It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft. This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document. Information in this document, including URL and other Internet website references, is subject to change without notice. The entire risk of the use or the results from the use of this document remains with the user. Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious. No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="6dec6-p162">Microsoft puede ser propietario de patentes, solicitudes de patentes, marcas comerciales, derechos de autor u otros derechos de propiedad intelectual relacionados con el tema de este documento. Excepto cuando quede expresamente indicado en cualquier contrato de licencia de Microsoft, el suministro de este documento no le otorga ninguna licencia sobre dichas patentes, marcas comerciales, derechos de autor u otro tipo de propiedad intelectual.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="6dec6-p163">© 2012 Microsoft Corporation. Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="6dec6-p163">© 2012 Microsoft Corporation. All rights reserved.</span></span>

<span data-ttu-id="6dec6-620">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook y SQL Server son marcas comerciales o marcas registradas de Microsoft Corporation en los Estados Unidos y/o en otros países o regiones.</span><span class="sxs-lookup"><span data-stu-id="6dec6-620">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="6dec6-621">Todas las demás marcas comerciales pertenecen a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="6dec6-621">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

