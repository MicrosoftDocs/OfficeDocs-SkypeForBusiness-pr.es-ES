---
title: 'Lync Server 2013: requisitos de copia de seguridad y restauración: datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8431e16e976f0ad189205f0c42c04d50e6936e90
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527047"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="12c54-102">Requisitos de copia de seguridad y restauración en Lync Server 2013: datos</span><span class="sxs-lookup"><span data-stu-id="12c54-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12c54-103">_**Última modificación del tema:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="12c54-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="12c54-104">Lync Server usa la configuración y la información de configuración que se almacenan en las bases de datos y los datos que se almacenan en las bases de datos y los almacenes de archivos.</span><span class="sxs-lookup"><span data-stu-id="12c54-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="12c54-105">En este tema se describen los datos de los que necesita hacer una copia de seguridad para poder restaurar el servicio si la organización experimenta un error o una interrupción, y también identifica los datos y componentes usados por Lync Server de los que necesita hacer una copia de seguridad por separado.</span><span class="sxs-lookup"><span data-stu-id="12c54-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="12c54-106">Requisitos de parámetros y configuración</span><span class="sxs-lookup"><span data-stu-id="12c54-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="12c54-107">En este tema se incluyen procedimientos para realizar copias de seguridad y restaurar la información de configuración y configuración necesaria para la recuperación del servicio de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="12c54-108">La información de configuración se encuentra en el almacén de administración central o en otra base de datos back-end o en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12c54-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="12c54-109">En la tabla siguiente se identifican las opciones de configuración y la información de configuración necesarias para hacer una copia de seguridad y restaurar.</span><span class="sxs-lookup"><span data-stu-id="12c54-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="12c54-110">Datos de parámetros y configuración</span><span class="sxs-lookup"><span data-stu-id="12c54-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12c54-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="12c54-111">Type of data</span></span></th>
<th><span data-ttu-id="12c54-112">Dónde se almacenan</span><span class="sxs-lookup"><span data-stu-id="12c54-112">Where stored</span></span></th>
<th><span data-ttu-id="12c54-113">Descripción/Cuándo hacer una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="12c54-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12c54-114">Información de configuración de la topología</span><span class="sxs-lookup"><span data-stu-id="12c54-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="12c54-115">Almacén de administración central (base de datos: XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="12c54-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="12c54-116">Topología, directivas y opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="12c54-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="12c54-117">Realice una copia de seguridad con las copias de seguridad periódicas y después use los cmdlets o el panel de control de Lync Server para modificar la configuración o las directivas.</span><span class="sxs-lookup"><span data-stu-id="12c54-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12c54-118">Información de ubicación</span><span class="sxs-lookup"><span data-stu-id="12c54-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="12c54-119">Almacén de administración central (base de datos: Lis. MDF)</span><span class="sxs-lookup"><span data-stu-id="12c54-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="12c54-p103">Información de configuración de la telefonía IP empresarial (Enterprise Voice Enhanced 9-1-1, E9-1-1). Esta información generalmente es estática.</span><span class="sxs-lookup"><span data-stu-id="12c54-p103">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information. This information is generally static.</span></span></p>
<p><span data-ttu-id="12c54-122">Haga la copia de seguridad con el resto de copias de seguridad habituales.</span><span class="sxs-lookup"><span data-stu-id="12c54-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12c54-123">Información de configuración del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="12c54-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="12c54-124">Servidor back-end o servidor Standard Edition (base de datos: RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="12c54-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="12c54-125">Grupos, colas y flujos de trabajo del agente de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="12c54-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="12c54-126">Haga la copia de seguridad con el resto de copias de seguridad habituales y después de agregar o modificar grupos de agentes, colas o flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="12c54-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="12c54-127">Requisitos de datos</span><span class="sxs-lookup"><span data-stu-id="12c54-127">Data Requirements</span></span>

<span data-ttu-id="12c54-128">A continuación, se muestra una lista de los datos de Lync Server de los que necesita hacer una copia de seguridad para poder restaurar el servicio Lync Server en caso de que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="12c54-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="12c54-129">Tenga en cuenta que algunos tipos de datos no son necesarios para la recuperación.</span><span class="sxs-lookup"><span data-stu-id="12c54-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="12c54-130">Este tema no contiene procedimientos para realizar copias de seguridad de estos tipos de datos, entre los que se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="12c54-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="12c54-131">Datos de usuario transitorios, como extremos y suscripciones, servidores de conferencia activos y estados de conferencia transitorios (base de datos: RtcDyn.mdf)</span><span class="sxs-lookup"><span data-stu-id="12c54-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="12c54-132">Datos de la libreta de direcciones (bases de datos: Rtcab. MDF y Rtcab1. MDF).</span><span class="sxs-lookup"><span data-stu-id="12c54-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="12c54-133">La base de datos de la libreta de direcciones se regenera automáticamente desde los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12c54-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="12c54-134">Información dinámica para la aplicación estacionamiento de llamadas (base de datos: CpsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="12c54-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="12c54-135">Datos del grupo de respuesta transitorios, como el estado de inicio de sesión del agente y la información de llamadas en espera (base de datos: RgsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="12c54-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="12c54-136">La base de datos de cumplimiento para chat persistente (base de datos: MgcComp. MDF).</span><span class="sxs-lookup"><span data-stu-id="12c54-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="12c54-137">Si tiene habilitado el cumplimiento de chat persistente, la información de la base de datos de cumplimiento de chat persistente será transitoria siempre que tenga un adaptador configurado para leer información de la base de datos y convertirla a un formato alternativo.</span><span class="sxs-lookup"><span data-stu-id="12c54-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="12c54-138">Por lo tanto, la base de datos de cumplimiento de chat persistente se considera transitoria.</span><span class="sxs-lookup"><span data-stu-id="12c54-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="12c54-139">Lync Server 2013 el servidor de chat persistente se distribuye con un adaptador XML.</span><span class="sxs-lookup"><span data-stu-id="12c54-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="12c54-140">También puede instalar adaptadores personalizados que toman estos datos y los mueven a otros orígenes, como archivos hospedados de Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c54-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="12c54-141">En la tabla siguiente se identifican los datos necesarios para la copia de seguridad y la restauración.</span><span class="sxs-lookup"><span data-stu-id="12c54-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="12c54-142">Datos almacenados en bases de datos</span><span class="sxs-lookup"><span data-stu-id="12c54-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12c54-143">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="12c54-143">Type of data</span></span></th>
<th><span data-ttu-id="12c54-144">Dónde se almacenan</span><span class="sxs-lookup"><span data-stu-id="12c54-144">Where stored</span></span></th>
<th><span data-ttu-id="12c54-145">Descripción/Cuándo hacer una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="12c54-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12c54-146">Datos de usuario persistentes</span><span class="sxs-lookup"><span data-stu-id="12c54-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="12c54-147">Servidor back-end o servidor Standard Edition (base de datos: RTCXDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="12c54-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="12c54-148">Derechos de usuario, listas de contacto de usuario, datos de grupos de servidores, conferencias programadas, etc.</span><span class="sxs-lookup"><span data-stu-id="12c54-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="12c54-149">Estos datos de usuario no incluyen el contenido cargado en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="12c54-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="12c54-150">Haga la copia de seguridad con el resto de copias de seguridad habituales.</span><span class="sxs-lookup"><span data-stu-id="12c54-150">Back up with your regular backups.</span></span> <span data-ttu-id="12c54-151">Esta información es dinámica, pero la pérdida de actualizaciones no es catastrófica para Lync Server si necesita restaurar la última copia de seguridad normal.</span><span class="sxs-lookup"><span data-stu-id="12c54-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="12c54-152">Si las listas de contactos son esenciales para la organización, puede hacer una copia de seguridad de estos datos con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="12c54-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12c54-153">Datos de archivado</span><span class="sxs-lookup"><span data-stu-id="12c54-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="12c54-154">Base de datos de archivado (base de datos: LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="12c54-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="12c54-155">Estos datos pueden almacenarse en Exchange 2013, si ha habilitado la opción de integración de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c54-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="12c54-156">De lo contrario, estos datos se conservan en una base de datos de archivado de Lync Server, que puede estar combinada con otra base de datos de Lync Server o independiente en un servidor de bases de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="12c54-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="12c54-157">Mensajería instantánea (MI) y contenido de reuniones.</span><span class="sxs-lookup"><span data-stu-id="12c54-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="12c54-158">Estos datos no son críticos para Lync Server, pero pueden ser críticos para su organización con fines normativos.</span><span class="sxs-lookup"><span data-stu-id="12c54-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="12c54-159">Determine la programación de copias de seguridad según corresponda.</span><span class="sxs-lookup"><span data-stu-id="12c54-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12c54-160">Datos de supervisión</span><span class="sxs-lookup"><span data-stu-id="12c54-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="12c54-161">Bases de datos de supervisión (LcsCDR.mdf y QoeMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="12c54-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="12c54-162">Estas bases de datos pueden combinarse con otra base de datos de Lync Server o independiente en un servidor de bases de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="12c54-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="12c54-163">Registros de detalles de llamadas (LcsCDR. MDF) y métricas de calidad de la experiencia (QoE) (QoeMetrics. MDF).</span><span class="sxs-lookup"><span data-stu-id="12c54-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="12c54-p112">Las registros detallados de llamadas son dinámicos y pueden ser esenciales para el negocio. Determine la programación de copias de seguridad teniendo en cuenta si se necesitan estos registros con fines de cumplimiento de normativas.</span><span class="sxs-lookup"><span data-stu-id="12c54-p112">Call detail records are dynamic and may be critical to your business. Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="12c54-166">La información de Calidad de la experiencia es dinámica.</span><span class="sxs-lookup"><span data-stu-id="12c54-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="12c54-167">La pérdida de datos de QoE no es crítica para el funcionamiento de Lync Server, pero puede ser crítico para su empresa.</span><span class="sxs-lookup"><span data-stu-id="12c54-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="12c54-168">Determine la programación de copias de seguridad según la importancia de esta información para la organización.</span><span class="sxs-lookup"><span data-stu-id="12c54-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12c54-169">Datos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="12c54-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="12c54-170">Base de datos de chat persistente (administradas. MDF).</span><span class="sxs-lookup"><span data-stu-id="12c54-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="12c54-171">Esta base de datos puede estar combinada con otra base de datos de Lync Server o independiente en un servidor de base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="12c54-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="12c54-172">Los datos de chat persistente son contenido de chat real que se publica en salones de chat.</span><span class="sxs-lookup"><span data-stu-id="12c54-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="12c54-173">Estos datos suelen ser críticos para la empresa.</span><span class="sxs-lookup"><span data-stu-id="12c54-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="12c54-174">Puede optar por usar la copia de seguridad de SQL Server o exportar la base de datos mediante el cmdlet <strong>Export-CsPersistentChatData</strong> que se proporciona en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="12c54-175">Para la recuperación de los datos, puede importar y restaurar la base de datos hasta el punto de la última copia de seguridad completa, lo que significa que no se puede restaurar la base de datos en el punto de error.</span><span class="sxs-lookup"><span data-stu-id="12c54-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="12c54-176">Requisitos de datos de almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="12c54-176">File Store Data Requirements</span></span>

<span data-ttu-id="12c54-177">En una implementación de Enterprise Edition, el almacén de archivos de Lync Server suele estar ubicado en un servidor de archivos.</span><span class="sxs-lookup"><span data-stu-id="12c54-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="12c54-178">En una implementación de Standard Edition, el almacén de archivos de Lync Server se encuentra de forma predeterminada en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12c54-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="12c54-179">Normalmente, hay un almacén de archivos de Lync Server que se comparte en un sitio.</span><span class="sxs-lookup"><span data-stu-id="12c54-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="12c54-180">El almacén de archivos de chat persistente usa el mismo recurso compartido de archivos que el almacén de archivos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="12c54-181">Las ubicaciones del almacén de archivos se identifican como \\ \\ \\ nombre del recurso compartido del servidor.</span><span class="sxs-lookup"><span data-stu-id="12c54-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="12c54-182">Para buscar las ubicaciones específicas de los almacenes de archivos, abra el generador de topologías y mire en el nodo **almacenes de archivos** .</span><span class="sxs-lookup"><span data-stu-id="12c54-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="12c54-183">En la siguiente tabla se identifican los almacenes de archivos necesarios para hacer una copia de seguridad y restaurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="12c54-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="12c54-184">Almacenes de archivos</span><span class="sxs-lookup"><span data-stu-id="12c54-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12c54-185">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="12c54-185">Type of data</span></span></th>
<th><span data-ttu-id="12c54-186">Dónde se almacenan</span><span class="sxs-lookup"><span data-stu-id="12c54-186">Where stored</span></span></th>
<th><span data-ttu-id="12c54-187">Descripción/Cuándo hacer una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="12c54-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12c54-188">Almacén de archivos de Lync Server</span><span class="sxs-lookup"><span data-stu-id="12c54-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="12c54-189">Normalmente en un servidor de archivos, un clúster de archivos o un servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="12c54-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="12c54-190">Contenido de la reunión, los metadatos de contenido, las reuniones registros de cumplimiento, los archivos de datos de aplicaciones, los archivos de actualización para actualizaciones de dispositivos, los archivos de audio para el grupo de respuesta, el estacionamiento de llamadas y las aplicaciones de anuncio y los archivos publicados en los salones de chat persistente</span><span class="sxs-lookup"><span data-stu-id="12c54-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="12c54-191">Haga la copia de seguridad con el resto de copias de seguridad habituales.</span><span class="sxs-lookup"><span data-stu-id="12c54-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="12c54-192">Requisitos adicionales de las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="12c54-192">Additional Backup Requirements</span></span>

<span data-ttu-id="12c54-193">Para ayudar a garantizar la posibilidad de restaurar los servicios de Lync Server en caso de que se produzca un error, debe hacer una copia de seguridad de algunos componentes necesarios que no formen parte de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="12c54-194">Los siguientes componentes no se incluyen en la copia de seguridad ni se restauran como parte del proceso de copia de seguridad y restauración de Lync Server que se describe en este documento:</span><span class="sxs-lookup"><span data-stu-id="12c54-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="12c54-195">Servicios de dominio de **Active**     Directory Debe hacer una copia de seguridad de AD DS con las herramientas de Active Directory al mismo tiempo que realiza una copia de seguridad de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="12c54-196">Es importante mantener AD DS sincronizado con Lync Server, para evitar problemas que se pueden producir cuando Lync Server espera objetos de contacto que no coinciden con los de AD DS.</span><span class="sxs-lookup"><span data-stu-id="12c54-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="12c54-197">AD DS almacena los siguientes valores de configuración que se usan en Lync Server:</span><span class="sxs-lookup"><span data-stu-id="12c54-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="12c54-198">URI del SIP del usuario y otras opciones de configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="12c54-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="12c54-199">Objetos de contacto para aplicaciones como grupo de respuesta y operador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="12c54-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="12c54-200">Un puntero al almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="12c54-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="12c54-201">Cuenta de autenticación Kerberos (un objeto de equipo opcional) y grupos de seguridad de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="12c54-202">Para obtener información detallada sobre cómo realizar copias de seguridad y restaurar AD DS en Windows Server 2008, consulte la guía paso a paso de copia de seguridad y recuperación de AD DS en [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .</span><span class="sxs-lookup"><span data-stu-id="12c54-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="12c54-203">**Entidad de certificación y certificados**     Use la Directiva de la organización para hacer una copia de seguridad de la entidad de certificación (CA) y los certificados.</span><span class="sxs-lookup"><span data-stu-id="12c54-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="12c54-204">Si usa claves privadas exportables, puede hacer una copia de seguridad del certificado y la clave privada y, a continuación, exportarlos si usa los procedimientos de este documento para restaurar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="12c54-205">Si usa una CA interna, puede volver a inscribirse si necesita restaurar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="12c54-206">Es importante que conserve la clave privada en un lugar seguro donde esté disponible en caso de que se produzca un error en un equipo.</span><span class="sxs-lookup"><span data-stu-id="12c54-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="12c54-207">**System Center Operations Manager**     Si usa Microsoft System Center Operations Manager (anteriormente, Microsoft Operations Manager) para supervisar la implementación de Lync Server, puede hacer una copia de seguridad de los datos que crea mientras supervisa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="12c54-208">Use el proceso de copia de seguridad estándar de SQL Server para hacer una copia de seguridad de los archivos de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="12c54-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="12c54-209">Estos archivos no se restauran durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="12c54-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="12c54-210">**Configuración de puerta de enlace de red telefónica conmutada (RTC)**     Si usa dispositivos de telefonía IP empresarial o de sucursal con funciones de supervivencia, debe realizar una copia de seguridad de la configuración de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="12c54-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="12c54-211">Consulte con su proveedor para obtener más detalles sobre cómo hacer una copia de seguridad y restaurar configuraciones de puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="12c54-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="12c54-212">**Versiones coexistentes de Lync Server u Office Communications Server**     Si su implementación de Lync Server 2013 coexiste con Lync Server 2010 o con una versión anterior de Office Communications Server, no puede usar los procedimientos de este documento para realizar copias de seguridad o restaurar la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="12c54-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="12c54-213">En lugar de ello, debe seguir los procedimientos de copias de seguridad y restauración documentados específicamente para la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="12c54-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="12c54-214">Para más detalles sobre cómo realizar copias de seguridad y restaurar Lync Server 2010, consulte [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span><span class="sxs-lookup"><span data-stu-id="12c54-214">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="12c54-215">Para obtener más información sobre cómo realizar copias de seguridad y restaurar Microsoft Office Communications Server 2007 R2, consulte [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .</span><span class="sxs-lookup"><span data-stu-id="12c54-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="12c54-216">**Información**     de infraestructura Debe hacer una copia de seguridad de la infraestructura, como la configuración del firewall, la configuración del equilibrio de carga, la configuración de Internet Information Services (IIS), los registros del sistema de nombres de dominio (DNS) y las direcciones IP, y la configuración del Protocolo de configuración dinámica de host (DHCP).</span><span class="sxs-lookup"><span data-stu-id="12c54-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="12c54-217">Para más información detallada sobre cómo hacer una copia de seguridad de estos componentes, consulte con los proveedores correspondientes.</span><span class="sxs-lookup"><span data-stu-id="12c54-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="12c54-218">**Mensajería unificada (MU) de Microsoft Exchange y Exchange**     Realice una copia de seguridad y restaure Microsoft Exchange y Exchange UM tal como se describe en la documentación de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c54-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="12c54-219">Para más detalles sobre cómo realizar copias de seguridad y restaurar Exchange Server 2013, consulte [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) .</span><span class="sxs-lookup"><span data-stu-id="12c54-219">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="12c54-220">Para más detalles sobre cómo realizar copias de seguridad y restaurar Exchange Server 2010, consulte [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .</span><span class="sxs-lookup"><span data-stu-id="12c54-220">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="12c54-221">Tenga en cuenta que Lync Server 2013 presenta la capacidad de tener listas de contactos de usuarios, fotos de usuarios de alta definición y datos de archivado almacenados en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="12c54-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="12c54-222">Consulte la lista siguiente para ver cómo realizar una copia de seguridad de estos tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="12c54-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="12c54-223">Se realiza una copia de seguridad de las **fotos de alta definición** como parte de la copia de seguridad de Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="12c54-224">El **almacén de contactos unificado** se presenta en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12c54-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="12c54-225">Almacén de contactos unificado permite a los usuarios mantener toda su información de contacto en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="12c54-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="12c54-226">Debe asegurarse de que las copias de seguridad están actualizadas para los usuarios en cuanto a si sus contactos de usuario se almacenan en el almacén de contactos unificados o en el servidor back-end de Lync.</span><span class="sxs-lookup"><span data-stu-id="12c54-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="12c54-227">Los siguientes escenarios ilustran dónde migrar contactos de usuario al almacén de contactos unificado puede causar problemas en el proceso de copia de seguridad y restauración.</span><span class="sxs-lookup"><span data-stu-id="12c54-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="12c54-228">**Escenario 1:** Los contactos de usuario se migran al almacén de contactos unificado y se realiza una restauración desde una copia de seguridad de Lync Server realizada antes de la migración de los contactos de usuario.</span><span class="sxs-lookup"><span data-stu-id="12c54-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="12c54-229">En este escenario, el usuario tendrá un estado de contactos obsoletos durante un máximo de un día hasta que la tarea de migración de Lync Server comience a migrar los contactos de usuario a Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c54-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="12c54-230">(Tenga en cuenta que, puesto que los contactos de usuario se han migrado anteriormente al almacén de contactos unificado, se usará la información de contacto de Exchange).</span><span class="sxs-lookup"><span data-stu-id="12c54-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="12c54-231">No se necesita ninguna intervención del administrador en este escenario.</span><span class="sxs-lookup"><span data-stu-id="12c54-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="12c54-232">**Escenario 2:** Los contactos de usuario se almacenaban anteriormente en el almacén de contactos unificados, pero luego se revirtieron.</span><span class="sxs-lookup"><span data-stu-id="12c54-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="12c54-233">Se realiza una restauración desde una copia de seguridad de Lync Server tomada cuando los contactos de usuario se almacenaron en el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="12c54-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="12c54-234">En este escenario, un mensaje de error de `Error: Incorrect Exchange Version` en los registros del servidor o el cliente de Lyss puede indicar que se trata de un problema.</span><span class="sxs-lookup"><span data-stu-id="12c54-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="12c54-235">El usuario podrá tener acceso a su lista de contactos en Lync 2013 directamente desde Exchange, pero el estado del cliente no coincidirá con el estado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="12c54-236">Para solucionar esto, un administrador tendrá que ejecutar los cmdlets **Invoke-CsUCSRollback** para los usuarios afectados.</span><span class="sxs-lookup"><span data-stu-id="12c54-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="12c54-237">Los **datos de archivado** se pueden almacenar en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="12c54-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="12c54-238">Estos datos no son críticos para Lync Server, pero pueden ser críticos para su organización con fines normativos.</span><span class="sxs-lookup"><span data-stu-id="12c54-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="12c54-239">Si los datos de archivado se almacenan en Exchange y son críticos para su organización, siga los procedimientos de copia de seguridad y restauración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c54-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="12c54-240">Tenga en cuenta que los datos de archivado almacenados en Exchange no se pueden volver a mover a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12c54-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="12c54-241">Además, no hay ninguna forma de mover los datos que ya están almacenados en la base de datos de archivado de Lync a Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c54-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

